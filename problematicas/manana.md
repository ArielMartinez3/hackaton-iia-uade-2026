# Problemáticas · Hackatón IIA · Comisión Mañana

Cada grupo tiene **una problemática propia**, armada sobre el dominio que trabaja desde la Clase 1. Tu código de grupo se proyecta al empezar la clase. Buscalo acá y trabajá solo con tu ficha.

**Cómo están armados los datos**
- Son 20 casos inventados. Ninguno corresponde a una persona real.
- Los casos 1 a 14 son de **entrenamiento**: con ellos construís o ajustás tu sistema.
- Los casos 15 a 20 son de **prueba**: no los mirás para construir; solo los usás para medir.
- La división no se cambia.
- La última columna es el resultado real: 1 = SÍ, 0 = NO.
- Los mismos datos están en `datos/<código>.csv`, listos para Colab o una planilla.

**Qué tenés que construir:** un sistema que, ante un caso nuevo, responda SÍ o NO a la pregunta de tu ficha. Elegís la pista:
- **Neurona:** un perceptrón con pesos y sesgo (Clases 9 y 10).
- **Reglas:** un sistema de reglas si‑entonces.
- **Agente:** un agente racional con su PEAS que, ante cada caso, elige la acción teniendo en cuenta las consecuencias (Clase 12).

Las condiciones, las pruebas y el evaluador están en `BASES.md`.

---

## M01 · ¿Roma acepta la batalla campal?

**Dominio:** El imperio Romano · **IA declarada:** ChatGPT

**Situación.** Segunda Guerra Púnica. Un cónsul romano tiene que decidir si acepta la batalla campal que le ofrece Aníbal o si la rehúye, como hacía Fabio Máximo. Cada caso es una batalla ofrecida.

**Quién decide.** El cónsul y su consejo de guerra.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = si Roma acepta la batalla, la gana.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Aceptar una batalla que se pierde: es Cannas. Se pierde un ejército consular entero y aliados itálicos se pasan a Aníbal.
- Falso negativo (dice NO y era SÍ): Rehuir una batalla que se ganaba: la guerra se alarga, Aníbal sigue saqueando Italia y el Senado pierde paciencia.

**Datos** (también en `datos/M01.csv`)

| Caso | Conjunto | Relación de fuerzas (infantería romana / cartaginesa) | Caballería propia (% del ejército) | Terreno favorable (índice 0 a 10; 10 = llano propio y conocido) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 1,33 | 14 | 3 | 0 |
| 2 | Entrenamiento | 1,24 | 23 | 0 | 0 |
| 3 | Entrenamiento | 1,05 | 33 | 7 | 1 |
| 4 | Entrenamiento | 0,99 | 14 | 6 | 0 |
| 5 | Entrenamiento | 1,02 | 9 | 6 | 0 |
| 6 | Entrenamiento | 0,62 | 16 | 4 | 0 |
| 7 | Entrenamiento | 1,77 | 13 | 2 | 0 |
| 8 | Entrenamiento | 1,63 | 35 | 9 | 1 |
| 9 | Entrenamiento | 1,51 | 32 | 10 | 1 |
| 10 | Entrenamiento | 0,87 | 35 | 7 | 1 |
| 11 | Entrenamiento | 0,79 | 17 | 8 | 1 |
| 12 | Entrenamiento | 1,19 | 30 | 0 | 0 |
| 13 | Entrenamiento | 0,88 | 22 | 2 | 0 |
| 14 | Entrenamiento | 1,92 | 28 | 9 | 1 |
| 15 | Prueba | 1,36 | 18 | 6 | 1 |
| 16 | Prueba | 0,82 | 27 | 4 | 0 |
| 17 | Prueba | 1,33 | 24 | 5 | 0 |
| 18 | Prueba | 1,81 | 30 | 2 | 1 |
| 19 | Prueba | 0,81 | 10 | 3 | 0 |
| 20 | Prueba | 0,99 | 28 | 6 | 1 |

---

## M02 · ¿Derivar a consulta nutricional?

**Dominio:** Obesidad y alimentación saludable · **IA declarada:** Google Gemini

**Situación.** Una app de salud de una prepaga revisa los hábitos que registran sus afiliados adultos y decide a quién derivar a una consulta nutricional preventiva. Cada caso es un afiliado.

**Quién decide.** El equipo de prevención de la prepaga.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el afiliado desarrolla obesidad en los 12 meses siguientes.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Derivar a alguien que no lo necesitaba: un turno ocupado y una consulta de más.
- Falso negativo (dice NO y era SÍ): No derivar a alguien que sí lo necesitaba: se pierde la ventana de prevención.

**Datos** (también en `datos/M02.csv`)

| Caso | Conjunto | Horas sentado por día (h) | Porciones de ultraprocesados (por semana) | Pasos diarios (miles) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 10 | 12 | 13,6 | 0 |
| 2 | Entrenamiento | 8 | 3 | 6,8 | 0 |
| 3 | Entrenamiento | 8 | 6 | 2,8 | 0 |
| 4 | Entrenamiento | 12 | 21 | 4,8 | 1 |
| 5 | Entrenamiento | 5 | 18 | 8,3 | 0 |
| 6 | Entrenamiento | 6 | 10 | 5,2 | 0 |
| 7 | Entrenamiento | 14 | 14 | 11,8 | 0 |
| 8 | Entrenamiento | 6 | 15 | 5,8 | 0 |
| 9 | Entrenamiento | 6 | 11 | 2,9 | 0 |
| 10 | Entrenamiento | 11 | 24 | 6,0 | 1 |
| 11 | Entrenamiento | 8 | 12 | 12,2 | 0 |
| 12 | Entrenamiento | 6 | 30 | 10,5 | 0 |
| 13 | Entrenamiento | 4 | 7 | 11,9 | 0 |
| 14 | Entrenamiento | 10 | 14 | 6,1 | 0 |
| 15 | Prueba | 9 | 24 | 8,1 | 1 |
| 16 | Prueba | 8 | 11 | 9,2 | 0 |
| 17 | Prueba | 3 | 15 | 12,6 | 0 |
| 18 | Prueba | 8 | 16 | 5,0 | 0 |
| 19 | Prueba | 5 | 9 | 10,3 | 0 |
| 20 | Prueba | 7 | 18 | 5,4 | 0 |

---

## M03 · ¿Este pedido es fraudulento?

**Dominio:** Comercio Electronico · **IA declarada:** Claude

**Situación.** Una tienda online revisa cada pedido antes de despacharlo para frenar compras hechas con tarjetas robadas. Cada caso es un pedido.

**Quién decide.** El sistema antifraude de la tienda, antes de despachar.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el pedido es fraudulento.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Frenar un pedido legítimo: cliente enojado y venta perdida.
- Falso negativo (dice NO y era SÍ): Despachar un pedido fraudulento: se pierde la mercadería y el banco cobra el contracargo.

**Datos** (también en `datos/M03.csv`)

| Caso | Conjunto | Monto del pedido (USD) | Antigüedad de la cuenta (días) | Distancia envío–facturación (km) | Contracargo registrado (0 = no, 1 = sí) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 245 | 13 | 214 | 0 | 0 |
| 2 | Entrenamiento | 339 | 713 | 425 | 0 | 0 |
| 3 | Entrenamiento | 136 | 34 | 485 | 1 | 1 |
| 4 | Entrenamiento | 578 | 309 | 527 | 1 | 1 |
| 5 | Entrenamiento | 373 | 435 | 202 | 0 | 0 |
| 6 | Entrenamiento | 181 | 86 | 1261 | 1 | 1 |
| 7 | Entrenamiento | 648 | 667 | 370 | 0 | 0 |
| 8 | Entrenamiento | 379 | 105 | 1064 | 1 | 1 |
| 9 | Entrenamiento | 322 | 406 | 701 | 0 | 0 |
| 10 | Entrenamiento | 282 | 538 | 619 | 0 | 0 |
| 11 | Entrenamiento | 43 | 2 | 1226 | 1 | 1 |
| 12 | Entrenamiento | 360 | 243 | 832 | 1 | 1 |
| 13 | Entrenamiento | 685 | 240 | 33 | 0 | 0 |
| 14 | Entrenamiento | 143 | 111 | 378 | 0 | 0 |
| 15 | Prueba | 783 | 487 | 694 | 1 | 1 |
| 16 | Prueba | 81 | 428 | 36 | 0 | 0 |
| 17 | Prueba | 352 | 257 | 1121 | 1 | 1 |
| 18 | Prueba | 224 | 96 | 317 | 1 | 1 |
| 19 | Prueba | 371 | 669 | 522 | 0 | 0 |
| 20 | Prueba | 567 | 42 | 307 | 1 | 1 |

---

## M04 · ¿Este título va a la portada del usuario?

**Dominio:** Dominio de recomendacion en Streaming. · **IA declarada:** Claude

**Situación.** Una plataforma de streaming elige qué títulos mostrar en la fila principal de cada usuario. Cada caso es un par usuario–título candidato.

