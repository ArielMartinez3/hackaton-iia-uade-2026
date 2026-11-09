# C01 · ¿Paramos esta bomba de riego para mantenimiento?

**Integrantes:** Ariel Martinez
**IA declarada:** Gemini
**Pista:** Neurona artificial
**Publicación en LinkedIn:** https://lnkd.in/p/dtavpcGA

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

**El sistema emite una orden, no repara la bomba.** La salida algorítmica es una alerta preventiva; el objetivo real es la continuidad del riego. Entre la predicción y el resultado está la cuadrilla técnica: el sistema solo aporta al objetivo de negocio si el taller cuenta con stock de repuestos y la intervención se realiza eficazmente dentro de la ventana de medio día. La Sensibilidad del 100% mide el techo de cobertura del modelo, no la ausencia de fallas mecánicas en el campo.

---

## 2. El sistema

**Cómo decide.** 
Usamos una neurona artificial (perceptrón simple) que combina las tres mediciones físicas con pesos fijos y un sesgo:
n = 2.0 * horas + 1.0 * temperatura + 10.0 * vibración - 155.0

Si la entrada neta n es mayor o igual a 0, el sistema responde SÍ (parar para service). Si n es menor a 0, responde NO (dejar funcionando).

**Variables que usa y por qué.** 
Usamos tres variables disponibles al momento de la revisión:
- Horas de uso desde el último service: mide el desgaste acumulado en el tiempo.
- Temperatura del rodamiento: indica fricción o problemas de lubricación.
- Vibración: es la variable con mayor peso (w=10) porque es el síntoma físico directo de desbalance, desalineación o juego interno en el motor.

Descartamos por completo la columna «Repuestos pedidos en los 30 días siguientes». La decisión del jefe de mantenimiento se toma el día 1 del mes; lo que pase durante los 30 días posteriores es información del futuro que todavía no ocurrió. Usar ese dato para decidir sería fuga de datos (Target Leakage), lo cual falsearía el sistema e invalidaría su aplicación en una situación real.

**Cómo se corre en vivo.** 
Para resolver un caso nuevo:
1. En Google Colab: abrir el notebook https://colab.research.google.com/drive/1sPhevznx9r7qIC8cK8FuAbeJ7Ezlt5aY?usp=sharing , ir a la última celda interactiva y ejecutar la función `resolver_caso_en_vivo_interactivo()`.
2. A mano: calcular la fórmula n = 2.0*(horas) + 1.0*(temperatura) + 10.0*(vibración) - 155.0. Si el resultado da 0 o positivo, la salida es SÍ. Si da negativo, la salida es NO.

**Dos casos de ejemplo.**

| Caso inventado | Valores | Salida del sistema |
|---|---|---|
| A | Horas = 10.0, Temp = 85 °C, Vib = 6.5 mm/s -> n = 2(10) + 1(85) + 10(6.5) - 155 = +15.0 | SÍ |
| B | Horas = 4.0, Temp = 56 °C, Vib = 2.0 mm/s -> n = 2(4) + 1(56) + 10(2.0) - 155 = -71.0 | NO |

---

## 3. Medición

**Entrenamiento (casos 1–14)**

| | Predice SÍ | Predice NO |
|---|---|---|
| **Real SÍ** | VP = 4 | FN = 0 |
| **Real NO** | FP = 0 | VN = 10 |

**Prueba (casos 15–20)**

| | Predice SÍ | Predice NO |
|---|---|---|
| **Real SÍ** | VP = 2 | FN = 0 |
| **Real NO** | FP = 1 | VN = 3 |

| Métrica | Entrenamiento | Prueba |
|---|---|---|
| Exactitud | 100.0% (14/14) | 83.3% (5/6) |
| Precisión | 100.0% (4/4) | 66.7% (2/3) |
| Sensibilidad | 100.0% (4/4) | 100.0% (2/2) |
| Especificidad | 100.0% (10/10) | 75.0% (3/4) |

**Entrenamiento contra prueba.** 
En entrenamiento el modelo acertó el 100% de los casos. En prueba la exactitud bajó a 83.3% por un único falso positivo (Caso 18: Horas 7.7, Temp 81, Vib 6.4, n = +5.4). No es sobreajuste, sino una generalización deliberadamente prudente: la Sensibilidad se mantuvo en 100% (cero fallas omitidas). El caso 18 presentaba valores térmicos y de vibración elevados; ante la duda, el sistema prefirió indicar service preventivo antes que arriesgar una rotura.

**Límites de la muestra de prueba.** Dado que el conjunto de prueba consta de solo 6 casos, cada bomba representa 16.7 puntos porcentuales. Un único desvío produce una caída porcentual visible (del 100% al 83.3%), lo que evidencia que la muestra es pequeña para conclusiones definitivas de exactitud general, pero suficiente para validar la consistencia en Sensibilidad: 2 de 2 fallas reales detectadas.

