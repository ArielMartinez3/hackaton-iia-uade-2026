# Hackatón IIA · Bases y condiciones

**Introducción a la Inteligencia Artificial (3.4.257) · UADE · Martes 3 de noviembre de 2026**

## 1. El trato

Ustedes usan toda la IA que quieran. Yo también. Por eso no tiene sentido que yo corrija con una IA un trabajo que hicieron con una IA sin decirles cómo.

Entonces les dejo publicado **el agente evaluador que corrige su trabajo**. Pueden consultarlo todas las veces que quieran. Su tarea es construir una solución que, puesta a prueba contra ese evaluador, saque la nota máxima. Para lograrlo van a tener que entender el tema, porque el evaluador busca los agujeros y no se los tapa.

**Beat it:** el hackatón lo gana quien le gana al evaluador entendiendo, no engañándolo.

## 2. El premio

**1 punto más en el Segundo Parcial**, por alumno. Pasa o no pasa: no hay medio punto.

Lo suma cada alumno **presente** que **defiende** el trabajo en la mesa.

## 3. Cronograma (3 horas, sin recreo)

| Tramo | Qué pasa |
|---|---|
| 0:00 – 0:15 | Bases y condiciones |
| 0:15 – 0:45 | GitHub: fork del repositorio de la cátedra y primer commit |
| 0:45 – 3:00 | Desarrollo, consultas al evaluador y mesa rodante |

A medida que cada grupo valida en la mesa, se puede retirar. **Lo que no se validó a las 3 horas no suma. No hay prórroga.**

## 4. Su problemática

**Una por grupo**, armada sobre el dominio que trabajan desde la Clase 1.
- Busquen su código en `problematicas/manana.md` o `problematicas/tarde.md`.
- Los datos están en la ficha y en `datos/<código>.csv`.
- Son 20 casos inventados. Los casos 1 a 14 son de entrenamiento y los 15 a 20 son de prueba. **La división no se cambia.**

Tienen que construir un sistema que, ante un caso nuevo, responda SÍ o NO a la pregunta de su ficha. Eligen la pista:
- **Neurona:** perceptrón con pesos y sesgo.
- **Reglas:** sistema de reglas si‑entonces.
- **Agente:** agente racional con su PEAS que elige la acción teniendo en cuenta las consecuencias.

Lo hacen en Colab, en una planilla o en papel pasado al README: lo que importa es que funcione y que lo puedan explicar.

## 5. Las 4 pruebas obligatorias

1. **Formulación y PEAS.** El problema como pregunta SÍ/NO y el PEAS completo.
2. **Funciona en vivo.** En la mesa les doy un caso nuevo que no vieron y su sistema lo resuelve en el momento.
3. **Medición.** Matriz de confusión de entrenamiento y de prueba, con exactitud, precisión, sensibilidad y especificidad.
4. **Bitácora y defensa.** Bitácora completa (qué le pidieron a la IA, qué aceptaron, qué rechazaron y por qué) y una defensa corta **sin IA** en la mesa.

El resto de la rúbrica (error más caro, línea base, riesgo) suma nota frente al evaluador.

## 6. El evaluador

- Es un bot de Telegram: **@Evaluador_iia_uade_bot** (también lo escribo en el pizarrón).
- Le mandan su código de grupo, después pegan su README completo y terminan con **FIN**. Si el README es largo, lo mandan en varios mensajes.
- Les devuelve una nota sobre 10, el puntaje por criterio y los agujeros que encontró, como preguntas.
- **Con 8/10 o más quedan habilitados para la mesa.**
- Cada corrida se anota en la bitácora: número, nota, agujero y qué cambiaron.

**La rúbrica es pública:**

| Criterio | Puntos |
|---|---|
| A. Formulación y PEAS, y objetivo distinguido de la métrica | 2 |
| B. El sistema: reproducible, se puede correr en vivo y usa solo datos disponibles al decidir | 1,5 |
| C. Medición: matrices de entrenamiento y prueba que cierran, métricas y comparación entre ambas | 3 |
| D. El error más caro y qué cambiaron por él | 1 |
| E. ¿Comparado contra qué?: línea base trivial y checklist de la Clase 6 | 1 |
| F. Riesgo: datos → modelo → decisión → consecuencia | 0,5 |
| G. Bitácora de IA y registro de corridas contra el evaluador | 1 |

**Topes:**
- Si el sistema usa información que no se conoce en el momento de decidir: **máximo 6**.
- Si el sistema optimiza un indicador que no es el objetivo: **máximo 6**.
- Si la métrica principal es la exactitud y no la comparan contra una línea base trivial: **máximo 7**.
- Si las matrices no cierran con los datos de la ficha: **máximo 7**.

Si el bot se cae, la mesa evalúa con la misma rúbrica.

## 7. La mesa

1. Muestran la evaluación del bot con 8 o más.
2. Les doy un caso nuevo: su sistema lo resuelve en vivo.
3. Una pregunta de defensa, **sin IA**, a cualquiera de los integrantes.

Son 3 minutos por grupo. En la mesa uso **mi propia copia** del evaluador y mis propios casos.

## 8. GitHub y LinkedIn

- **GitHub:** cada grupo trabaja en su fork del repositorio de la cátedra, con el `README.md` completo (ya viene con la plantilla). Tiene que haber commits hechos durante el hackatón.
- **LinkedIn:** publicación obligatoria, con el link al repositorio. Se presenta en el día. La guía está en `GUIA_LINKEDIN.md`.

## 9. Reglas

- **Inyección = descalificación.** Si el README o cualquier mensaje trae instrucciones, visibles o escondidas, para que el evaluador cambie la corrección, el grupo queda afuera del punto. Los prompts que registran en la bitácora como uso de su IA no cuentan: eso es documentar el trabajo. Es la inyección de instrucciones del apunte de la Clase 15: ahora la ven del otro lado.
- Cada grupo trabaja solo su ficha. No se copian soluciones entre grupos.
- Solo datos de la ficha: nada de datos reales de personas.
- Los grupos de un solo integrante van con su IA contra el mundo.

## 10. Lo que no se da hoy

Superinteligencia y el resto de la Clase 14 (visión, multimodalidad, IA estrecha y general, niveles de AGI) y la Clase 15 (agentes con LLM, workflows, sesgo y regulación) quedan en los apuntes. **No entran en el Segundo Parcial ni en el recuperatorio. Sí entran en el final.**