**Quién decide.** El recomendador de la portada.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el usuario mira más del 70 % del título.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Poner en portada algo que no termina: un lugar desperdiciado y un usuario que siente que la plataforma no lo conoce.
- Falso negativo (dice NO y era SÍ): Dejar afuera algo que habría disfrutado: una oportunidad perdida de retenerlo.

**Dato de contexto.** El equipo de producto hoy premia la tasa de clics en la portada.

**Datos** (también en `datos/M04.csv`)

| Caso | Conjunto | Afinidad con su historial (0 a 1) | Duración (min) | Calificación del título (0 a 10) | Clics esperados en la miniatura (% estimado) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 0,33 | 115 | 4,2 | 22 | 0 |
| 2 | Entrenamiento | 0,75 | 172 | 9,1 | 3 | 1 |
| 3 | Entrenamiento | 0,57 | 169 | 3,9 | 9 | 0 |
| 4 | Entrenamiento | 0,26 | 55 | 7,3 | 4 | 1 |
| 5 | Entrenamiento | 0,14 | 164 | 4,0 | 23 | 0 |
| 6 | Entrenamiento | 0,64 | 69 | 5,0 | 17 | 1 |
| 7 | Entrenamiento | 0,71 | 34 | 8,4 | 2 | 1 |
| 8 | Entrenamiento | 0,66 | 140 | 7,7 | 3 | 1 |
| 9 | Entrenamiento | 0,96 | 27 | 9,4 | 20 | 1 |
| 10 | Entrenamiento | 0,59 | 50 | 7,6 | 21 | 1 |
| 11 | Entrenamiento | 0,03 | 176 | 5,3 | 22 | 0 |
| 12 | Entrenamiento | 0,19 | 61 | 6,2 | 17 | 0 |
| 13 | Entrenamiento | 0,11 | 106 | 6,4 | 24 | 0 |
| 14 | Entrenamiento | 0,71 | 158 | 5,5 | 24 | 0 |
| 15 | Prueba | 0,83 | 38 | 9,3 | 4 | 1 |
| 16 | Prueba | 0,48 | 135 | 6,3 | 19 | 0 |
| 17 | Prueba | 0,35 | 103 | 5,4 | 18 | 0 |
| 18 | Prueba | 0,34 | 116 | 9,3 | 8 | 0 |
| 19 | Prueba | 0,98 | 92 | 3,3 | 20 | 1 |
| 20 | Prueba | 0,71 | 55 | 3,9 | 17 | 0 |

---

## M05 · ¿Este cliente se va el próximo trimestre?

**Dominio:** Logística: Fuga de clientes · **IA declarada:** Claude

**Situación.** Una empresa de logística trabaja con comercios que le tercerizan sus envíos. Quiere detectar a tiempo qué clientes están por irse a la competencia. Cada caso es un cliente.

**Quién decide.** El área comercial, que puede ofrecer una bonificación de retención.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el cliente se va en el próximo trimestre.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Bonificar a un cliente que no se iba: se regala un 5 % de una factura.
- Falso negativo (dice NO y era SÍ): No detectar a un cliente que se va: se pierde toda su facturación anual.

**Datos** (también en `datos/M05.csv`)

| Caso | Conjunto | Entregas tardías (% del último trimestre) | Reclamos abiertos (cantidad) | Antigüedad como cliente (meses) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 39 | 6 | 1 | 1 |
| 2 | Entrenamiento | 31 | 6 | 35 | 1 |
| 3 | Entrenamiento | 4 | 5 | 21 | 0 |
| 4 | Entrenamiento | 1 | 9 | 45 | 0 |
| 5 | Entrenamiento | 18 | 2 | 48 | 0 |
| 6 | Entrenamiento | 0 | 1 | 9 | 0 |
| 7 | Entrenamiento | 21 | 6 | 29 | 1 |
| 8 | Entrenamiento | 39 | 8 | 46 | 1 |
| 9 | Entrenamiento | 34 | 10 | 22 | 1 |
| 10 | Entrenamiento | 15 | 6 | 50 | 1 |
| 11 | Entrenamiento | 28 | 8 | 24 | 1 |
| 12 | Entrenamiento | 40 | 8 | 45 | 1 |
| 13 | Entrenamiento | 1 | 8 | 41 | 0 |
| 14 | Entrenamiento | 33 | 6 | 14 | 1 |
| 15 | Prueba | 5 | 6 | 17 | 1 |
| 16 | Prueba | 13 | 6 | 50 | 0 |
| 17 | Prueba | 2 | 5 | 20 | 0 |
| 18 | Prueba | 6 | 9 | 49 | 0 |
| 19 | Prueba | 20 | 4 | 6 | 1 |
| 20 | Prueba | 24 | 3 | 25 | 0 |

---

## M06 · ¿Rotamos a este jugador?

**Dominio:** futbol (cuerpo tecnico) · **IA declarada:** ChatGPT

**Situación.** El cuerpo técnico de un club de Primera tiene que decidir quién descansa en la próxima fecha para prevenir lesiones musculares. Cada caso es un jugador en una semana.

**Quién decide.** El cuerpo técnico, con el preparador físico.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el jugador sufre una lesión muscular en los 14 días siguientes.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Rotar a alguien que no se iba a lesionar: el equipo juega sin un titular.
- Falso negativo (dice NO y era SÍ): No rotar a quien se lesiona: se pierde al jugador tres o cuatro semanas.

**Datos** (también en `datos/M06.csv`)

| Caso | Conjunto | Minutos jugados (últimos 7 días) | Distancia a alta intensidad (km en la semana) | Sueño promedio (h por noche) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 285 | 3,4 | 7,1 | 1 |
| 2 | Entrenamiento | 155 | 3,6 | 5,9 | 1 |
| 3 | Entrenamiento | 20 | 3,5 | 7,4 | 0 |
| 4 | Entrenamiento | 140 | 1,4 | 8,3 | 0 |
| 5 | Entrenamiento | 58 | 2,1 | 7,9 | 0 |
| 6 | Entrenamiento | 137 | 1,3 | 5,8 | 0 |
| 7 | Entrenamiento | 221 | 1,0 | 8,8 | 0 |
| 8 | Entrenamiento | 29 | 1,8 | 7,9 | 0 |
| 9 | Entrenamiento | 339 | 2,0 | 7,3 | 0 |
| 10 | Entrenamiento | 30 | 3,7 | 6,1 | 0 |
| 11 | Entrenamiento | 8 | 3,5 | 8,2 | 0 |
| 12 | Entrenamiento | 230 | 3,4 | 8,9 | 0 |
| 13 | Entrenamiento | 44 | 2,0 | 5,3 | 0 |
| 14 | Entrenamiento | 240 | 2,1 | 6,8 | 0 |
| 15 | Prueba | 136 | 2,2 | 8,1 | 0 |
| 16 | Prueba | 296 | 0,7 | 5,4 | 0 |
| 17 | Prueba | 71 | 2,7 | 6,7 | 0 |
| 18 | Prueba | 122 | 3,8 | 5,7 | 0 |
| 19 | Prueba | 14 | 2,0 | 6,7 | 0 |
| 20 | Prueba | 343 | 3,0 | 5,7 | 1 |

---

## M07 · ¿Le indicamos antibiótico?

**Dominio:** Medicina · **IA declarada:** Deepseek

**Situación.** En una guardia hay que decidir si una infección respiratoria es bacteriana y requiere antibiótico, o si es viral. Cada caso es un paciente (datos inventados).

**Quién decide.** El médico de guardia, asistido por el sistema.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la infección es bacteriana.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Dar antibiótico a una infección viral: no sirve, tiene efectos adversos y alimenta la resistencia bacteriana.
- Falso negativo (dice NO y era SÍ): No dar antibiótico a una infección bacteriana: el paciente puede complicarse, incluso con una neumonía grave.

**Datos** (también en `datos/M07.csv`)

| Caso | Conjunto | Temperatura (°C) | Leucocitos (miles por µL) | Proteína C reactiva (mg/L) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 37,7 | 14,8 | 47 | 0 |
| 2 | Entrenamiento | 37,0 | 12,0 | 5 | 0 |
| 3 | Entrenamiento | 39,6 | 15,3 | 80 | 1 |
| 4 | Entrenamiento | 38,5 | 7,8 | 96 | 0 |
| 5 | Entrenamiento | 36,6 | 12,4 | 178 | 1 |
| 6 | Entrenamiento | 37,2 | 5,8 | 188 | 0 |
| 7 | Entrenamiento | 38,5 | 22,1 | 155 | 1 |
| 8 | Entrenamiento | 38,5 | 9,4 | 18 | 0 |
| 9 | Entrenamiento | 36,8 | 13,8 | 159 | 1 |
| 10 | Entrenamiento | 37,5 | 20,8 | 68 | 1 |
| 11 | Entrenamiento | 37,7 | 9,3 | 42 | 0 |
| 12 | Entrenamiento | 40,1 | 16,9 | 171 | 1 |
| 13 | Entrenamiento | 38,1 | 11,5 | 135 | 0 |
| 14 | Entrenamiento | 39,7 | 18,2 | 127 | 1 |
| 15 | Prueba | 39,7 | 22,3 | 100 | 1 |
| 16 | Prueba | 38,7 | 24,4 | 29 | 1 |
| 17 | Prueba | 37,6 | 10,7 | 79 | 0 |
| 18 | Prueba | 37,8 | 16,6 | 60 | 1 |
| 19 | Prueba | 39,3 | 4,9 | 36 | 0 |
| 20 | Prueba | 37,3 | 19,7 | 129 | 1 |