---

## 4. El error más caro

En este campo el falso negativo es mucho peor que el falso positivo. 
Un falso positivo significa parar una bomba que no iba a fallar: el costo es medio día de riego perdido y pagar un service que no hacía falta. En cambio, un falso negativo significa no parar una bomba que termina rompiéndose en plena campaña: el pivote queda parado varios días en el momento más importante del cultivo y la reparación de urgencia sale varias veces más cara que el service preventivo.

Para evitar ese error, ajustamos el sesgo (b = -155.0) y le dimos peso fuerte a la vibración y a la temperatura. De esta forma, ante valores que se acercan a zonas de riesgo, la neurona da positivo y prioriza no dejar pasar ninguna falla (100% de Sensibilidad).

---

## 5. ¿Comparado contra qué?

**Línea base trivial.** 
Como la mayoría de las bombas no fallan (10 de 14 en entrenamiento y 4 de 6 en prueba), un clasificador ciego que diga siempre NO obtendría:
- Exactitud en entrenamiento: 10/14 = 71.4%
- Exactitud en prueba: 4/6 = 66.7%
- Sensibilidad: 0.0% (dejaría romper todas las bombas averiadas)

Nuestra neurona supera a la línea base en exactitud (100% vs 71.4% en entrenamiento, y 83.3% vs 66.7% en prueba). Sin embargo, la ventaja real está en que alcanza 100% de Sensibilidad frente al 0% de la línea base, cumpliendo el objetivo de detectar todas las roturas.

**El extremo opuesto: responder siempre SÍ.** Un clasificador que responda siempre SÍ lograría también 100% de Sensibilidad, pero con Especificidad 0%: ordenaría detener las 20 bombas, paralizando por completo el esquema de riego del campo. El valor de nuestra neurona reside en sostener el 100% de Sensibilidad interviniendo únicamente 4 de 14 bombas en entrenamiento y 3 de 6 en prueba (75% de Especificidad), maximizando la protección con una disrupción mínima del riego.

| Checklist (Clase 6) | Respuesta |
|---|---|
| ¿Qué datos? | 20 casos de telemetría de bombas provistos en la ficha C01 (14 de entrenamiento y 6 de prueba). Se descartó la columna de repuestos por ser Target Leakage. |
| ¿Qué métrica? | Sensibilidad como métrica central para evitar roturas, acompañada por matriz de confusión completa y Exactitud. |
| ¿Comparado contra qué? | Contra el clasificador trivial «siempre NO» y el extremo de sobrealerta «siempre SÍ». |
| ¿Quién lo midió? | El grupo mediante código en Google Colab, respetando la partición de prueba a ciegas sin tocar los pesos. |

---

## 6. Riesgo: el camino completo

Datos -> Modelo -> Decisión -> Consecuencia

- Datos: sensores de vibración y temperatura instalados en los pozos de riego.
- Riesgo concreto en los datos: un acelerómetro flojo o mal calibrado registra 2.0 mm/s de vibración cuando en realidad la bomba está vibrando a 7.5 mm/s por desgaste interno.
- Modelo: la neurona recibe un valor bajo de vibración y calcula una entrada neta negativa (n < 0).
- Decisión: el sistema predice NO y el encargado deja la bomba funcionando sin mantenimiento.
- Consecuencia: la bomba colapsa en medio de una semana calurosa de riego intensivo. El pivote queda fuera de servicio por falta de repuestos inmediatos, el cultivo sufre estrés hídrico y se generan sobrecostos por reparaciones de urgencia.

**Riesgo sociotécnico: Fatiga de alertas.** Al calibrar el modelo priorizando la Sensibilidad, toleramos falsos positivos marginales. Si el personal operativo experimenta detenciones donde el rodamiento no presentaba anomalías graves, existe el riesgo de que comiencen a desestimar las recomendaciones del sistema («la máquina exagera»), apagando el software o postergando un service preventivo crítico, desembocando en la rotura que se buscaba evitar.

**Condiciones de uso obligatorias:**
1. Las paradas sugeridas deben coordinarse en ventanas de bajo requerimiento hídrico (horarios nocturnos) para atenuar el costo operativo de un posible falso positivo.
2. La alerta técnica no reemplaza la inspección del mecánico: constituye una recomendación de revisión prioritaria antes de desacoplar definitivamente el pivote.

---

## 7. Bitácora

**Uso de la IA**

