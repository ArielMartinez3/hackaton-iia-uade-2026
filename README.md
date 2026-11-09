# C01 · ¿Paramos esta bomba de riego para mantenimiento?

**Integrantes:** Ariel Martinez
**IA declarada:** Gemini
**Pista:** Neurona artificial
**Publicación en LinkedIn:** <pendiente de publicación>

---

## 1. Formulación y PEAS

**La pregunta.** Para cada bomba revisada a principio de mes, ¿la bomba de riego fallará en los 30 días siguientes a la revisión? SÍ significa que la bomba va a romperse dentro de ese mes y se debe parar medio día para service preventivo. NO significa que la bomba puede seguir operando con normalidad hasta la próxima revisión.

| PEAS | Su sistema |
|---|---|
| Medida de rendimiento | Maximizar el tiempo de riego disponible en los momentos críticos de la campaña, evitar roturas imprevistas que paren los pivotes por días y minimizar los costos de reparaciones de urgencia y pérdidas de cultivo. |
| Entorno | Campo con sistema de riego por pivote central abastecido por bombas de pozo profundo, sometidas a desgaste mecánico y demanda hídrica estacional. |
| Actuadores | Orden de trabajo para frenar la bomba medio día por service preventivo, cuadrilla de mantenimiento y reemplazo de rodamientos o piezas desgastadas. |
| Sensores | Datos de la inspección mensual: horas de uso desde el último service (en cientos de horas), temperatura del rodamiento (°C) y vibración mecánica (mm/s). |

**Objetivo y métrica.** 
Lo que de verdad importa en el problema es que ninguna bomba se rompa en plena campaña de riego. Quedarse sin regar varios días daña el rendimiento del cultivo y la reparación de urgencia sale mucho más cara que un service programado. 
La métrica técnica para medirlo es la Sensibilidad (Recall = VP / (VP + FN)). 
No son lo mismo: la métrica es una cuenta estadística sobre los datos, mientras que el objetivo es la continuidad operativa y económica del campo. Si nos fijáramos solo en la Exactitud, un modelo ingenuo que diga siempre que NO paramos la bomba tendría un 71.4% de exactitud en entrenamiento, pero una Sensibilidad del 0% (se romperían todas las bombas averiadas). Por eso, el sistema se ajusta para priorizar la Sensibilidad por encima de la Exactitud.

---

## 2. El sistema

**Cómo decide.** 
Usamos una neurona artificial (perceptrón simple) que combina las tres mediciones físicas con pesos fijos y un sesgo:
n = 2.0 * horas + 1.0 * temperatura + 10.0 * vibración - 155.0

Si la entrada neta n es mayor o igual a 0, el sistema responde SÍ (parar para service). Si n es menor a 0, responde NO (dejar funcionando).

**Variables que usa y por qué.** 
Usamos tres variables disponibles al momento de la revisión:
* Horas de uso desde el último service: mide el desgaste acumulado en el tiempo.
* Temperatura del rodamiento: indica fricción o problemas de lubricación.
* Vibración: es la variable con mayor peso (w=10) porque es el síntoma físico directo de desbalance, desalineación o juego interno en el motor.

Descartamos por completo la columna «Repuestos pedidos en los 30 días siguientes». La decisión del jefe de mantenimiento se toma el día 1 del mes; lo que pase durante los 30 días posteriores es información del futuro que todavía no ocurrió. Usar ese dato para decidir sería fuga de datos (Target Leakage), lo cual falsearía el sistema e invalidaría su aplicación en una situación real.

**Cómo se corre en vivo.** 
Para resolver un caso nuevo:
1. En Google Colab: abrir el notebook https://colab.research.google.com/drive/1YqulaTRLl97Imyau1eRLstemMBZiIskB?usp=sharing , ir a la celda 8 y ejecutar la función `resolver_caso_en_vivo(horas, temp, vib)`.
2. A mano: calcular la fórmula n = 2.0*(horas) + 1.0*(temperatura) + 10.0*(vibración) - 155.0. Si el resultado da 0 o positivo, la salida es SÍ. Si da negativo, la salida es NO.

**Dos casos de ejemplo.**

| Caso inventado | Valores | Salida del sistema |
|---|---|---|
| A | Horas = 10.0, Temp = 85 °C, Vib = 6.5 mm/s -> n = 2(10) + 1(85) + 10(6.5) - 155 = +15.0 | SÍ |
| B | Horas = 4.0, Temp = 56 °C, Vib = 2.0 mm/s -> n = 2(4) + 1(56) + 10(2.0) - 155 = -71.0 | NO |