---

## M08 · ¿Llega a la maratón por debajo de 4 horas?

**Dominio:** deportes · **IA declarada:** Gemini

**Situación.** Un running team prepara a corredores amateurs para la maratón de Buenos Aires y quiere saber, ocho semanas antes, quién está en condiciones de bajar las 4 horas. Cada caso es un corredor.

**Quién decide.** El entrenador del running team.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el corredor termina la maratón en menos de 4 horas.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Decirle que va por debajo de 4 h a quien no llega: sale demasiado rápido y se funde en el km 30.
- Falso negativo (dice NO y era SÍ): Decirle que no llega a quien sí podía: entrena con miedo y se pierde la marca.

**Dato de contexto.** El ranking interno del team premia a quien más kilómetros suma por semana.

**Datos** (también en `datos/M08.csv`)

| Caso | Conjunto | Fondo más largo (km) | Ritmo en 10K (min por km) | Semanas sin lesión (de las últimas 12) | Km semanales (km) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 29 | 6,6 | 10 | 72 | 0 |
| 2 | Entrenamiento | 13 | 6,5 | 8 | 61 | 0 |
| 3 | Entrenamiento | 31 | 4,3 | 5 | 25 | 1 |
| 4 | Entrenamiento | 27 | 6,2 | 7 | 45 | 0 |
| 5 | Entrenamiento | 33 | 6,4 | 12 | 78 | 1 |
| 6 | Entrenamiento | 33 | 5,1 | 7 | 85 | 1 |
| 7 | Entrenamiento | 16 | 5,2 | 6 | 74 | 0 |
| 8 | Entrenamiento | 15 | 4,6 | 8 | 25 | 1 |
| 9 | Entrenamiento | 26 | 5,3 | 5 | 83 | 1 |
| 10 | Entrenamiento | 26 | 6,8 | 10 | 95 | 0 |
| 11 | Entrenamiento | 17 | 6,2 | 9 | 72 | 0 |
| 12 | Entrenamiento | 31 | 5,1 | 9 | 32 | 1 |
| 13 | Entrenamiento | 26 | 5,4 | 6 | 66 | 1 |
| 14 | Entrenamiento | 31 | 5,8 | 5 | 53 | 0 |
| 15 | Prueba | 26 | 6,1 | 6 | 69 | 0 |
| 16 | Prueba | 17 | 5,8 | 11 | 52 | 0 |
| 17 | Prueba | 31 | 5,9 | 6 | 39 | 1 |
| 18 | Prueba | 31 | 5,8 | 12 | 26 | 1 |
| 19 | Prueba | 22 | 4,8 | 7 | 41 | 1 |
| 20 | Prueba | 14 | 6,5 | 9 | 59 | 0 |

---

## M09 · ¿El tutor lo pasa al tema siguiente?

**Dominio:** Educacion-Tutor inteligente personalizado · **IA declarada:** ChatGPT

**Situación.** Un tutor inteligente personalizado decide cuándo un estudiante domina un tema y puede avanzar al siguiente. Cada caso es un estudiante al terminar un tema.

**Quién decide.** El tutor inteligente.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el estudiante aprueba la evaluación integradora del tema.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Avanzar a quien no domina el tema: se acumulan huecos que explotan en la evaluación.
- Falso negativo (dice NO y era SÍ): Retener a quien ya lo domina: se aburre y abandona la plataforma.

**Dato de contexto.** La plataforma muestra a los padres cuántos temas avanzó el chico por semana.

**Datos** (también en `datos/M09.csv`)

| Caso | Conjunto | Aciertos (% de los últimos 10 ejercicios) | Pistas pedidas (en el tema) | Tiempo por ejercicio (min) | Temas avanzados (en la semana) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 51 | 14 | 6,1 | 5 | 0 |
| 2 | Entrenamiento | 58 | 1 | 9,6 | 3 | 0 |
| 3 | Entrenamiento | 67 | 9 | 2,8 | 1 | 1 |
| 4 | Entrenamiento | 43 | 12 | 10,7 | 5 | 0 |
| 5 | Entrenamiento | 55 | 12 | 6,1 | 5 | 0 |
| 6 | Entrenamiento | 53 | 4 | 9,9 | 6 | 0 |
| 7 | Entrenamiento | 93 | 1 | 1,6 | 1 | 1 |
| 8 | Entrenamiento | 53 | 12 | 8,9 | 5 | 0 |
| 9 | Entrenamiento | 68 | 10 | 3,6 | 2 | 0 |
| 10 | Entrenamiento | 98 | 4 | 8,6 | 2 | 1 |
| 11 | Entrenamiento | 38 | 7 | 6,9 | 3 | 0 |
| 12 | Entrenamiento | 21 | 12 | 2,0 | 6 | 0 |
| 13 | Entrenamiento | 90 | 8 | 2,6 | 0 | 1 |
| 14 | Entrenamiento | 66 | 0 | 10,4 | 2 | 0 |
| 15 | Prueba | 94 | 5 | 2,6 | 0 | 1 |
| 16 | Prueba | 92 | 13 | 3,7 | 4 | 1 |
| 17 | Prueba | 78 | 2 | 5,3 | 3 | 1 |
| 18 | Prueba | 42 | 5 | 5,8 | 4 | 0 |
| 19 | Prueba | 67 | 3 | 8,3 | 1 | 0 |
| 20 | Prueba | 83 | 1 | 4,7 | 1 | 1 |

---

## M10 · ¿Este estudiante abandona primer año?

**Dominio:** education (casos de abandono estudiantil) · **IA declarada:** Claude

**Situación.** Una universidad quiere un sistema de alerta temprana para ofrecer tutorías a ingresantes en riesgo de abandonar. Cada caso es un estudiante al terminar el primer cuatrimestre.

**Quién decide.** La secretaría académica.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el estudiante abandona antes de terminar primer año.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Ofrecer tutoría a quien no iba a abandonar: un cupo de tutoría usado de más.
- Falso negativo (dice NO y era SÍ): No detectar a quien abandona: la universidad pierde al estudiante y él pierde el año.

**Datos** (también en `datos/M10.csv`)

| Caso | Conjunto | Asistencia (% del cuatrimestre) | Materias aprobadas (de 5) | Horas de trabajo (por semana) | Pidió constancia de baja (0 = no, 1 = sí) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 88 | 0 | 16 | 0 | 0 |
| 2 | Entrenamiento | 48 | 3 | 36 | 1 | 1 |
| 3 | Entrenamiento | 70 | 3 | 27 | 1 | 1 |
| 4 | Entrenamiento | 46 | 0 | 2 | 1 | 1 |
| 5 | Entrenamiento | 99 | 1 | 25 | 0 | 0 |
| 6 | Entrenamiento | 83 | 4 | 20 | 0 | 0 |
| 7 | Entrenamiento | 85 | 4 | 42 | 0 | 0 |
| 8 | Entrenamiento | 100 | 5 | 42 | 0 | 0 |
| 9 | Entrenamiento | 63 | 5 | 9 | 0 | 0 |
| 10 | Entrenamiento | 56 | 1 | 16 | 1 | 1 |
| 11 | Entrenamiento | 70 | 0 | 4 | 1 | 1 |
| 12 | Entrenamiento | 68 | 3 | 25 | 0 | 0 |
| 13 | Entrenamiento | 37 | 3 | 27 | 1 | 1 |
| 14 | Entrenamiento | 37 | 3 | 29 | 1 | 1 |
| 15 | Prueba | 76 | 2 | 24 | 0 | 0 |
| 16 | Prueba | 94 | 4 | 9 | 0 | 0 |
| 17 | Prueba | 47 | 3 | 24 | 1 | 1 |
| 18 | Prueba | 37 | 4 | 2 | 0 | 0 |
| 19 | Prueba | 72 | 1 | 10 | 1 | 1 |
| 20 | Prueba | 86 | 2 | 15 | 0 | 0 |

---

## M11 · ¿El 9 de Boca convierte en el partido?

**Dominio:** Vamos a elegir el área de futbol sobre el equipo Boca sobre analizar los datos de como se creo, el rendimientos de los jugadores, las estadisticas de los partidos, los resultados, etc · **IA declarada:** Chatgpt

**Situación.** El área de análisis de Boca quiere anticipar, antes de cada partido, si su centrodelantero titular va a convertir, para ajustar el plan de juego. Cada caso es un partido.