| # | Qué le pedimos a la IA | Qué aceptamos | Qué rechazamos y por qué |
|:---:|---|---|---|
| 1 | Análisis exploratorio de las variables provistas en el CSV de la ficha C01 y estructura del PEAS. | La definición del entorno agrícola, los actuadores mecánicos y la formulación de la pregunta binaria para la decisión mensual. | Rechazamos la sugerencia inicial de la IA de correlacionar todas las columnas. Detectamos que la variable «Repuestos pedidos en los 30 días siguientes» ocurre después de la inspección y constituye Target Leakage estricto. |
| 2 | Evaluación comparativa entre las 3 pistas (Reglas, Agente racional y Neurona) para definir la arquitectura. | La elección de la Pista 1 (Neurona/Perceptrón lineal de 3 entradas) por su transparencia analítica y facilidad de resolución manual en vivo. | Rechazamos la Pista 2 (Reglas) por volverse rígida ante casos límite, y la Pista 3 (Agente) porque requería definir matrices de decisión complejas sin datos suficientes en la ficha. |
| 3 | Calibración de pesos y sesgo para los 14 casos de entrenamiento. | Los pesos relativos w = (2.0 para horas, 1.0 para temperatura y 10.0 para vibración) por reflejar la criticidad física del desbalance mecánico. | Rechazamos una propuesta inicial con sesgo neutro (b = -160) porque priorizaba la exactitud simétrica y generaba riesgo de falsos negativos en casos límite. Exigimos ajustar b = -155 para priorizar 100% de Sensibilidad. |
| 4 | Desarrollo del script en Python para Google Colab y cálculo automatizado de matrices de confusión. | La función de partición fija de datos, las fórmulas matemáticas de las 4 métricas y la verificación de que las cuentas cerraran con los 20 casos de la ficha. | Rechazamos el uso de librerías de caja negra como scikit-learn (LogisticRegression). Exigimos programar el cálculo de la entrada neta y la matriz de confusión con funciones nativas de Python/Pandas para transparentar la aritmética. |
| 5 | Manejo de errores de carga en el notebook y estandarización de datos. | El bloque de código para normalizar los nombres de columnas del CSV y el casteo de valores con comas decimales a float. | Rechazamos salidas visuales recargadas con caracteres innecesarios. Pedimos simplificar los prints de consola para que la lectura de resultados sea limpia y directa. |
| 6 | Diseño del método de prueba en vivo para la defensa oral obligatoria. | La creación de una función interactiva con captura de datos por teclado (`input`) para ingresar horas, temperatura y vibración en tiempo real. | Rechazamos dejar una celda estática que requiriera modificar el código fuente frente al profesor; el modo interactivo permite ingresar los valores que dicte el docente y veredicto inmediato. |

**Registro de versiones**

| Versión | Commit | Qué cambió | Por qué |
|:---:|---|---|---|
| 1 | `Encabezado y Sección 1: Formulación PEAS` | Formulación de la pregunta binaria, desglose de la tabla PEAS y distinción entre objetivo de campo y métrica técnica. | Establecer el marco de decisión y fijar la Sensibilidad como norte antes de construir el modelo. |
| 2 | `Sección 2: Arquitectura de neurona y descarte de target leakage` | Definición de pesos w=(2, 1, 10), sesgo b=-155, justificación del descarte de repuestos y dos casos inventados (A y B). | Documentar el modelo matemático explicable y blindar el sistema contra fuga de datos del futuro. |
| 3 | `Sección 3: Matrices de confusión y métricas completas` | Cuentas fila por fila de entrenamiento y prueba, matrices 2x2 verificadas y tabla comparativa de métricas. | Validar que el sistema generaliza con 100% de Sensibilidad y 83.3% de Exactitud en casos no vistos. |
| 4 | `Secciones 4, 5 y 6: Análisis de error, línea base y riesgo` | Justificación del costo del Falso Negativo, contraste contra la línea base trivial de clase mayoritaria y flujo de riesgo técnico. | Demostrar que el modelo aporta valor real sobre el clasificador ciego y previene roturas caras. |
| 5 | `Sección 7: Bitácora de IA y registro de versiones` | Detalle exhaustivo de interacción con la IA (6 iteraciones) y registro de commits del repositorio. | Transparentar la autoría, la auditoría metodológica y cumplir con el Criterio G de la rúbrica. |
| 6 | `Refinamiento: Fatiga de alertas, límites muestrales y baseline siempre SÍ` | Incorporación del límite muestral (16.7%/caso), baseline «siempre SÍ», fatiga de alertas y condiciones de uso. | Robustecer el análisis sociotécnico y desarmar la trampa de maximizar sensibilidad a costa de sobrealertas. |
| 7 | `Cierre: Link a publicación en LinkedIn` | Incorporación del enlace a la publicación pública obligatoria en LinkedIn en el encabezado. | Completar la totalidad de los requisitos de entrega estipulados por la cátedra. |
