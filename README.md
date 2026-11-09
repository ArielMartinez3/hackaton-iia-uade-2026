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