**Quién decide.** El área de análisis de rendimiento.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el centrodelantero convierte al menos un gol.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Armar el plan alrededor de un 9 que no convierte: el equipo carga todo por un solo lado.
- Falso negativo (dice NO y era SÍ): No aprovechar un partido en el que el 9 estaba para convertir.

**Dato de contexto.** Los programas deportivos miden al 9 por la cantidad de remates.

**Datos** (también en `datos/M11.csv`)

| Caso | Conjunto | Goles recibidos por el rival (promedio por partido) | Pases al área recibidos (promedio últimos 5 partidos) | Local (0 = visitante, 1 = Bombonera) | Remates totales (en el partido anterior) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 2,1 | 12 | 1 | 0 | 1 |
| 2 | Entrenamiento | 0,9 | 12 | 1 | 7 | 0 |
| 3 | Entrenamiento | 1,8 | 11 | 0 | 6 | 1 |
| 4 | Entrenamiento | 1,7 | 12 | 1 | 0 | 1 |
| 5 | Entrenamiento | 0,7 | 8 | 0 | 8 | 0 |
| 6 | Entrenamiento | 1,2 | 11 | 0 | 7 | 0 |
| 7 | Entrenamiento | 0,5 | 6 | 0 | 5 | 0 |
| 8 | Entrenamiento | 2,2 | 13 | 0 | 7 | 1 |
| 9 | Entrenamiento | 2,2 | 12 | 1 | 4 | 1 |
| 10 | Entrenamiento | 1,1 | 7 | 1 | 6 | 0 |
| 11 | Entrenamiento | 0,7 | 7 | 0 | 4 | 0 |
| 12 | Entrenamiento | 0,6 | 10 | 1 | 5 | 1 |
| 13 | Entrenamiento | 1,0 | 14 | 1 | 8 | 1 |
| 14 | Entrenamiento | 1,8 | 7 | 0 | 4 | 0 |
| 15 | Prueba | 1,9 | 11 | 1 | 3 | 1 |
| 16 | Prueba | 0,9 | 9 | 0 | 1 | 0 |
| 17 | Prueba | 0,7 | 5 | 0 | 9 | 0 |
| 18 | Prueba | 0,7 | 4 | 0 | 3 | 0 |
| 19 | Prueba | 2,2 | 10 | 0 | 1 | 1 |
| 20 | Prueba | 1,2 | 5 | 0 | 9 | 0 |

---

## M12 · ¿Este envío internacional llega tarde?

**Dominio:** El efecto mariposa en el tema de logistica · **IA declarada:** Gemini

**Situación.** Un operador logístico quiere anticipar qué envíos internacionales van a llegar tarde por demoras que se encadenan. Cada caso es un envío.

**Quién decide.** El área de operaciones.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el envío llega tarde al cliente final.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Avisar una demora que no ocurre: se paga un flete urgente de más.
- Falso negativo (dice NO y era SÍ): No anticipar una demora: el cliente se entera tarde y reclama la penalidad.

**Dato de contexto.** La gerencia mide el éxito por el % de envíos que salen a tiempo del depósito.

**Datos** (también en `datos/M12.csv`)

| Caso | Conjunto | Escalas (cantidad de transbordos) | Días de holgura (entre fecha prometida y estimada) | Congestión portuaria (índice 0 a 10) | Despachado a tiempo del depósito (0 = no, 1 = sí) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 1 | 9 | 4 | 0 | 0 |
| 2 | Entrenamiento | 2 | 8 | 2 | 1 | 0 |
| 3 | Entrenamiento | 3 | 9 | 8 | 1 | 0 |
| 4 | Entrenamiento | 2 | 6 | 9 | 0 | 0 |
| 5 | Entrenamiento | 4 | 7 | 5 | 0 | 1 |
| 6 | Entrenamiento | 4 | 10 | 8 | 1 | 1 |
| 7 | Entrenamiento | 1 | 3 | 2 | 1 | 0 |
| 8 | Entrenamiento | 5 | 4 | 1 | 1 | 1 |
| 9 | Entrenamiento | 1 | 2 | 9 | 1 | 1 |
| 10 | Entrenamiento | 3 | 5 | 7 | 1 | 0 |
| 11 | Entrenamiento | 3 | 6 | 9 | 1 | 1 |
| 12 | Entrenamiento | 3 | 1 | 8 | 1 | 1 |
| 13 | Entrenamiento | 3 | 2 | 6 | 0 | 1 |
| 14 | Entrenamiento | 2 | 5 | 5 | 0 | 0 |
| 15 | Prueba | 3 | 3 | 5 | 0 | 1 |
| 16 | Prueba | 3 | 9 | 6 | 1 | 0 |
| 17 | Prueba | 4 | 2 | 1 | 0 | 1 |
| 18 | Prueba | 2 | 10 | 1 | 1 | 0 |
| 19 | Prueba | 2 | 6 | 3 | 1 | 0 |
| 20 | Prueba | 5 | 1 | 9 | 1 | 1 |

---

## M13 · ¿El NPC ataca o se retira?

**Dominio:** Comportamiento de los NPC en los videojuegos · **IA declarada:** Claude

**Situación.** En un juego de acción, un NPC enemigo decide en cada encuentro si ataca al jugador o se retira a pedir refuerzos. Cada caso es un encuentro.

**Quién decide.** La IA del NPC.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = si el NPC ataca, gana el enfrentamiento.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): El NPC ataca y pierde: una pelea más corta, el jugador gana un poco antes.
- Falso negativo (dice NO y era SÍ): El NPC se retira cuando ganaba: el jugador nunca siente peligro. En las pruebas de juego es la queja número uno y la principal causa de reseñas negativas.

**Datos** (también en `datos/M13.csv`)

| Caso | Conjunto | Vida del NPC (%) | Vida del jugador (%) | Distancia (metros) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 75 | 18 | 19 | 1 |
| 2 | Entrenamiento | 50 | 68 | 6 | 0 |
| 3 | Entrenamiento | 59 | 20 | 1 | 1 |
| 4 | Entrenamiento | 85 | 29 | 5 | 1 |
| 5 | Entrenamiento | 51 | 69 | 1 | 0 |
| 6 | Entrenamiento | 13 | 15 | 13 | 1 |
| 7 | Entrenamiento | 64 | 45 | 28 | 0 |
| 8 | Entrenamiento | 86 | 8 | 14 | 1 |
| 9 | Entrenamiento | 52 | 76 | 18 | 0 |
| 10 | Entrenamiento | 43 | 77 | 26 | 0 |
| 11 | Entrenamiento | 45 | 98 | 30 | 0 |
| 12 | Entrenamiento | 99 | 90 | 14 | 0 |
| 13 | Entrenamiento | 15 | 33 | 25 | 0 |
| 14 | Entrenamiento | 32 | 59 | 7 | 0 |
| 15 | Prueba | 41 | 66 | 3 | 0 |
| 16 | Prueba | 53 | 63 | 1 | 1 |
| 17 | Prueba | 20 | 20 | 19 | 0 |
| 18 | Prueba | 54 | 8 | 12 | 1 |
| 19 | Prueba | 37 | 29 | 14 | 1 |
| 20 | Prueba | 22 | 13 | 13 | 1 |

---

## M14 · ¿El agente de atención escala a un humano?

**Dominio:** Agentes de IA · **IA declarada:** Gemini

**Situación.** Una empresa atiende consultas con un agente de IA. En cada conversación el agente decide si sigue solo o deriva a un operador humano. Cada caso es una conversación.

**Quién decide.** El agente de atención.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la conversación necesita un humano para resolverse.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Escalar algo que el agente resolvía: un operador ocupado de más.
- Falso negativo (dice NO y era SÍ): No escalar a un cliente que lo necesitaba: queja pública y cliente perdido.

**Datos** (también en `datos/M14.csv`)

| Caso | Conjunto | Intentos fallidos (respuestas que no resolvieron) | Tono del cliente (−1 (furioso) a 1 (cordial)) | Monto en disputa (USD) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 5 | 0,8 | 7 | 0 |
| 2 | Entrenamiento | 2 | -0,49 | 876 | 0 |
| 3 | Entrenamiento | 6 | -0,33 | 1538 | 1 |
| 4 | Entrenamiento | 2 | 0,28 | 1194 | 0 |
| 5 | Entrenamiento | 6 | 0,22 | 911 | 1 |
| 6 | Entrenamiento | 5 | -0,77 | 1489 | 1 |
| 7 | Entrenamiento | 5 | -0,65 | 685 | 1 |
| 8 | Entrenamiento | 5 | 0,69 | 1057 | 0 |
| 9 | Entrenamiento | 2 | -0,8 | 115 | 0 |
| 10 | Entrenamiento | 3 | -0,89 | 196 | 1 |
| 11 | Entrenamiento | 3 | 0,68 | 1827 | 1 |
| 12 | Entrenamiento | 5 | 0,27 | 1540 | 1 |
| 13 | Entrenamiento | 1 | -0,18 | 1555 | 0 |
| 14 | Entrenamiento | 5 | 0,49 | 1918 | 1 |
| 15 | Prueba | 3 | -0,32 | 1664 | 1 |
| 16 | Prueba | 1 | 0,52 | 179 | 0 |
| 17 | Prueba | 1 | -0,61 | 1555 | 0 |
| 18 | Prueba | 4 | 0,63 | 713 | 0 |
| 19 | Prueba | 3 | 0,28 | 1737 | 1 |
| 20 | Prueba | 3 | 0,77 | 1175 | 0 |

---

## M15 · ¿Este jugador vuelve la semana que viene?

**Dominio:** Videojuegos y entretenimiento · **IA declarada:** Gemini

**Situación.** Un estudio de videojuegos quiere detectar a los jugadores que están por dejar su juego para ofrecerles contenido nuevo. Cada caso es un jugador en una semana.

**Quién decide.** El equipo de live ops del estudio.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el jugador NO vuelve a jugar la semana siguiente.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Regalarle contenido a quien iba a volver igual: se regala algo que se podía vender.
- Falso negativo (dice NO y era SÍ): No detectar a quien se va: se pierde un jugador.

**Dato de contexto.** El estudio mide el éxito por minutos jugados totales.

**Datos** (también en `datos/M15.csv`)

| Caso | Conjunto | Sesiones (en la semana) | Días trabado (sin avanzar de nivel) | Amigos activos (en su lista) | Minutos jugados (en la semana) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 2 | 7 | 1 | 258 | 1 |
| 2 | Entrenamiento | 7 | 9 | 2 | 686 | 0 |
| 3 | Entrenamiento | 6 | 4 | 7 | 767 | 0 |
| 4 | Entrenamiento | 10 | 0 | 2 | 548 | 0 |
| 5 | Entrenamiento | 1 | 14 | 0 | 9 | 1 |
| 6 | Entrenamiento | 13 | 2 | 3 | 247 | 0 |
| 7 | Entrenamiento | 5 | 9 | 2 | 735 | 1 |
| 8 | Entrenamiento | 1 | 10 | 4 | 0 | 1 |
| 9 | Entrenamiento | 6 | 6 | 6 | 538 | 0 |
| 10 | Entrenamiento | 9 | 11 | 4 | 676 | 0 |
| 11 | Entrenamiento | 7 | 11 | 5 | 727 | 1 |
| 12 | Entrenamiento | 7 | 3 | 3 | 433 | 0 |
| 13 | Entrenamiento | 2 | 7 | 7 | 209 | 1 |
| 14 | Entrenamiento | 12 | 8 | 3 | 295 | 0 |
| 15 | Prueba | 5 | 13 | 6 | 419 | 1 |
| 16 | Prueba | 13 | 12 | 7 | 240 | 0 |
| 17 | Prueba | 4 | 1 | 8 | 900 | 0 |
| 18 | Prueba | 11 | 2 | 6 | 403 | 0 |
| 19 | Prueba | 6 | 13 | 3 | 125 | 1 |
| 20 | Prueba | 0 | 5 | 9 | 217 | 0 |

---

## M16 · ¿Sembramos maíz esta semana?

**Dominio:** agronomia(suelos y climatologia) · **IA declarada:** claude

**Situación.** Un productor decide en qué semana sembrar maíz según el suelo y el pronóstico. Cada caso es un lote en una semana posible de siembra.

**Quién decide.** El asesor agronómico.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la siembra logra una buena implantación.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Sembrar con malas condiciones: hay que resembrar o el lote rinde menos.
- Falso negativo (dice NO y era SÍ): Esperar cuando se podía sembrar: se acorta el ciclo del cultivo.

**Datos** (también en `datos/M16.csv`)

| Caso | Conjunto | Temperatura de suelo a 5 cm (°C) | Humedad de suelo (% de capacidad de campo) | Lluvia pronosticada (mm en 7 días) | Plantas logradas a los 20 días (plantas por m²) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 7,8 | 77 | 18 | 3,8 | 0 |
| 2 | Entrenamiento | 14,4 | 55 | 60 | 7,1 | 1 |
| 3 | Entrenamiento | 21,4 | 70 | 0 | 7,4 | 1 |
| 4 | Entrenamiento | 13,0 | 67 | 54 | 4,2 | 0 |
| 5 | Entrenamiento | 13,1 | 69 | 27 | 5,6 | 0 |
| 6 | Entrenamiento | 19,5 | 72 | 35 | 8,0 | 1 |
| 7 | Entrenamiento | 8,9 | 63 | 57 | 5,4 | 0 |
| 8 | Entrenamiento | 21,5 | 89 | 41 | 7,8 | 1 |
| 9 | Entrenamiento | 21,9 | 61 | 14 | 7,7 | 1 |
| 10 | Entrenamiento | 11,4 | 62 | 36 | 5,7 | 0 |
| 11 | Entrenamiento | 10,0 | 76 | 15 | 4,1 | 0 |
| 12 | Entrenamiento | 9,3 | 36 | 16 | 4,9 | 0 |
| 13 | Entrenamiento | 20,1 | 31 | 30 | 7,9 | 1 |
| 14 | Entrenamiento | 10,7 | 77 | 19 | 4,0 | 0 |
| 15 | Prueba | 15,1 | 81 | 28 | 8,0 | 1 |
| 16 | Prueba | 13,5 | 58 | 58 | 5,4 | 0 |
| 17 | Prueba | 19,9 | 77 | 13 | 8,2 | 1 |
| 18 | Prueba | 21,3 | 80 | 18 | 7,7 | 1 |
| 19 | Prueba | 8,1 | 77 | 55 | 3,6 | 0 |
| 20 | Prueba | 14,9 | 37 | 42 | 4,0 | 0 |

---

## M17 · ¿Entra el triple sobre la chicharra?

**Dominio:** Basquet · **IA declarada:** ChatGPT

**Situación.** Un cuerpo técnico de básquet analiza las últimas posesiones para decidir quién y desde dónde tira el triple final. Cada caso es un tiro sobre la chicharra.

**Quién decide.** El entrenador, al diseñar la jugada final.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el triple entra.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Diseñar la jugada para un tiro que no entra: se pierde el partido.
- Falso negativo (dice NO y era SÍ): Descartar al tirador que la metía: se elige una opción peor.

**Datos** (también en `datos/M17.csv`)

| Caso | Conjunto | Distancia del tiro (m) | Defensor más cercano (m) | Efectividad del tirador (% en triples en la temporada) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 7,38 | 1,7 | 32 | 0 |
| 2 | Entrenamiento | 7,0 | 0,9 | 29 | 0 |
| 3 | Entrenamiento | 7,24 | 2,4 | 31 | 0 |
| 4 | Entrenamiento | 9,47 | 1,3 | 37 | 0 |
| 5 | Entrenamiento | 7,64 | 1,9 | 26 | 0 |
| 6 | Entrenamiento | 8,69 | 0,9 | 33 | 0 |
| 7 | Entrenamiento | 6,95 | 1,9 | 27 | 0 |
| 8 | Entrenamiento | 7,64 | 2,9 | 26 | 0 |
| 9 | Entrenamiento | 8,51 | 0,8 | 30 | 0 |
| 10 | Entrenamiento | 8,06 | 2,9 | 43 | 1 |
| 11 | Entrenamiento | 7,72 | 2,3 | 43 | 1 |
| 12 | Entrenamiento | 9,45 | 0,5 | 33 | 0 |
| 13 | Entrenamiento | 7,13 | 0,7 | 41 | 0 |
| 14 | Entrenamiento | 9,14 | 1,7 | 42 | 0 |
| 15 | Prueba | 8,87 | 2,9 | 28 | 0 |
| 16 | Prueba | 8,97 | 0,9 | 35 | 0 |
| 17 | Prueba | 6,94 | 0,6 | 39 | 0 |
| 18 | Prueba | 6,76 | 1,7 | 44 | 1 |
| 19 | Prueba | 7,19 | 2,6 | 28 | 0 |
| 20 | Prueba | 7,05 | 1,1 | 33 | 0 |

---

## M18 · ¿Este nadador llega a la final?

**Dominio:** Deportes · **IA declarada:** ChatGPT

**Situación.** Una federación decide a qué nadadores juveniles financiarles el viaje al Sudamericano según sus chances de entrar a la final. Cada caso es un nadador.

**Quién decide.** La comisión técnica de la federación.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el nadador entra a la final de su prueba.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Financiar a quien no llega a la final: se gasta un pasaje.
- Falso negativo (dice NO y era SÍ): No llevar a quien llegaba: el país pierde un finalista.

**Datos** (también en `datos/M18.csv`)

| Caso | Conjunto | Distancia a la marca de corte (segundos (negativo = mejor que el corte)) | Sesiones de entrenamiento (por semana) | Edad (años) | Puesto en la semifinal (puesto (1 a 16)) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 1,32 | 9 | 16 | 6 | 1 |
| 2 | Entrenamiento | -0,02 | 10 | 19 | 7 | 1 |
| 3 | Entrenamiento | -0,59 | 7 | 16 | 8 | 1 |
| 4 | Entrenamiento | -0,06 | 9 | 15 | 6 | 1 |
| 5 | Entrenamiento | 2,31 | 5 | 15 | 13 | 0 |
| 6 | Entrenamiento | -1,15 | 10 | 18 | 7 | 1 |
| 7 | Entrenamiento | 1,22 | 8 | 17 | 12 | 0 |
| 8 | Entrenamiento | 1,03 | 7 | 17 | 13 | 0 |
| 9 | Entrenamiento | 1,41 | 6 | 14 | 14 | 0 |
| 10 | Entrenamiento | 2,06 | 8 | 18 | 13 | 0 |
| 11 | Entrenamiento | 1,96 | 11 | 19 | 1 | 1 |
| 12 | Entrenamiento | 0,29 | 11 | 18 | 1 | 1 |
| 13 | Entrenamiento | -0,11 | 5 | 14 | 13 | 0 |
| 14 | Entrenamiento | 1,16 | 6 | 18 | 15 | 0 |
| 15 | Prueba | 0,82 | 7 | 16 | 13 | 0 |
| 16 | Prueba | 1,45 | 8 | 18 | 7 | 1 |
| 17 | Prueba | -1,27 | 6 | 14 | 8 | 1 |
| 18 | Prueba | 2,25 | 8 | 17 | 11 | 0 |
| 19 | Prueba | 0,74 | 6 | 15 | 10 | 0 |
| 20 | Prueba | 1,79 | 10 | 18 | 12 | 0 |

---

## M19 · ¿Esta selección pasa la fase de grupos?

**Dominio:** deportes, selecciones nacionales de fútbol (FIFA), · **IA declarada:** Claude

**Situación.** Un analista estima, antes del Mundial, qué selecciones superan la fase de grupos. Cada caso es una selección.

**Quién decide.** El analista de la federación.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la selección pasa la fase de grupos.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Apostar a que pasa una selección que queda afuera.
- Falso negativo (dice NO y era SÍ): Subestimar a una selección que pasa.

**Dato de contexto.** La federación evalúa al técnico por la cantidad de amistosos ganados.

**Datos** (también en `datos/M19.csv`)

| Caso | Conjunto | Ranking FIFA (puesto) | Goles a favor en eliminatorias (por partido) | Jugadores en ligas top (de 26) | Amistosos ganados (en el año) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 74 | 2,1 | 25 | 2 | 1 |
| 2 | Entrenamiento | 64 | 0,7 | 23 | 4 | 0 |
| 3 | Entrenamiento | 65 | 1,2 | 21 | 3 | 0 |
| 4 | Entrenamiento | 13 | 1,1 | 23 | 7 | 1 |
| 5 | Entrenamiento | 49 | 1,4 | 8 | 2 | 0 |
| 6 | Entrenamiento | 47 | 1,0 | 3 | 8 | 0 |
| 7 | Entrenamiento | 57 | 0,6 | 19 | 6 | 0 |
| 8 | Entrenamiento | 57 | 1,2 | 23 | 2 | 1 |
| 9 | Entrenamiento | 44 | 1,3 | 8 | 7 | 0 |
| 10 | Entrenamiento | 7 | 2,4 | 12 | 1 | 1 |
| 11 | Entrenamiento | 40 | 0,7 | 20 | 8 | 0 |
| 12 | Entrenamiento | 44 | 1,8 | 2 | 5 | 0 |
| 13 | Entrenamiento | 55 | 2,0 | 23 | 8 | 0 |
| 14 | Entrenamiento | 15 | 2,2 | 24 | 2 | 1 |
| 15 | Prueba | 56 | 2,5 | 25 | 4 | 1 |
| 16 | Prueba | 32 | 2,0 | 3 | 4 | 0 |
| 17 | Prueba | 6 | 1,0 | 23 | 0 | 1 |
| 18 | Prueba | 48 | 0,6 | 11 | 5 | 0 |
| 19 | Prueba | 7 | 2,1 | 6 | 6 | 1 |
| 20 | Prueba | 23 | 0,6 | 8 | 8 | 0 |

---

## M20 · ¿Este jugador hace trampa?

**Dominio:** Seguridad e integridad en videojuegos mediante IA · **IA declarada:** Claude

**Situación.** Un shooter competitivo quiere detectar a quienes usan aimbot para mandarlos a revisión manual. Cada caso es una cuenta en una semana.

**Quién decide.** El sistema anti-trampas.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la cuenta usa trampas.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Mandar a revisión a un jugador honesto muy bueno: si lo banean, es un escándalo en redes.
- Falso negativo (dice NO y era SÍ): Dejar pasar a un tramposo: arruina partidas y la comunidad abandona el juego.

**Datos** (también en `datos/M20.csv`)

| Caso | Conjunto | Disparos a la cabeza (% de los impactos) | Tiempo de reacción (ms) | Horas en la cuenta (h totales) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 58 | 398 | 1960 | 0 |
| 2 | Entrenamiento | 20 | 125 | 772 | 0 |
| 3 | Entrenamiento | 18 | 355 | 1777 | 0 |
| 4 | Entrenamiento | 79 | 311 | 607 | 0 |
| 5 | Entrenamiento | 64 | 329 | 1358 | 0 |
| 6 | Entrenamiento | 61 | 282 | 1849 | 0 |
| 7 | Entrenamiento | 83 | 123 | 1988 | 0 |
| 8 | Entrenamiento | 36 | 123 | 1159 | 0 |
| 9 | Entrenamiento | 33 | 150 | 1398 | 0 |
| 10 | Entrenamiento | 88 | 160 | 254 | 1 |
| 11 | Entrenamiento | 79 | 328 | 1690 | 0 |
| 12 | Entrenamiento | 12 | 320 | 768 | 0 |
| 13 | Entrenamiento | 66 | 315 | 715 | 0 |
| 14 | Entrenamiento | 82 | 157 | 172 | 1 |
| 15 | Prueba | 75 | 292 | 1993 | 0 |
| 16 | Prueba | 64 | 374 | 1914 | 0 |
| 17 | Prueba | 51 | 393 | 1772 | 0 |
| 18 | Prueba | 74 | 92 | 467 | 1 |
| 19 | Prueba | 10 | 298 | 950 | 0 |
| 20 | Prueba | 48 | 366 | 1991 | 0 |

---

## M21 · ¿Emitimos alerta de incendio forestal hoy?

**Dominio:** medio ambiente · **IA declarada:** gemini

**Situación.** Un servicio de manejo del fuego decide cada mañana si emite alerta roja de incendio en una zona serrana. Cada caso es un día en una zona.

**Quién decide.** El servicio de manejo del fuego.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = ese día se inicia un incendio que se propaga.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Alerta sin incendio: brigadas movilizadas de más y actividades suspendidas.
- Falso negativo (dice NO y era SÍ): No alertar y que haya incendio: hectáreas quemadas, fauna perdida y riesgo para viviendas.

**Datos** (también en `datos/M21.csv`)

| Caso | Conjunto | Humedad relativa (%) | Viento (km/h) | Días sin lluvia (días) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 59 | 42 | 26 | 0 |
| 2 | Entrenamiento | 16 | 31 | 3 | 1 |
| 3 | Entrenamiento | 65 | 38 | 23 | 0 |
| 4 | Entrenamiento | 68 | 13 | 32 | 0 |
| 5 | Entrenamiento | 42 | 20 | 34 | 0 |
| 6 | Entrenamiento | 68 | 5 | 18 | 0 |
| 7 | Entrenamiento | 26 | 60 | 10 | 1 |
| 8 | Entrenamiento | 77 | 14 | 23 | 0 |
| 9 | Entrenamiento | 45 | 40 | 21 | 0 |
| 10 | Entrenamiento | 75 | 53 | 44 | 1 |
| 11 | Entrenamiento | 27 | 6 | 23 | 0 |
| 12 | Entrenamiento | 65 | 44 | 43 | 1 |
| 13 | Entrenamiento | 13 | 32 | 28 | 1 |
| 14 | Entrenamiento | 21 | 48 | 32 | 1 |
| 15 | Prueba | 37 | 23 | 6 | 0 |
| 16 | Prueba | 24 | 24 | 21 | 0 |
| 17 | Prueba | 75 | 16 | 26 | 0 |
| 18 | Prueba | 57 | 47 | 26 | 1 |
| 19 | Prueba | 29 | 7 | 42 | 1 |
| 20 | Prueba | 59 | 57 | 44 | 1 |

---

## M22 · ¿Convierte el penal?

**Dominio:** Futbol · **IA declarada:** Gemini

**Situación.** Un entrenador tiene que elegir el orden de los pateadores para una definición por penales. Cada caso es un penal de un pateador del plantel.

**Quién decide.** El entrenador.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el penal se convierte.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Confiar en un penal que se erra.
- Falso negativo (dice NO y era SÍ): Sacar de la lista a quien lo metía.

**Datos** (también en `datos/M22.csv`)

| Caso | Conjunto | Efectividad histórica (% de penales convertidos) | Minutos jugados en el partido (min) | Penales pateados en su carrera (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 92 | 98 | 23 | 1 |
| 2 | Entrenamiento | 63 | 43 | 13 | 0 |
| 3 | Entrenamiento | 71 | 105 | 30 | 1 |
| 4 | Entrenamiento | 66 | 71 | 31 | 1 |
| 5 | Entrenamiento | 75 | 65 | 28 | 1 |
| 6 | Entrenamiento | 84 | 114 | 37 | 1 |
| 7 | Entrenamiento | 56 | 106 | 25 | 0 |
| 8 | Entrenamiento | 93 | 60 | 38 | 1 |
| 9 | Entrenamiento | 92 | 21 | 24 | 1 |
| 10 | Entrenamiento | 78 | 34 | 3 | 1 |
| 11 | Entrenamiento | 87 | 105 | 19 | 1 |
| 12 | Entrenamiento | 84 | 88 | 35 | 1 |
| 13 | Entrenamiento | 69 | 57 | 24 | 1 |
| 14 | Entrenamiento | 89 | 104 | 4 | 1 |
| 15 | Prueba | 81 | 10 | 2 | 1 |
| 16 | Prueba | 94 | 89 | 8 | 1 |
| 17 | Prueba | 83 | 11 | 17 | 1 |
| 18 | Prueba | 87 | 104 | 39 | 1 |
| 19 | Prueba | 86 | 90 | 27 | 1 |
| 20 | Prueba | 65 | 37 | 14 | 0 |

---

## M23 · ¿Le ofrecemos contrato profesional?

**Dominio:** Deporte · **IA declarada:** Claude

**Situación.** Un club decide a qué juveniles de reserva ofrecerles el primer contrato profesional. Cada caso es un juvenil.

**Quién decide.** La secretaría técnica del club.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el juvenil se consolida en Primera en los dos años siguientes.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Firmar a quien no se consolida: un sueldo profesional sin retorno.
- Falso negativo (dice NO y era SÍ): No firmar a quien después triunfa en otro club: se va libre.

**Datos** (también en `datos/M23.csv`)

| Caso | Conjunto | Minutos en reserva (en la temporada) | Goles + asistencias (cada 90 minutos) | Edad (años) | Partidos en Primera al año siguiente (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 1288 | 0,96 | 19 | 25 | 1 |
| 2 | Entrenamiento | 323 | 0,45 | 18 | 0 | 0 |
| 3 | Entrenamiento | 905 | 0,68 | 20 | 4 | 0 |
| 4 | Entrenamiento | 2044 | 0,78 | 17 | 25 | 1 |
| 5 | Entrenamiento | 2155 | 0,4 | 18 | 30 | 1 |
| 6 | Entrenamiento | 1959 | 0,58 | 19 | 22 | 1 |
| 7 | Entrenamiento | 988 | 0,18 | 17 | 4 | 0 |
| 8 | Entrenamiento | 1136 | 0,08 | 21 | 1 | 0 |
| 9 | Entrenamiento | 821 | 0,51 | 17 | 3 | 0 |
| 10 | Entrenamiento | 482 | 0,17 | 21 | 4 | 0 |
| 11 | Entrenamiento | 1724 | 0,59 | 20 | 24 | 1 |
| 12 | Entrenamiento | 617 | 0,13 | 21 | 2 | 0 |
| 13 | Entrenamiento | 1308 | 0,38 | 18 | 1 | 0 |
| 14 | Entrenamiento | 1159 | 0,97 | 20 | 17 | 1 |
| 15 | Prueba | 2196 | 0,92 | 21 | 17 | 1 |
| 16 | Prueba | 1722 | 0,09 | 19 | 5 | 0 |
| 17 | Prueba | 2506 | 0,43 | 18 | 14 | 1 |
| 18 | Prueba | 480 | 0,74 | 18 | 27 | 1 |
| 19 | Prueba | 1002 | 0,87 | 17 | 15 | 1 |
| 20 | Prueba | 1451 | 0,37 | 17 | 2 | 0 |

---

## M24 · ¿Este atleta está sobreentrenado?

**Dominio:** La evolución del entrenamiento deportivo · **IA declarada:** Claude pro

**Situación.** Un preparador físico decide cada semana si baja la carga de un atleta para evitar el sobreentrenamiento. Cada caso es un atleta en una semana.

**Quién decide.** El preparador físico.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el atleta rinde peor en el test de la semana siguiente.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Bajar la carga a quien la toleraba: se pierde una semana de estímulo.
- Falso negativo (dice NO y era SÍ): Seguir cargando a quien estaba sobreentrenado: cae el rendimiento y aparecen lesiones.

**Dato de contexto.** El club evalúa al preparador por la carga semanal acumulada.

**Datos** (también en `datos/M24.csv`)

| Caso | Conjunto | Variabilidad de frecuencia cardíaca (ms) | Esfuerzo percibido (1 a 10) | Horas de sueño (promedio por noche) | Carga semanal (unidades arbitrarias) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 31 | 8 | 8,2 | 1491 | 1 |
| 2 | Entrenamiento | 88 | 5 | 8,5 | 2175 | 0 |
| 3 | Entrenamiento | 98 | 8 | 5,6 | 3042 | 0 |
| 4 | Entrenamiento | 50 | 6 | 7,2 | 3659 | 1 |
| 5 | Entrenamiento | 91 | 8 | 8,6 | 3940 | 0 |
| 6 | Entrenamiento | 78 | 6 | 8,0 | 4192 | 0 |
| 7 | Entrenamiento | 106 | 8 | 5,0 | 1482 | 1 |
| 8 | Entrenamiento | 53 | 8 | 5,7 | 2751 | 1 |
| 9 | Entrenamiento | 82 | 8 | 8,1 | 3081 | 1 |
| 10 | Entrenamiento | 80 | 6 | 7,6 | 1501 | 0 |
| 11 | Entrenamiento | 20 | 9 | 7,4 | 3995 | 1 |
| 12 | Entrenamiento | 47 | 7 | 6,5 | 4340 | 1 |
| 13 | Entrenamiento | 84 | 8 | 5,6 | 3039 | 1 |
| 14 | Entrenamiento | 32 | 10 | 7,0 | 1000 | 1 |
| 15 | Prueba | 26 | 5 | 7,3 | 1000 | 1 |
| 16 | Prueba | 50 | 2 | 8,2 | 1859 | 0 |
| 17 | Prueba | 101 | 3 | 6,5 | 2347 | 0 |
| 18 | Prueba | 91 | 5 | 5,6 | 4464 | 0 |
| 19 | Prueba | 69 | 3 | 6,8 | 2498 | 0 |
| 20 | Prueba | 98 | 6 | 5,3 | 1063 | 1 |

---

## M25 · ¿Esta canción entra al Top 50?

**Dominio:** Musica · **IA declarada:** Gemini

**Situación.** Un sello discográfico decide en qué lanzamientos invertir promoción paga, según sus chances de entrar al Top 50 de una plataforma en el primer mes. Cada caso es una canción.

**Quién decide.** El área de marketing del sello.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la canción entra al Top 50 en su primer mes.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Invertir promoción en una canción que no entra: presupuesto perdido.
- Falso negativo (dice NO y era SÍ): No promocionar un hit: la canción crece sola, pero el sello deja de ganar.

**Datos** (también en `datos/M25.csv`)

| Caso | Conjunto | Seguidores del artista (miles) | Playlists editoriales (en las que entra la primera semana) | Colaboración con otro artista (0 = no, 1 = sí) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 1208 | 6 | 1 | 0 |
| 2 | Entrenamiento | 2367 | 6 | 0 | 0 |
| 3 | Entrenamiento | 2205 | 12 | 1 | 1 |
| 4 | Entrenamiento | 345 | 2 | 1 | 0 |
| 5 | Entrenamiento | 253 | 0 | 1 | 0 |
| 6 | Entrenamiento | 916 | 10 | 1 | 0 |
| 7 | Entrenamiento | 483 | 3 | 0 | 0 |
| 8 | Entrenamiento | 2696 | 10 | 0 | 0 |
| 9 | Entrenamiento | 728 | 12 | 0 | 0 |
| 10 | Entrenamiento | 1773 | 12 | 1 | 1 |
| 11 | Entrenamiento | 461 | 12 | 1 | 0 |
| 12 | Entrenamiento | 2126 | 3 | 1 | 0 |
| 13 | Entrenamiento | 1431 | 9 | 0 | 0 |
| 14 | Entrenamiento | 2926 | 9 | 0 | 0 |
| 15 | Prueba | 933 | 9 | 0 | 0 |
| 16 | Prueba | 860 | 12 | 0 | 0 |
| 17 | Prueba | 1445 | 6 | 0 | 0 |
| 18 | Prueba | 1939 | 2 | 1 | 0 |
| 19 | Prueba | 2769 | 11 | 0 | 1 |
| 20 | Prueba | 2965 | 1 | 1 | 0 |

---

## M26 · ¿Ocultamos este comentario del chat?

**Dominio:** Entretenimiento digital · **IA declarada:** Claude

**Situación.** Una plataforma de streaming en vivo modera el chat de transmisiones con audiencia adolescente. Cada caso es un mensaje.

**Quién decide.** El moderador automático.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el mensaje es acoso o discurso de odio.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Ocultar un mensaje legítimo: un usuario se siente censurado.
- Falso negativo (dice NO y era SÍ): Dejar pasar acoso: daño a quien lo recibe, más grave con menores en la audiencia.

**Datos** (también en `datos/M26.csv`)

| Caso | Conjunto | Términos ofensivos (detectados en el mensaje) | Mensajes del autor (en el último minuto) | Antigüedad de la cuenta (días) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 4 | 9 | 422 | 1 |
| 2 | Entrenamiento | 2 | 5 | 129 | 0 |
| 3 | Entrenamiento | 1 | 11 | 637 | 0 |
| 4 | Entrenamiento | 4 | 14 | 824 | 1 |
| 5 | Entrenamiento | 1 | 3 | 794 | 0 |
| 6 | Entrenamiento | 3 | 12 | 654 | 1 |
| 7 | Entrenamiento | 1 | 8 | 90 | 0 |
| 8 | Entrenamiento | 0 | 16 | 634 | 0 |
| 9 | Entrenamiento | 6 | 10 | 471 | 1 |
| 10 | Entrenamiento | 5 | 13 | 38 | 1 |
| 11 | Entrenamiento | 1 | 17 | 379 | 0 |
| 12 | Entrenamiento | 3 | 2 | 745 | 0 |
| 13 | Entrenamiento | 4 | 3 | 512 | 1 |
| 14 | Entrenamiento | 4 | 7 | 164 | 1 |
| 15 | Prueba | 5 | 16 | 613 | 1 |
| 16 | Prueba | 5 | 3 | 626 | 1 |
| 17 | Prueba | 4 | 17 | 461 | 1 |
| 18 | Prueba | 5 | 20 | 513 | 1 |
| 19 | Prueba | 2 | 6 | 333 | 0 |
| 20 | Prueba | 1 | 4 | 559 | 0 |

---

## M27 · ¿Tomografía urgente por sospecha de ACV?

**Dominio:** Neurología - Salud · **IA declarada:** ChatGPT

**Situación.** En la guardia, un sistema de triage decide a qué pacientes mandar a tomografía urgente por sospecha de ACV. Cada caso es un paciente (datos inventados).

**Quién decide.** El sistema de triage, con validación médica.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el paciente está cursando un ACV.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Tomografía a quien no tenía ACV: un estudio de más y un tomógrafo ocupado.
- Falso negativo (dice NO y era SÍ): No detectar un ACV: se pierde la ventana de tratamiento y quedan secuelas.

**Datos** (también en `datos/M27.csv`)

| Caso | Conjunto | Asimetría facial (escala 0 a 3) | Debilidad en un brazo (escala 0 a 4) | Dificultad para hablar (escala 0 a 3) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 0 | 1 | 0 | 0 |
| 2 | Entrenamiento | 2 | 0 | 2 | 1 |
| 3 | Entrenamiento | 2 | 1 | 2 | 1 |
| 4 | Entrenamiento | 0 | 3 | 1 | 0 |
| 5 | Entrenamiento | 3 | 1 | 3 | 1 |
| 6 | Entrenamiento | 2 | 3 | 0 | 1 |
| 7 | Entrenamiento | 1 | 1 | 2 | 0 |
| 8 | Entrenamiento | 0 | 3 | 1 | 0 |
| 9 | Entrenamiento | 1 | 4 | 2 | 1 |
| 10 | Entrenamiento | 2 | 2 | 1 | 0 |
| 11 | Entrenamiento | 3 | 2 | 3 | 1 |
| 12 | Entrenamiento | 1 | 3 | 1 | 0 |
| 13 | Entrenamiento | 1 | 0 | 1 | 0 |
| 14 | Entrenamiento | 1 | 1 | 1 | 0 |
| 15 | Prueba | 1 | 0 | 2 | 0 |
| 16 | Prueba | 2 | 4 | 1 | 1 |
| 17 | Prueba | 2 | 3 | 2 | 1 |
| 18 | Prueba | 2 | 4 | 0 | 1 |
| 19 | Prueba | 1 | 1 | 2 | 0 |
| 20 | Prueba | 3 | 0 | 2 | 1 |

---

## M28 · ¿Le damos el crédito a esta pyme?

**Dominio:** Negocios · **IA declarada:** Claude

**Situación.** Una fintech decide si otorga un crédito de capital de trabajo a pymes. Cada caso es una pyme que lo pide.

**Quién decide.** El comité de crédito de la fintech.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la pyme paga el crédito sin atrasos.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Prestarle a quien no paga: se pierde el capital.
- Falso negativo (dice NO y era SÍ): No prestarle a quien pagaba: se pierde un buen cliente.

**Datos** (también en `datos/M28.csv`)

| Caso | Conjunto | Meses facturando (meses) | Deuda sobre ingresos (relación) | Cheques rechazados (último año) | Días de atraso en la primera cuota (días) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 44 | 0,23 | 7 | 0 | 1 |
| 2 | Entrenamiento | 14 | 0,97 | 2 | 30 | 0 |
| 3 | Entrenamiento | 38 | 0,79 | 4 | 0 | 1 |
| 4 | Entrenamiento | 34 | 0,6 | 6 | 69 | 0 |
| 5 | Entrenamiento | 7 | 0,86 | 4 | 27 | 0 |
| 6 | Entrenamiento | 113 | 0,15 | 6 | 0 | 1 |
| 7 | Entrenamiento | 25 | 0,1 | 3 | 0 | 1 |
| 8 | Entrenamiento | 23 | 0,07 | 1 | 0 | 1 |
| 9 | Entrenamiento | 51 | 1,15 | 4 | 61 | 0 |
| 10 | Entrenamiento | 23 | 0,89 | 2 | 63 | 0 |
| 11 | Entrenamiento | 64 | 1,1 | 6 | 21 | 0 |
| 12 | Entrenamiento | 48 | 0,12 | 2 | 0 | 1 |
| 13 | Entrenamiento | 52 | 0,76 | 0 | 0 | 1 |
| 14 | Entrenamiento | 72 | 0,2 | 8 | 84 | 0 |
| 15 | Prueba | 22 | 1,3 | 4 | 69 | 0 |
| 16 | Prueba | 9 | 1,38 | 3 | 20 | 0 |
| 17 | Prueba | 51 | 1,3 | 8 | 38 | 0 |
| 18 | Prueba | 68 | 0,49 | 2 | 0 | 1 |
| 19 | Prueba | 54 | 0,26 | 6 | 0 | 1 |
| 20 | Prueba | 20 | 0,14 | 8 | 22 | 0 |

---

## M29 · ¿Le va a gustar esta recomendación?

**Dominio:** El tema que elegimos es recomendación y streaming · **IA declarada:** Claude

**Situación.** Una plataforma de streaming quiere predecir qué recomendaciones recibirán un «pulgar arriba». Cada caso es una recomendación mostrada a un usuario.

**Quién decide.** El recomendador.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el usuario le da pulgar arriba.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Mostrar con confianza algo que no le gusta: el usuario confía menos en las recomendaciones.
- Falso negativo (dice NO y era SÍ): Esconder algo que le iba a gustar.

**Datos** (también en `datos/M29.csv`)

| Caso | Conjunto | Coincidencia con su historial (0 a 1) | Popularidad del título (percentil) | Es estreno (0 = no, 1 = sí) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 0,22 | 34 | 0 | 0 |
| 2 | Entrenamiento | 0,45 | 26 | 0 | 0 |
| 3 | Entrenamiento | 0,99 | 85 | 1 | 1 |
| 4 | Entrenamiento | 0,48 | 58 | 1 | 0 |
| 5 | Entrenamiento | 0,73 | 68 | 0 | 0 |
| 6 | Entrenamiento | 0,67 | 47 | 1 | 0 |
| 7 | Entrenamiento | 0,13 | 93 | 0 | 0 |
| 8 | Entrenamiento | 0,63 | 49 | 1 | 0 |
| 9 | Entrenamiento | 0,93 | 36 | 1 | 1 |
| 10 | Entrenamiento | 0,69 | 89 | 0 | 0 |
| 11 | Entrenamiento | 0,41 | 5 | 1 | 0 |
| 12 | Entrenamiento | 0,45 | 62 | 0 | 0 |
| 13 | Entrenamiento | 0,01 | 2 | 1 | 0 |
| 14 | Entrenamiento | 0,47 | 23 | 1 | 0 |
| 15 | Prueba | 0,31 | 29 | 0 | 0 |
| 16 | Prueba | 0,78 | 98 | 0 | 1 |
| 17 | Prueba | 0,32 | 83 | 0 | 0 |
| 18 | Prueba | 0,12 | 11 | 0 | 0 |
| 19 | Prueba | 0,38 | 48 | 1 | 0 |
| 20 | Prueba | 0,11 | 16 | 0 | 0 |

---
