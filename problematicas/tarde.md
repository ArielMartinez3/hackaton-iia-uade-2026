# Problemáticas · Hackatón IIA · Comisión Tarde

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

## T01 · ¿Este inicio de sesión es una intrusión?

**Dominio:** Deteccion de amenazas en sistemas/software asistido por IA · **IA declarada:** Claude

**Situación.** Un sistema de seguridad revisa los inicios de sesión al servidor de una empresa para detectar accesos con credenciales robadas. Cada caso es un inicio de sesión.

**Quién decide.** El sistema de detección de intrusiones.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el inicio de sesión es una intrusión.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Bloquear a un empleado legítimo: horas de trabajo perdidas.
- Falso negativo (dice NO y era SÍ): Dejar pasar una intrusión: fuga de datos.

**Datos** (también en `datos/T01.csv`)

| Caso | Conjunto | Intentos fallidos previos (en la última hora) | Distancia al último acceso (km) | Datos descargados (MB en la sesión) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 1 | 767 | 692 | 0 |
| 2 | Entrenamiento | 2 | 8331 | 594 | 0 |
| 3 | Entrenamiento | 12 | 1592 | 54 | 0 |
| 4 | Entrenamiento | 3 | 796 | 499 | 0 |
| 5 | Entrenamiento | 9 | 5393 | 378 | 0 |
| 6 | Entrenamiento | 3 | 7361 | 288 | 0 |
| 7 | Entrenamiento | 0 | 8420 | 448 | 0 |
| 8 | Entrenamiento | 6 | 2861 | 300 | 0 |
| 9 | Entrenamiento | 6 | 5928 | 217 | 0 |
| 10 | Entrenamiento | 14 | 8475 | 513 | 1 |
| 11 | Entrenamiento | 15 | 6761 | 245 | 1 |
| 12 | Entrenamiento | 7 | 806 | 92 | 0 |
| 13 | Entrenamiento | 7 | 4079 | 706 | 0 |
| 14 | Entrenamiento | 6 | 1934 | 701 | 0 |
| 15 | Prueba | 13 | 2688 | 42 | 0 |
| 16 | Prueba | 14 | 57 | 645 | 0 |
| 17 | Prueba | 13 | 1119 | 612 | 0 |
| 18 | Prueba | 15 | 2098 | 615 | 0 |
| 19 | Prueba | 15 | 5747 | 335 | 1 |
| 20 | Prueba | 1 | 6373 | 231 | 0 |

---

## T02 · ¿9z gana este mapa?

**Dominio:** Equipo de E-Sports argentina sobre Counter-Strike historia · **IA declarada:** deepseek

**Situación.** El analista de un equipo argentino de Counter-Strike quiere predecir qué mapas gana el equipo para preparar el veto. Cada caso es un mapa jugado.

**Quién decide.** El analista y el capitán, al armar el veto.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = 9z gana el mapa.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Dejar en el veto un mapa que se pierde.
- Falso negativo (dice NO y era SÍ): Vetar un mapa que se ganaba.

**Datos** (también en `datos/T02.csv`)

| Caso | Conjunto | Diferencia de ranking (puestos (positivo = 9z mejor rankeado)) | Rondas de pistola ganadas (% en el torneo) | Mapa elegido por 9z (0 = no, 1 = sí) | Rondas ganadas en el primer tiempo (de 12) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | -19 | 66 | 0 | 2 | 0 |
| 2 | Entrenamiento | 7 | 29 | 1 | 9 | 1 |
| 3 | Entrenamiento | -6 | 23 | 1 | 4 | 0 |
| 4 | Entrenamiento | -7 | 29 | 0 | 4 | 0 |
| 5 | Entrenamiento | 2 | 68 | 1 | 8 | 1 |
| 6 | Entrenamiento | 5 | 79 | 1 | 7 | 1 |
| 7 | Entrenamiento | 11 | 76 | 0 | 9 | 1 |
| 8 | Entrenamiento | 27 | 31 | 1 | 9 | 1 |
| 9 | Entrenamiento | -3 | 58 | 0 | 5 | 0 |
| 10 | Entrenamiento | 12 | 38 | 1 | 7 | 1 |
| 11 | Entrenamiento | 2 | 64 | 0 | 4 | 0 |
| 12 | Entrenamiento | -4 | 42 | 0 | 3 | 0 |
| 13 | Entrenamiento | -16 | 54 | 0 | 2 | 0 |
| 14 | Entrenamiento | -5 | 70 | 1 | 8 | 1 |
| 15 | Prueba | -4 | 63 | 0 | 8 | 1 |
| 16 | Prueba | -29 | 29 | 0 | 3 | 0 |
| 17 | Prueba | 0 | 46 | 1 | 9 | 1 |
| 18 | Prueba | 27 | 67 | 0 | 8 | 1 |
| 19 | Prueba | 20 | 38 | 0 | 8 | 1 |
| 20 | Prueba | -16 | 22 | 1 | 3 | 0 |

---

## T03 · ¿Automatizamos este proceso?

**Dominio:** Automatización de procesos · **IA declarada:** Claude

**Situación.** Una empresa decide qué procesos administrativos automatizar con un bot de software. Cada caso es un proceso candidato.

**Quién decide.** El área de mejora de procesos.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la automatización se paga en menos de 6 meses.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Automatizar algo que no se paga: horas de desarrollo y mantenimiento perdidas.
- Falso negativo (dice NO y era SÍ): Dejar manual algo que convenía automatizar.

**Dato de contexto.** La dirección premia al área por la cantidad de procesos automatizados.

**Datos** (también en `datos/T03.csv`)

| Caso | Conjunto | Ejecuciones por mes (cantidad) | Minutos por ejecución (min) | Excepciones (% de casos que no siguen la regla) | Procesos automatizados del área (en el año) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 225 | 26 | 10 | 7 | 0 |
| 2 | Entrenamiento | 1111 | 42 | 37 | 30 | 0 |
| 3 | Entrenamiento | 1828 | 60 | 50 | 10 | 0 |
| 4 | Entrenamiento | 696 | 26 | 3 | 16 | 0 |
| 5 | Entrenamiento | 1312 | 26 | 29 | 14 | 1 |
| 6 | Entrenamiento | 1993 | 45 | 36 | 0 | 1 |
| 7 | Entrenamiento | 235 | 23 | 49 | 24 | 0 |
| 8 | Entrenamiento | 400 | 45 | 44 | 18 | 0 |
| 9 | Entrenamiento | 1279 | 52 | 35 | 23 | 1 |
| 10 | Entrenamiento | 1534 | 39 | 14 | 8 | 1 |
| 11 | Entrenamiento | 877 | 37 | 30 | 10 | 0 |
| 12 | Entrenamiento | 653 | 23 | 34 | 30 | 0 |
| 13 | Entrenamiento | 1468 | 48 | 16 | 21 | 1 |
| 14 | Entrenamiento | 1485 | 48 | 25 | 2 | 1 |
| 15 | Prueba | 1276 | 58 | 0 | 22 | 1 |
| 16 | Prueba | 357 | 26 | 30 | 4 | 0 |
| 17 | Prueba | 194 | 38 | 31 | 30 | 0 |
| 18 | Prueba | 1460 | 17 | 9 | 17 | 1 |
| 19 | Prueba | 1605 | 32 | 9 | 13 | 1 |
| 20 | Prueba | 1393 | 42 | 44 | 6 | 0 |

---

## T04 · ¿Está en fuera de juego?

**Dominio:** Inteligencia Artificial en el deporte · **IA declarada:** ChatGpt

**Situación.** Un sistema de fuera de juego semiautomático decide si anula un gol. Cada caso es una jugada revisada.

**Quién decide.** El sistema, con el árbitro del VAR.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el atacante está en posición adelantada.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Anular un gol válido: cambia el resultado y el reglamento pide que, en la duda, se favorezca al atacante.
- Falso negativo (dice NO y era SÍ): Convalidar un gol en fuera de juego.

**Datos** (también en `datos/T04.csv`)

| Caso | Conjunto | Adelanto medido (cm (positivo = adelantado)) | Error del seguimiento (cm) | Cámaras con visión clara (de 12) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | -36 | 8 | 12 | 0 |
| 2 | Entrenamiento | -7 | 12 | 11 | 0 |
| 3 | Entrenamiento | 30 | 4 | 12 | 1 |
| 4 | Entrenamiento | 1 | 7 | 10 | 0 |
| 5 | Entrenamiento | -14 | 13 | 8 | 0 |
| 6 | Entrenamiento | 32 | 4 | 12 | 1 |
| 7 | Entrenamiento | 20 | 13 | 12 | 1 |
| 8 | Entrenamiento | 31 | 11 | 10 | 1 |
| 9 | Entrenamiento | -29 | 11 | 11 | 0 |
| 10 | Entrenamiento | -23 | 3 | 10 | 0 |
| 11 | Entrenamiento | 33 | 3 | 10 | 1 |
| 12 | Entrenamiento | -28 | 9 | 6 | 0 |
| 13 | Entrenamiento | -32 | 9 | 11 | 0 |
| 14 | Entrenamiento | -37 | 4 | 10 | 0 |
| 15 | Prueba | 20 | 9 | 9 | 1 |
| 16 | Prueba | -33 | 13 | 5 | 0 |
| 17 | Prueba | -3 | 11 | 9 | 0 |
| 18 | Prueba | -18 | 3 | 11 | 1 |
| 19 | Prueba | 18 | 8 | 8 | 0 |
| 20 | Prueba | 17 | 9 | 7 | 1 |

---

## T05 · ¿Esta partida va a quedar desbalanceada?

**Dominio:** Gaming · **IA declarada:** ChatGPT

**Situación.** Un juego online arma partidas 5 contra 5. Antes de confirmar una partida, el sistema estima si va a quedar desbalanceada. Cada caso es una partida armada.

**Quién decide.** El sistema de emparejamiento.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la partida termina en paliza y algún jugador abandona.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Rearmar una partida que iba a estar pareja: espera de más.
- Falso negativo (dice NO y era SÍ): Confirmar una paliza: jugadores frustrados que abandonan el juego.

**Dato de contexto.** El estudio mide la calidad del emparejamiento por el tiempo de espera.

**Datos** (también en `datos/T05.csv`)

| Caso | Conjunto | Diferencia de nivel promedio (puntos de MMR) | Grupo armado (0 = no, 1 = un equipo es grupo premade) | Diferencia de partidas jugadas (promedio) | Tiempo de espera en cola (segundos) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 325 | 1 | 145 | 193 | 0 |
| 2 | Entrenamiento | 44 | 1 | 455 | 148 | 0 |
| 3 | Entrenamiento | 337 | 1 | 486 | 164 | 1 |
| 4 | Entrenamiento | 497 | 0 | 737 | 46 | 1 |
| 5 | Entrenamiento | 238 | 1 | 170 | 241 | 1 |
| 6 | Entrenamiento | 434 | 1 | 76 | 218 | 1 |
| 7 | Entrenamiento | 398 | 0 | 509 | 119 | 0 |
| 8 | Entrenamiento | 62 | 1 | 522 | 98 | 0 |
| 9 | Entrenamiento | 312 | 0 | 663 | 279 | 0 |
| 10 | Entrenamiento | 71 | 0 | 646 | 291 | 0 |
| 11 | Entrenamiento | 408 | 0 | 601 | 10 | 1 |
| 12 | Entrenamiento | 523 | 0 | 37 | 231 | 0 |
| 13 | Entrenamiento | 173 | 1 | 244 | 206 | 0 |
| 14 | Entrenamiento | 491 | 1 | 273 | 141 | 1 |
| 15 | Prueba | 330 | 0 | 761 | 218 | 0 |
| 16 | Prueba | 532 | 0 | 230 | 174 | 0 |
| 17 | Prueba | 16 | 1 | 197 | 262 | 0 |
| 18 | Prueba | 375 | 1 | 444 | 257 | 1 |
| 19 | Prueba | 225 | 1 | 33 | 265 | 0 |
| 20 | Prueba | 400 | 0 | 723 | 61 | 1 |

---

## T06 · ¿Este equipo desciende?

**Dominio:** Futbol Argentino · **IA declarada:** ChatGPT

**Situación.** Un analista estima a mitad de temporada qué equipos de la Liga Profesional van a descender. Cada caso es un equipo.

**Quién decide.** El analista de un club.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el equipo desciende.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Dar por descendido a quien se salva: el club arma el presupuesto de la B sin necesidad.
- Falso negativo (dice NO y era SÍ): No ver venir el descenso: no se refuerza a tiempo.

**Datos** (también en `datos/T06.csv`)

| Caso | Conjunto | Puntos por partido (en la temporada) | Promedio de los últimos años (puntos por partido) | Diferencia de gol (en la temporada) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 1,3 | 1,18 | 17 | 0 |
| 2 | Entrenamiento | 1,52 | 1,25 | 10 | 0 |
| 3 | Entrenamiento | 1,2 | 1,59 | 17 | 0 |
| 4 | Entrenamiento | 0,77 | 1,16 | -6 | 1 |
| 5 | Entrenamiento | 1,23 | 0,82 | 7 | 0 |
| 6 | Entrenamiento | 1,93 | 1,01 | 6 | 0 |
| 7 | Entrenamiento | 1,82 | 0,99 | 2 | 0 |
| 8 | Entrenamiento | 1,37 | 1,22 | 7 | 0 |
| 9 | Entrenamiento | 0,93 | 1,38 | 9 | 0 |
| 10 | Entrenamiento | 1,27 | 1,84 | 12 | 0 |
| 11 | Entrenamiento | 0,76 | 1,23 | 16 | 0 |
| 12 | Entrenamiento | 1,39 | 0,93 | -20 | 1 |
| 13 | Entrenamiento | 1,26 | 0,87 | 19 | 0 |
| 14 | Entrenamiento | 1,01 | 1,58 | -13 | 0 |
| 15 | Prueba | 1,33 | 1,27 | -2 | 0 |
| 16 | Prueba | 1,14 | 1,93 | -16 | 0 |
| 17 | Prueba | 1,78 | 1,91 | 13 | 0 |
| 18 | Prueba | 1,53 | 1,57 | -20 | 0 |
| 19 | Prueba | 0,72 | 0,86 | 16 | 1 |
| 20 | Prueba | 1,23 | 1,33 | 0 | 0 |

---

## T07 · ¿Este juego indie es un éxito en Steam?

**Dominio:** Videojuegos · **IA declarada:** Claude

**Situación.** Una distribuidora decide a qué juegos indie les financia el lanzamiento. Cada caso es un juego.

**Quién decide.** La distribuidora.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el juego supera las 10.000 reseñas en Steam.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Financiar un juego que no despega.
- Falso negativo (dice NO y era SÍ): Dejar pasar un éxito que publica otra distribuidora.

**Datos** (también en `datos/T07.csv`)

| Caso | Conjunto | Lista de deseos antes del lanzamiento (miles) | Precio (USD) | Tuvo demo pública (0 = no, 1 = sí) | Reseñas en la primera semana (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 210 | 36 | 0 | 518 | 0 |
| 2 | Entrenamiento | 97 | 17 | 0 | 541 | 0 |
| 3 | Entrenamiento | 224 | 17 | 0 | 6250 | 1 |
| 4 | Entrenamiento | 85 | 24 | 1 | 602 | 0 |
| 5 | Entrenamiento | 258 | 26 | 1 | 3912 | 1 |
| 6 | Entrenamiento | 134 | 5 | 1 | 4093 | 1 |
| 7 | Entrenamiento | 260 | 34 | 0 | 96 | 0 |
| 8 | Entrenamiento | 228 | 15 | 0 | 619 | 0 |
| 9 | Entrenamiento | 283 | 22 | 1 | 4719 | 1 |
| 10 | Entrenamiento | 87 | 28 | 0 | 358 | 0 |
| 11 | Entrenamiento | 219 | 12 | 0 | 4889 | 1 |
| 12 | Entrenamiento | 42 | 13 | 1 | 737 | 0 |
| 13 | Entrenamiento | 186 | 34 | 1 | 5601 | 1 |
| 14 | Entrenamiento | 32 | 39 | 0 | 456 | 0 |
| 15 | Prueba | 161 | 5 | 0 | 467 | 0 |
| 16 | Prueba | 242 | 38 | 0 | 891 | 0 |
| 17 | Prueba | 3 | 35 | 1 | 514 | 0 |
| 18 | Prueba | 158 | 16 | 1 | 7407 | 1 |
| 19 | Prueba | 169 | 37 | 1 | 6271 | 1 |
| 20 | Prueba | 253 | 17 | 0 | 341 | 0 |

---

## T08 · ¿Este jugador profesional se quema en el split?

**Dominio:** Esports · **IA declarada:** Chat gpt

**Situación.** Un equipo de esports quiere detectar a tiempo a los jugadores con riesgo de agotamiento (burnout) durante la temporada. Cada caso es un jugador en un mes.

**Quién decide.** El cuerpo técnico del equipo.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el rendimiento del jugador cae fuerte el mes siguiente.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Dar descanso a quien estaba bien: se pierde ritmo de juego.
- Falso negativo (dice NO y era SÍ): No detectar el agotamiento: el jugador rinde mal y puede dejar el equipo.

**Dato de contexto.** El equipo mide el compromiso de los jugadores por horas de práctica.

**Datos** (también en `datos/T08.csv`)

| Caso | Conjunto | Días libres (en el mes) | Horas de sueño (promedio) | Partidas oficiales (en el mes) | Horas de práctica (por día) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 3 | 6,8 | 5 | 12 | 0 |
| 2 | Entrenamiento | 2 | 8,1 | 17 | 13 | 1 |
| 3 | Entrenamiento | 5 | 8,3 | 5 | 13 | 0 |
| 4 | Entrenamiento | 0 | 5,7 | 14 | 11 | 1 |
| 5 | Entrenamiento | 1 | 8,1 | 21 | 8 | 1 |
| 6 | Entrenamiento | 6 | 5,4 | 29 | 8 | 1 |
| 7 | Entrenamiento | 6 | 7,7 | 18 | 13 | 0 |
| 8 | Entrenamiento | 8 | 6,3 | 5 | 8 | 0 |
| 9 | Entrenamiento | 2 | 7,7 | 16 | 8 | 0 |
| 10 | Entrenamiento | 6 | 5,3 | 15 | 11 | 0 |
| 11 | Entrenamiento | 2 | 5,6 | 14 | 12 | 1 |
| 12 | Entrenamiento | 7 | 5,9 | 17 | 13 | 0 |
| 13 | Entrenamiento | 6 | 8,0 | 9 | 9 | 0 |
| 14 | Entrenamiento | 7 | 7,2 | 15 | 11 | 0 |
| 15 | Prueba | 7 | 5,8 | 16 | 12 | 0 |
| 16 | Prueba | 5 | 5,2 | 23 | 6 | 1 |
| 17 | Prueba | 6 | 7,1 | 25 | 14 | 0 |
| 18 | Prueba | 1 | 8,0 | 21 | 6 | 1 |
| 19 | Prueba | 8 | 6,9 | 18 | 11 | 0 |
| 20 | Prueba | 4 | 6,0 | 9 | 8 | 1 |

---

## T09 · ¿Este colectivo llega con más de 10 minutos de demora?

**Dominio:** Los desafíos del transporte del siglo XXI · **IA declarada:** ChatGPT

**Situación.** Una empresa de transporte quiere avisar en la app cuándo un colectivo va a llegar muy demorado a la cabecera. Cada caso es un viaje.

**Quién decide.** El sistema de información al pasajero.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el colectivo llega con más de 10 minutos de demora.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Avisar una demora que no ocurre: la gente se va a otra línea sin necesidad.
- Falso negativo (dice NO y era SÍ): No avisar una demora: pasajeros esperando y llegando tarde.

**Datos** (también en `datos/T09.csv`)

| Caso | Conjunto | Pasajeros a bordo (promedio del viaje) | Lluvia (mm en la hora) | Obras en el recorrido (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 83 | 30 | 2 | 1 |
| 2 | Entrenamiento | 12 | 30 | 0 | 0 |
| 3 | Entrenamiento | 70 | 14 | 4 | 0 |
| 4 | Entrenamiento | 80 | 13 | 3 | 0 |
| 5 | Entrenamiento | 66 | 30 | 1 | 0 |
| 6 | Entrenamiento | 70 | 7 | 1 | 0 |
| 7 | Entrenamiento | 67 | 29 | 2 | 0 |
| 8 | Entrenamiento | 44 | 17 | 3 | 0 |
| 9 | Entrenamiento | 31 | 13 | 0 | 0 |
| 10 | Entrenamiento | 68 | 15 | 1 | 0 |
| 11 | Entrenamiento | 9 | 18 | 0 | 0 |
| 12 | Entrenamiento | 63 | 24 | 3 | 1 |
| 13 | Entrenamiento | 86 | 13 | 1 | 0 |
| 14 | Entrenamiento | 58 | 10 | 1 | 0 |
| 15 | Prueba | 14 | 23 | 3 | 0 |
| 16 | Prueba | 81 | 25 | 1 | 0 |
| 17 | Prueba | 32 | 9 | 2 | 0 |
| 18 | Prueba | 32 | 13 | 3 | 0 |
| 19 | Prueba | 33 | 9 | 2 | 0 |
| 20 | Prueba | 70 | 26 | 3 | 1 |

---

## T10 · ¿Esta película con mucho CGI recupera su presupuesto?

**Dominio:** entretenimiento(evolucion del cgi del cine) · **IA declarada:** claude

**Situación.** Un estudio decide si aprueba películas con efectos visuales generados por computadora (CGI) intensivos. Cada caso es una película.

**Quién decide.** El comité de aprobación del estudio.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la película recupera su presupuesto en taquilla.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Aprobar una película que no recupera: pérdida millonaria.
- Falso negativo (dice NO y era SÍ): Rechazar un éxito que después hace otro estudio.

**Datos** (también en `datos/T10.csv`)

| Caso | Conjunto | Presupuesto en CGI (% del total) | Es secuela o franquicia (0 = no, 1 = sí) | Interés en el tráiler (millones de vistas la primera semana) | Recaudación del primer fin de semana (% del presupuesto) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 59 | 1 | 16 | 13 | 0 |
| 2 | Entrenamiento | 18 | 1 | 38 | 109 | 1 |
| 3 | Entrenamiento | 30 | 0 | 48 | 23 | 0 |
| 4 | Entrenamiento | 12 | 0 | 92 | 103 | 1 |
| 5 | Entrenamiento | 45 | 1 | 18 | 14 | 0 |
| 6 | Entrenamiento | 62 | 1 | 23 | 17 | 0 |
| 7 | Entrenamiento | 47 | 0 | 113 | 47 | 1 |
| 8 | Entrenamiento | 33 | 0 | 67 | 11 | 0 |
| 9 | Entrenamiento | 62 | 1 | 10 | 22 | 0 |
| 10 | Entrenamiento | 49 | 0 | 27 | 24 | 0 |
| 11 | Entrenamiento | 40 | 0 | 115 | 107 | 1 |
| 12 | Entrenamiento | 18 | 1 | 41 | 75 | 1 |
| 13 | Entrenamiento | 61 | 0 | 63 | 14 | 0 |
| 14 | Entrenamiento | 27 | 0 | 66 | 29 | 0 |
| 15 | Prueba | 44 | 0 | 92 | 6 | 0 |
| 16 | Prueba | 32 | 1 | 3 | 6 | 0 |
| 17 | Prueba | 11 | 0 | 83 | 58 | 1 |
| 18 | Prueba | 22 | 1 | 34 | 95 | 1 |
| 19 | Prueba | 53 | 0 | 41 | 7 | 0 |
| 20 | Prueba | 59 | 1 | 58 | 114 | 1 |

---

## T11 · ¿Este usuario está encerrado en una burbuja de filtro?

**Dominio:** Algoritmos de recomendación y burbujas de filtro · **IA declarada:** Gemini

**Situación.** Una red social quiere detectar usuarios encerrados en una burbuja de filtro para mostrarles contenido más diverso. Cada caso es un usuario en una semana.

**Quién decide.** El equipo de integridad de la red social.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el usuario está en una burbuja de filtro.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Diversificar el contenido de alguien que no lo necesitaba: un poco menos de interés.
- Falso negativo (dice NO y era SÍ): Dejar a alguien encerrado en su burbuja: se refuerza la polarización.

**Dato de contexto.** La red social mide el éxito por el tiempo que el usuario pasa en la plataforma.

**Datos** (también en `datos/T11.csv`)

| Caso | Conjunto | Contenido del mismo tema (% de lo consumido) | Fuentes distintas (consumidas en la semana) | Interacciones con opiniones opuestas (en la semana) | Tiempo en la plataforma (min por día) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 96 | 39 | 5 | 250 | 1 |
| 2 | Entrenamiento | 59 | 4 | 7 | 58 | 1 |
| 3 | Entrenamiento | 83 | 28 | 18 | 84 | 0 |
| 4 | Entrenamiento | 51 | 11 | 19 | 181 | 0 |
| 5 | Entrenamiento | 96 | 2 | 4 | 30 | 1 |
| 6 | Entrenamiento | 86 | 34 | 18 | 76 | 0 |
| 7 | Entrenamiento | 67 | 29 | 2 | 144 | 1 |
| 8 | Entrenamiento | 35 | 7 | 10 | 102 | 0 |
| 9 | Entrenamiento | 50 | 8 | 18 | 300 | 0 |
| 10 | Entrenamiento | 45 | 38 | 5 | 98 | 0 |
| 11 | Entrenamiento | 38 | 4 | 9 | 124 | 1 |
| 12 | Entrenamiento | 91 | 20 | 11 | 72 | 1 |
| 13 | Entrenamiento | 39 | 25 | 12 | 210 | 0 |
| 14 | Entrenamiento | 90 | 32 | 5 | 69 | 1 |
| 15 | Prueba | 77 | 17 | 17 | 266 | 0 |
| 16 | Prueba | 77 | 27 | 15 | 73 | 0 |
| 17 | Prueba | 64 | 31 | 11 | 168 | 0 |
| 18 | Prueba | 64 | 30 | 4 | 77 | 1 |
| 19 | Prueba | 50 | 18 | 5 | 300 | 0 |
| 20 | Prueba | 65 | 14 | 12 | 173 | 1 |

---

## T12 · ¿Este córner termina en gol?

**Dominio:** Inteligencia artificial aplicada al análisis, la predicción y la toma de decisiones en el fútbol. · **IA declarada:** ChatGPT

**Situación.** El cuerpo técnico analiza los córners a favor para decidir qué jugada preparada usar. Cada caso es un córner ejecutado.

**Quién decide.** El entrenador de pelota parada.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el córner termina en gol.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Practicar una jugada que no rinde.
- Falso negativo (dice NO y era SÍ): Descartar la jugada que hacía goles.

**Datos** (también en `datos/T12.csv`)

| Caso | Conjunto | Altura promedio de los cabeceadores (cm) | Jugadores propios en el área (cantidad) | Marcas en zona del rival (0 = individual, 1 = zonal) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 184 | 7 | 0 | 0 |
| 2 | Entrenamiento | 189 | 7 | 1 | 1 |
| 3 | Entrenamiento | 181 | 4 | 1 | 0 |
| 4 | Entrenamiento | 185 | 3 | 1 | 0 |
| 5 | Entrenamiento | 177 | 3 | 0 | 0 |
| 6 | Entrenamiento | 177 | 6 | 1 | 0 |
| 7 | Entrenamiento | 187 | 4 | 1 | 0 |
| 8 | Entrenamiento | 189 | 7 | 0 | 0 |
| 9 | Entrenamiento | 190 | 7 | 1 | 1 |
| 10 | Entrenamiento | 179 | 6 | 0 | 0 |
| 11 | Entrenamiento | 183 | 5 | 0 | 0 |
| 12 | Entrenamiento | 185 | 7 | 0 | 0 |
| 13 | Entrenamiento | 187 | 5 | 0 | 0 |
| 14 | Entrenamiento | 184 | 3 | 1 | 0 |
| 15 | Prueba | 176 | 6 | 1 | 0 |
| 16 | Prueba | 185 | 5 | 0 | 0 |
| 17 | Prueba | 186 | 6 | 0 | 0 |
| 18 | Prueba | 182 | 4 | 1 | 0 |
| 19 | Prueba | 191 | 7 | 0 | 1 |
| 20 | Prueba | 186 | 5 | 0 | 0 |

---

## T13 · ¿Aplicamos fungicida contra la roya de la soja?

**Dominio:** Agronomía · **IA declarada:** Claude

**Situación.** Un asesor decide si aplica fungicida en lotes de soja ante el riesgo de roya asiática. Cada caso es un lote en una semana.

**Quién decide.** El asesor agronómico.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la roya causa pérdidas si no se aplica.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Aplicar sin necesidad: costo del producto e impacto ambiental.
- Falso negativo (dice NO y era SÍ): No aplicar y que haya epidemia: pérdidas de rendimiento de hasta un tercio.

**Datos** (también en `datos/T13.csv`)

| Caso | Conjunto | Horas de mojado foliar (en la semana) | Temperatura media (°C) | Severidad en lotes vecinos (% de hojas afectadas) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 35 | 28,2 | 15 | 1 |
| 2 | Entrenamiento | 1 | 18,4 | 8 | 0 |
| 3 | Entrenamiento | 61 | 28,6 | 8 | 1 |
| 4 | Entrenamiento | 1 | 15,9 | 14 | 0 |
| 5 | Entrenamiento | 67 | 15,4 | 22 | 1 |
| 6 | Entrenamiento | 64 | 26,0 | 3 | 1 |
| 7 | Entrenamiento | 10 | 16,7 | 22 | 0 |
| 8 | Entrenamiento | 50 | 26,7 | 24 | 1 |
| 9 | Entrenamiento | 1 | 28,4 | 17 | 0 |
| 10 | Entrenamiento | 19 | 20,5 | 15 | 0 |
| 11 | Entrenamiento | 69 | 22,5 | 4 | 0 |
| 12 | Entrenamiento | 6 | 19,6 | 8 | 0 |
| 13 | Entrenamiento | 67 | 24,4 | 30 | 1 |
| 14 | Entrenamiento | 28 | 22,7 | 18 | 1 |
| 15 | Prueba | 18 | 21,7 | 17 | 0 |
| 16 | Prueba | 63 | 16,2 | 21 | 1 |
| 17 | Prueba | 21 | 18,6 | 21 | 0 |
| 18 | Prueba | 8 | 15,3 | 28 | 1 |
| 19 | Prueba | 48 | 20,3 | 26 | 1 |
| 20 | Prueba | 3 | 23,7 | 2 | 0 |

---

## T14 · ¿Este socio da de baja la cuota?

**Dominio:** Gimnasio · **IA declarada:** Claude

**Situación.** Una cadena de gimnasios quiere detectar a tiempo a los socios que están por irse, para ofrecerles un mes bonificado. Cada caso es un socio.

**Quién decide.** El área de retención del gimnasio.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el socio da de baja la cuota el mes siguiente.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Bonificar a quien no se iba: un mes regalado.
- Falso negativo (dice NO y era SÍ): No retener a quien se va: se pierde un año de cuotas.

**Datos** (también en `datos/T14.csv`)

| Caso | Conjunto | Visitas (en el último mes) | Antigüedad (meses) | Clases grupales (por semana) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 8 | 14 | 1 | 1 |
| 2 | Entrenamiento | 17 | 35 | 4 | 0 |
| 3 | Entrenamiento | 8 | 29 | 4 | 0 |
| 4 | Entrenamiento | 22 | 4 | 2 | 1 |
| 5 | Entrenamiento | 7 | 25 | 2 | 1 |
| 6 | Entrenamiento | 17 | 3 | 5 | 0 |
| 7 | Entrenamiento | 9 | 18 | 3 | 1 |
| 8 | Entrenamiento | 7 | 17 | 5 | 0 |
| 9 | Entrenamiento | 24 | 45 | 1 | 0 |
| 10 | Entrenamiento | 0 | 12 | 4 | 1 |
| 11 | Entrenamiento | 4 | 10 | 3 | 1 |
| 12 | Entrenamiento | 3 | 38 | 2 | 1 |
| 13 | Entrenamiento | 10 | 37 | 1 | 1 |
| 14 | Entrenamiento | 20 | 44 | 3 | 0 |
| 15 | Prueba | 19 | 10 | 3 | 1 |
| 16 | Prueba | 13 | 29 | 1 | 1 |
| 17 | Prueba | 19 | 36 | 4 | 0 |
| 18 | Prueba | 20 | 35 | 2 | 0 |
| 19 | Prueba | 11 | 11 | 4 | 1 |
| 20 | Prueba | 21 | 47 | 3 | 0 |

---

## T15 · ¿Sacamos al jugador para evaluar una conmoción?

**Dominio:** Nuevas tecnologicas el deporte · **IA declarada:** Gemini

**Situación.** En rugby, un protector bucal con sensor mide los impactos en la cabeza. El sistema decide si se saca al jugador para una evaluación de conmoción. Cada caso es un impacto.

**Quién decide.** El médico del partido, alertado por el sistema.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el jugador sufrió una conmoción cerebral.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Sacar a un jugador sano: el equipo juega 10 minutos con un suplente.
- Falso negativo (dice NO y era SÍ): Dejar jugando a alguien con una conmoción: riesgo de lesión cerebral grave.

**Datos** (también en `datos/T15.csv`)

| Caso | Conjunto | Aceleración pico (g) | Aceleración rotacional (miles de rad/s²) | Impactos previos en el partido (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 72 | 8,7 | 8 | 1 |
| 2 | Entrenamiento | 68 | 7,8 | 6 | 1 |
| 3 | Entrenamiento | 38 | 5,4 | 2 | 1 |
| 4 | Entrenamiento | 102 | 3,3 | 5 | 1 |
| 5 | Entrenamiento | 73 | 6,5 | 8 | 1 |
| 6 | Entrenamiento | 43 | 7,6 | 3 | 1 |
| 7 | Entrenamiento | 116 | 6,8 | 5 | 1 |
| 8 | Entrenamiento | 91 | 2,2 | 7 | 1 |
| 9 | Entrenamiento | 48 | 4,7 | 0 | 0 |
| 10 | Entrenamiento | 31 | 1,1 | 6 | 0 |
| 11 | Entrenamiento | 28 | 1,4 | 3 | 0 |
| 12 | Entrenamiento | 45 | 1,9 | 5 | 0 |
| 13 | Entrenamiento | 36 | 1,7 | 5 | 0 |
| 14 | Entrenamiento | 22 | 1,9 | 2 | 0 |
| 15 | Prueba | 14 | 7,2 | 6 | 0 |
| 16 | Prueba | 105 | 1,7 | 5 | 0 |
| 17 | Prueba | 88 | 3,4 | 6 | 1 |
| 18 | Prueba | 56 | 8,4 | 1 | 1 |
| 19 | Prueba | 48 | 6,3 | 3 | 1 |
| 20 | Prueba | 66 | 2,7 | 2 | 0 |

---

## T16 · ¿Este usuario termina la serie?

**Dominio:** consumo de peliculas y series en plataformas de streaming. · **IA declarada:** Gemini

**Situación.** Una plataforma quiere saber, después de la primera semana, quién va a terminar una serie, para decidir si le recomienda la temporada siguiente. Cada caso es un usuario que empezó una serie.

**Quién decide.** El equipo de contenidos de la plataforma.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el usuario termina la temporada.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Recomendar la temporada 2 a quien abandona.
- Falso negativo (dice NO y era SÍ): No recomendársela a quien la iba a mirar.

**Datos** (también en `datos/T16.csv`)

| Caso | Conjunto | Episodios vistos (en la primera semana) | Duración por episodio (min) | Vio la serie con alguien más (0 = no, 1 = sí) | Vio el anteúltimo episodio (0 = no, 1 = sí) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 2 | 50 | 0 | 0 | 0 |
| 2 | Entrenamiento | 9 | 59 | 0 | 0 | 0 |
| 3 | Entrenamiento | 8 | 49 | 0 | 1 | 1 |
| 4 | Entrenamiento | 6 | 51 | 1 | 1 | 1 |
| 5 | Entrenamiento | 5 | 44 | 0 | 0 | 0 |
| 6 | Entrenamiento | 5 | 64 | 0 | 0 | 0 |
| 7 | Entrenamiento | 8 | 37 | 1 | 1 | 1 |
| 8 | Entrenamiento | 7 | 37 | 1 | 1 | 1 |
| 9 | Entrenamiento | 7 | 34 | 0 | 1 | 1 |
| 10 | Entrenamiento | 8 | 53 | 0 | 0 | 0 |
| 11 | Entrenamiento | 7 | 21 | 0 | 1 | 1 |
| 12 | Entrenamiento | 4 | 68 | 1 | 0 | 0 |
| 13 | Entrenamiento | 3 | 22 | 0 | 0 | 0 |
| 14 | Entrenamiento | 2 | 28 | 1 | 1 | 1 |
| 15 | Prueba | 3 | 40 | 1 | 0 | 0 |
| 16 | Prueba | 8 | 32 | 1 | 1 | 1 |
| 17 | Prueba | 3 | 69 | 0 | 0 | 0 |
| 18 | Prueba | 1 | 63 | 1 | 0 | 0 |
| 19 | Prueba | 7 | 51 | 1 | 1 | 1 |
| 20 | Prueba | 8 | 20 | 0 | 1 | 1 |

---

## T17 · ¿Este jugador duplica su valor de mercado en dos años?

**Dominio:** Sistemas de Scouting y Valoración de Mercado de Jugadores · **IA declarada:** Gemini

**Situación.** Un área de scouting busca jugadores que se revaloricen para comprarlos antes de que suban de precio. Cada caso es un jugador.

**Quién decide.** La secretaría técnica, con el área de scouting.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el jugador duplica su valor de mercado en dos años.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Comprar a quien no se revaloriza: plata inmovilizada.
- Falso negativo (dice NO y era SÍ): No comprar a quien explota: después cuesta el doble.

**Datos** (también en `datos/T17.csv`)

| Caso | Conjunto | Edad (años) | Minutos jugados (en la temporada) | Goles + asistencias (cada 90 minutos) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 19 | 1463 | 0,71 | 0 |
| 2 | Entrenamiento | 22 | 304 | 0,4 | 0 |
| 3 | Entrenamiento | 23 | 439 | 0,08 | 0 |
| 4 | Entrenamiento | 27 | 622 | 0,54 | 0 |
| 5 | Entrenamiento | 19 | 1972 | 0,79 | 1 |
| 6 | Entrenamiento | 24 | 2526 | 0,5 | 0 |
| 7 | Entrenamiento | 23 | 608 | 0,0 | 0 |
| 8 | Entrenamiento | 21 | 2428 | 0,35 | 0 |
| 9 | Entrenamiento | 20 | 1555 | 0,38 | 0 |
| 10 | Entrenamiento | 18 | 2164 | 0,39 | 0 |
| 11 | Entrenamiento | 23 | 3372 | 0,33 | 0 |
| 12 | Entrenamiento | 25 | 812 | 0,38 | 0 |
| 13 | Entrenamiento | 18 | 1142 | 0,81 | 1 |
| 14 | Entrenamiento | 29 | 2227 | 0,03 | 0 |
| 15 | Prueba | 29 | 1149 | 0,11 | 0 |
| 16 | Prueba | 20 | 3064 | 0,59 | 1 |
| 17 | Prueba | 25 | 2324 | 0,29 | 0 |
| 18 | Prueba | 25 | 2555 | 0,36 | 0 |
| 19 | Prueba | 26 | 926 | 0,92 | 0 |
| 20 | Prueba | 26 | 1228 | 0,04 | 0 |

---

## T18 · ¿Este producto se queda sin stock la semana que viene?

**Dominio:** Logistica · **IA declarada:** ChatGPT

**Situación.** Un centro de distribución decide cada semana qué productos reponer de urgencia. Cada caso es un producto (SKU).

**Quién decide.** El planificador de abastecimiento.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el producto se queda sin stock la semana siguiente.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Reponer de urgencia algo que alcanzaba: flete urgente y sobrestock.
- Falso negativo (dice NO y era SÍ): Quedarse sin stock: ventas perdidas y un cliente que se va a la competencia.

**Datos** (también en `datos/T18.csv`)

| Caso | Conjunto | Días de cobertura (con el stock actual) | Variabilidad de la demanda (coeficiente de variación) | Demora del proveedor (días) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 24 | 0,94 | 8 | 0 |
| 2 | Entrenamiento | 13 | 0,21 | 18 | 0 |
| 3 | Entrenamiento | 10 | 0,2 | 17 | 1 |
| 4 | Entrenamiento | 14 | 0,84 | 19 | 1 |
| 5 | Entrenamiento | 1 | 0,27 | 15 | 1 |
| 6 | Entrenamiento | 9 | 0,58 | 7 | 0 |
| 7 | Entrenamiento | 3 | 0,82 | 13 | 1 |
| 8 | Entrenamiento | 21 | 0,42 | 5 | 0 |
| 9 | Entrenamiento | 26 | 0,3 | 12 | 0 |
| 10 | Entrenamiento | 8 | 0,32 | 15 | 0 |
| 11 | Entrenamiento | 3 | 0,25 | 18 | 1 |
| 12 | Entrenamiento | 18 | 0,35 | 15 | 0 |
| 13 | Entrenamiento | 14 | 0,35 | 9 | 0 |
| 14 | Entrenamiento | 22 | 0,29 | 6 | 0 |
| 15 | Prueba | 11 | 0,58 | 13 | 1 |
| 16 | Prueba | 3 | 0,88 | 13 | 1 |
| 17 | Prueba | 1 | 0,84 | 12 | 1 |
| 18 | Prueba | 2 | 0,1 | 16 | 0 |
| 19 | Prueba | 22 | 0,81 | 6 | 0 |
| 20 | Prueba | 2 | 0,54 | 19 | 1 |

---

## T19 · ¿Bajamos la dificultad de este jefe?

**Dominio:** IA en vidiojuegos enfocandonos en npc y enemigos · **IA declarada:** ChatGPT

**Situación.** Un juego ajusta la dificultad del jefe final según cómo le va a cada jugador. Cada caso es un jugador trabado en el jefe.

**Quién decide.** La IA de dificultad adaptativa.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el jugador abandona el juego si no se baja la dificultad.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Bajar la dificultad a quien lo iba a pasar: le quitamos el desafío.
- Falso negativo (dice NO y era SÍ): No ayudar a quien abandona: se pierde un jugador.

**Dato de contexto.** El estudio mide el éxito por el porcentaje de jugadores que derrotan al jefe.

**Datos** (también en `datos/T19.csv`)

| Caso | Conjunto | Muertes seguidas (contra el jefe) | Vida que le dejó al jefe (% en el mejor intento) | Horas jugadas (en total) | Jugadores que derrotan al jefe (% global) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 2 | 69 | 107 | 90 | 0 |
| 2 | Entrenamiento | 11 | 76 | 113 | 79 | 0 |
| 3 | Entrenamiento | 11 | 38 | 42 | 35 | 1 |
| 4 | Entrenamiento | 12 | 57 | 11 | 42 | 1 |
| 5 | Entrenamiento | 22 | 8 | 47 | 90 | 0 |
| 6 | Entrenamiento | 5 | 11 | 91 | 77 | 0 |
| 7 | Entrenamiento | 3 | 88 | 5 | 35 | 1 |
| 8 | Entrenamiento | 8 | 57 | 14 | 44 | 1 |
| 9 | Entrenamiento | 2 | 25 | 106 | 75 | 0 |
| 10 | Entrenamiento | 8 | 64 | 40 | 39 | 1 |
| 11 | Entrenamiento | 10 | 77 | 101 | 71 | 0 |
| 12 | Entrenamiento | 3 | 45 | 51 | 28 | 0 |
| 13 | Entrenamiento | 15 | 78 | 34 | 61 | 1 |
| 14 | Entrenamiento | 25 | 51 | 43 | 12 | 1 |
| 15 | Prueba | 14 | 43 | 41 | 48 | 1 |
| 16 | Prueba | 5 | 31 | 69 | 55 | 0 |
| 17 | Prueba | 8 | 45 | 79 | 90 | 0 |
| 18 | Prueba | 18 | 44 | 70 | 6 | 1 |
| 19 | Prueba | 17 | 35 | 17 | 44 | 1 |
| 20 | Prueba | 22 | 83 | 67 | 5 | 1 |

---

## T20 · ¿Esta entrega falla por ausente?

**Dominio:** Logística · **IA declarada:** Claude

**Situación.** Una empresa de última milla quiere anticipar qué entregas van a fallar porque no hay nadie en el domicilio, para reprogramarlas. Cada caso es una entrega.

**Quién decide.** El sistema de ruteo.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = la entrega falla por ausente.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Reprogramar una entrega que salía bien: demora innecesaria.
- Falso negativo (dice NO y era SÍ): Mandar el camión a un domicilio vacío: viaje perdido.

**Datos** (también en `datos/T20.csv`)

| Caso | Conjunto | Entregas fallidas previas (del cliente) | Respondió el aviso por WhatsApp (0 = no, 1 = sí) | Franja horaria (0 = mañana, 1 = tarde) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 4 | 0 | 0 | 1 |
| 2 | Entrenamiento | 5 | 1 | 0 | 0 |
| 3 | Entrenamiento | 1 | 0 | 0 | 0 |
| 4 | Entrenamiento | 2 | 1 | 1 | 0 |
| 5 | Entrenamiento | 2 | 0 | 0 | 0 |
| 6 | Entrenamiento | 5 | 0 | 0 | 1 |
| 7 | Entrenamiento | 0 | 0 | 0 | 0 |
| 8 | Entrenamiento | 4 | 0 | 1 | 0 |
| 9 | Entrenamiento | 5 | 1 | 1 | 0 |
| 10 | Entrenamiento | 2 | 1 | 0 | 0 |
| 11 | Entrenamiento | 4 | 1 | 0 | 0 |
| 12 | Entrenamiento | 4 | 1 | 1 | 0 |
| 13 | Entrenamiento | 3 | 1 | 1 | 0 |
| 14 | Entrenamiento | 6 | 1 | 1 | 0 |
| 15 | Prueba | 3 | 0 | 1 | 0 |
| 16 | Prueba | 2 | 1 | 1 | 0 |
| 17 | Prueba | 2 | 1 | 0 | 0 |
| 18 | Prueba | 3 | 1 | 0 | 0 |
| 19 | Prueba | 4 | 0 | 0 | 1 |
| 20 | Prueba | 3 | 0 | 1 | 0 |

---

## T21 · ¿El NPC aliado cura al jugador ahora?

**Dominio:** Comportamiento de los NPCs en los videojuegos · **IA declarada:** ChatGPT

**Situación.** En un juego cooperativo, un NPC compañero decide en cada momento si usa una poción para curar al jugador. Cada caso es un momento de combate.

**Quién decide.** La IA del NPC compañero.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = si no lo cura ahora, el jugador muere en los próximos segundos.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Gastar una poción cuando no hacía falta.
- Falso negativo (dice NO y era SÍ): Dejar morir al jugador: pierde el progreso y odia al compañero.

**Datos** (también en `datos/T21.csv`)

| Caso | Conjunto | Vida del jugador (%) | Enemigos cerca (cantidad) | Pociones restantes (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 14 | 5 | 3 | 1 |
| 2 | Entrenamiento | 12 | 1 | 1 | 0 |
| 3 | Entrenamiento | 34 | 4 | 2 | 1 |
| 4 | Entrenamiento | 81 | 2 | 5 | 0 |
| 5 | Entrenamiento | 50 | 5 | 3 | 1 |
| 6 | Entrenamiento | 27 | 3 | 4 | 1 |
| 7 | Entrenamiento | 8 | 5 | 2 | 1 |
| 8 | Entrenamiento | 41 | 4 | 2 | 0 |
| 9 | Entrenamiento | 6 | 4 | 4 | 1 |
| 10 | Entrenamiento | 77 | 3 | 4 | 0 |
| 11 | Entrenamiento | 71 | 4 | 3 | 1 |
| 12 | Entrenamiento | 37 | 4 | 1 | 1 |
| 13 | Entrenamiento | 64 | 2 | 3 | 0 |
| 14 | Entrenamiento | 76 | 6 | 2 | 1 |
| 15 | Prueba | 71 | 1 | 3 | 0 |
| 16 | Prueba | 73 | 3 | 3 | 0 |
| 17 | Prueba | 83 | 2 | 2 | 0 |
| 18 | Prueba | 46 | 6 | 4 | 1 |
| 19 | Prueba | 11 | 4 | 2 | 1 |
| 20 | Prueba | 97 | 4 | 3 | 0 |

---

## T22 · ¿Este estudiante desaprueba el parcial?

**Dominio:** Tutoría y Predicción de desempeño estudiantil - Educación · **IA declarada:** Gemini

**Situación.** Un tutor inteligente busca alertar a tiempo a los estudiantes en riesgo de desaprobar el primer parcial. Cada caso es un estudiante, dos semanas antes del parcial.

**Quién decide.** El tutor inteligente, que avisa al docente.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el estudiante desaprueba el parcial.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Alertar a quien iba a aprobar: un mail de más.
- Falso negativo (dice NO y era SÍ): No alertar a quien desaprueba: llega tarde la ayuda.

**Datos** (también en `datos/T22.csv`)

| Caso | Conjunto | Entregas a tiempo (%) | Horas en el campus virtual (por semana) | Nota del cuestionario 1 (0 a 10) | Se anotó al recuperatorio (0 = no, 1 = sí) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 56 | 9,4 | 9 | 0 | 0 |
| 2 | Entrenamiento | 91 | 5,2 | 3 | 0 | 0 |
| 3 | Entrenamiento | 66 | 11,6 | 3 | 0 | 0 |
| 4 | Entrenamiento | 9 | 4,4 | 8 | 1 | 1 |
| 5 | Entrenamiento | 83 | 12,4 | 2 | 0 | 0 |
| 6 | Entrenamiento | 92 | 15,0 | 9 | 0 | 0 |
| 7 | Entrenamiento | 43 | 14,1 | 2 | 1 | 1 |
| 8 | Entrenamiento | 41 | 1,4 | 9 | 1 | 1 |
| 9 | Entrenamiento | 22 | 3,2 | 9 | 1 | 1 |
| 10 | Entrenamiento | 31 | 5,3 | 5 | 1 | 1 |
| 11 | Entrenamiento | 14 | 13,5 | 3 | 1 | 1 |
| 12 | Entrenamiento | 37 | 12,4 | 5 | 1 | 1 |
| 13 | Entrenamiento | 88 | 12,9 | 7 | 0 | 0 |
| 14 | Entrenamiento | 82 | 4,1 | 6 | 0 | 0 |
| 15 | Prueba | 33 | 10,6 | 8 | 0 | 0 |
| 16 | Prueba | 23 | 5,2 | 3 | 1 | 1 |
| 17 | Prueba | 42 | 4,9 | 9 | 1 | 1 |
| 18 | Prueba | 27 | 4,6 | 1 | 1 | 1 |
| 19 | Prueba | 31 | 5,3 | 7 | 1 | 1 |
| 20 | Prueba | 50 | 4,5 | 10 | 0 | 0 |

---

## T23 · ¿Se agotan las entradas de este partido?

**Dominio:** deportes · **IA declarada:** ChatGPT

**Situación.** Un club decide una semana antes si refuerza el operativo de seguridad y habilita más puestos de control, previendo un estadio lleno. Cada caso es un partido de local.

**Quién decide.** La gerencia de operaciones del club.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = se agotan las entradas.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Reforzar el operativo para un estadio a medio llenar: gasto de más.
- Falso negativo (dice NO y era SÍ): Estadio lleno sin operativo reforzado: riesgo para el público.

**Datos** (también en `datos/T23.csv`)

| Caso | Conjunto | Es un clásico (0 = no, 1 = sí) | Puesto del equipo en la tabla (puesto) | Precio de la entrada (miles de pesos) | Entradas vendidas el día anterior al partido (% de la capacidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 0 | 25 | 12 | 95 | 1 |
| 2 | Entrenamiento | 0 | 6 | 20 | 63 | 0 |
| 3 | Entrenamiento | 1 | 25 | 54 | 93 | 1 |
| 4 | Entrenamiento | 0 | 26 | 41 | 77 | 0 |
| 5 | Entrenamiento | 1 | 12 | 16 | 96 | 1 |
| 6 | Entrenamiento | 0 | 27 | 13 | 48 | 0 |
| 7 | Entrenamiento | 1 | 6 | 46 | 93 | 1 |
| 8 | Entrenamiento | 0 | 22 | 55 | 63 | 0 |
| 9 | Entrenamiento | 0 | 22 | 23 | 74 | 0 |
| 10 | Entrenamiento | 1 | 7 | 10 | 96 | 1 |
| 11 | Entrenamiento | 1 | 22 | 12 | 98 | 1 |
| 12 | Entrenamiento | 0 | 11 | 46 | 45 | 0 |
| 13 | Entrenamiento | 0 | 20 | 44 | 51 | 0 |
| 14 | Entrenamiento | 1 | 9 | 11 | 95 | 1 |
| 15 | Prueba | 1 | 19 | 18 | 100 | 1 |
| 16 | Prueba | 1 | 24 | 15 | 93 | 1 |
| 17 | Prueba | 0 | 14 | 28 | 78 | 0 |
| 18 | Prueba | 1 | 9 | 39 | 92 | 1 |
| 19 | Prueba | 0 | 20 | 49 | 62 | 0 |
| 20 | Prueba | 1 | 17 | 54 | 100 | 1 |

---

## T24 · ¿Mañana hay pico de demanda eléctrica en el barrio?

**Dominio:** Ciudades inteligentes (urbanismo, eficiencia energetica y de uso de recursos) · **IA declarada:** Gemini

**Situación.** Una distribuidora eléctrica decide si activa generadores de respaldo en un barrio para el día siguiente. Cada caso es un barrio en un día de verano.

**Quién decide.** El centro de control de la distribuidora.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = al día siguiente la demanda supera la capacidad del barrio.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Activar el respaldo sin necesidad: costo operativo.
- Falso negativo (dice NO y era SÍ): No activarlo y que haya pico: corte de luz en plena ola de calor.

**Datos** (también en `datos/T24.csv`)

| Caso | Conjunto | Temperatura máxima pronosticada (°C) | Día hábil (0 = no, 1 = sí) | Demanda del día anterior (% de la capacidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 36 | 1 | 55 | 0 |
| 2 | Entrenamiento | 41 | 0 | 98 | 1 |
| 3 | Entrenamiento | 33 | 1 | 79 | 0 |
| 4 | Entrenamiento | 27 | 1 | 69 | 0 |
| 5 | Entrenamiento | 29 | 0 | 73 | 0 |
| 6 | Entrenamiento | 26 | 1 | 79 | 0 |
| 7 | Entrenamiento | 27 | 1 | 64 | 0 |
| 8 | Entrenamiento | 40 | 0 | 60 | 0 |
| 9 | Entrenamiento | 29 | 1 | 102 | 0 |
| 10 | Entrenamiento | 25 | 0 | 78 | 0 |
| 11 | Entrenamiento | 36 | 1 | 83 | 1 |
| 12 | Entrenamiento | 42 | 1 | 86 | 1 |
| 13 | Entrenamiento | 30 | 1 | 80 | 1 |
| 14 | Entrenamiento | 41 | 0 | 99 | 1 |
| 15 | Prueba | 36 | 1 | 78 | 1 |
| 16 | Prueba | 36 | 1 | 70 | 1 |
| 17 | Prueba | 27 | 1 | 50 | 0 |
| 18 | Prueba | 34 | 1 | 84 | 1 |
| 19 | Prueba | 31 | 1 | 62 | 0 |
| 20 | Prueba | 32 | 0 | 61 | 0 |

---

## T25 · ¿Este jugador compra el pase de batalla?

**Dominio:** Videojuegos · **IA declarada:** Claude

**Situación.** Un juego gratuito decide a qué jugadores mostrarles una oferta del pase de batalla. Cada caso es un jugador.

**Quién decide.** El sistema de ofertas del juego.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el jugador compra el pase de batalla.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Mostrar la oferta a quien no compra: un cartel molesto.
- Falso negativo (dice NO y era SÍ): No mostrarla a quien compraba: venta perdida.

**Datos** (también en `datos/T25.csv`)

| Caso | Conjunto | Horas jugadas (por semana) | Nivel de cuenta (nivel) | Compras previas (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 15 | 61 | 2 | 0 |
| 2 | Entrenamiento | 28 | 5 | 5 | 1 |
| 3 | Entrenamiento | 23 | 60 | 1 | 0 |
| 4 | Entrenamiento | 16 | 66 | 0 | 0 |
| 5 | Entrenamiento | 4 | 78 | 3 | 0 |
| 6 | Entrenamiento | 26 | 42 | 2 | 0 |
| 7 | Entrenamiento | 25 | 22 | 3 | 0 |
| 8 | Entrenamiento | 12 | 60 | 0 | 0 |
| 9 | Entrenamiento | 18 | 5 | 2 | 0 |
| 10 | Entrenamiento | 1 | 21 | 1 | 0 |
| 11 | Entrenamiento | 0 | 73 | 1 | 0 |
| 12 | Entrenamiento | 7 | 54 | 0 | 0 |
| 13 | Entrenamiento | 12 | 4 | 1 | 0 |
| 14 | Entrenamiento | 28 | 26 | 5 | 1 |
| 15 | Prueba | 21 | 24 | 5 | 0 |
| 16 | Prueba | 20 | 98 | 1 | 0 |
| 17 | Prueba | 16 | 54 | 4 | 0 |
| 18 | Prueba | 15 | 85 | 4 | 0 |
| 19 | Prueba | 18 | 90 | 5 | 1 |
| 20 | Prueba | 10 | 3 | 4 | 0 |

---

## T26 · ¿Subir la carga en sentadilla lo lesiona?

**Dominio:** Gimnasio · **IA declarada:** Claude

**Situación.** Una app de entrenamiento decide si recomienda subir la carga en sentadilla esta semana. Cada caso es un usuario.

**Quién decide.** El entrenador virtual de la app.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el usuario se lesiona si sube la carga.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): No recomendar subir a quien podía: progresa más lento.
- Falso negativo (dice NO y era SÍ): Recomendar subir a quien se lesiona: semanas sin entrenar.

**Datos** (también en `datos/T26.csv`)

| Caso | Conjunto | Aumento de carga propuesto (% sobre la semana anterior) | Técnica evaluada (1 a 10) | Horas de sueño (promedio) | Dolor reportado al día siguiente (escala 0 a 10) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 6 | 8 | 7,4 | 0 | 0 |
| 2 | Entrenamiento | 13 | 2 | 6,7 | 2 | 0 |
| 3 | Entrenamiento | 14 | 3 | 8,7 | 3 | 0 |
| 4 | Entrenamiento | 21 | 2 | 8,8 | 8 | 1 |
| 5 | Entrenamiento | 6 | 7 | 6,6 | 2 | 0 |
| 6 | Entrenamiento | 22 | 5 | 7,4 | 7 | 1 |
| 7 | Entrenamiento | 13 | 5 | 6,4 | 3 | 0 |
| 8 | Entrenamiento | 0 | 8 | 7,5 | 3 | 0 |
| 9 | Entrenamiento | 1 | 4 | 6,3 | 0 | 0 |
| 10 | Entrenamiento | 23 | 3 | 6,2 | 6 | 1 |
| 11 | Entrenamiento | 13 | 7 | 8,1 | 2 | 0 |
| 12 | Entrenamiento | 12 | 2 | 5,4 | 9 | 1 |
| 13 | Entrenamiento | 21 | 1 | 8,6 | 8 | 1 |
| 14 | Entrenamiento | 11 | 9 | 8,3 | 0 | 0 |
| 15 | Prueba | 16 | 3 | 7,8 | 9 | 1 |
| 16 | Prueba | 13 | 2 | 5,5 | 9 | 1 |
| 17 | Prueba | 3 | 9 | 6,9 | 2 | 0 |
| 18 | Prueba | 19 | 4 | 8,8 | 2 | 0 |
| 19 | Prueba | 23 | 3 | 5,3 | 8 | 1 |
| 20 | Prueba | 17 | 2 | 8,9 | 2 | 0 |

---

## T27 · ¿Paramos en boxes en esta vuelta?

**Dominio:** Formula 1 · **IA declarada:** Claude

**Situación.** El ingeniero de estrategia de un equipo de Fórmula 1 decide en cada vuelta si para en boxes para intentar el undercut. Cada caso es una vuelta.

**Quién decide.** El ingeniero de estrategia.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = parar en esta vuelta hace ganar la posición al auto de adelante.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Parar y no ganar la posición: se pierde tiempo y quedás atrás de autos lentos.
- Falso negativo (dice NO y era SÍ): No parar cuando funcionaba el undercut: el rival para primero y te pasa.

**Dato de contexto.** El equipo celebra y premia las paradas en boxes más rápidas.

**Datos** (también en `datos/T27.csv`)

| Caso | Conjunto | Degradación del neumático (décimas por vuelta) | Distancia al auto de adelante (s) | Vueltas restantes (cantidad) | Duración de la parada (s) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|---|
| 1 | Entrenamiento | 2,0 | 2,1 | 13 | 2,9 | 0 |
| 2 | Entrenamiento | 1,9 | 2,5 | 24 | 3,4 | 0 |
| 3 | Entrenamiento | 2,1 | 2,7 | 42 | 2,7 | 0 |
| 4 | Entrenamiento | 0,8 | 2,6 | 7 | 2,2 | 0 |
| 5 | Entrenamiento | 4,9 | 0,7 | 31 | 3,4 | 1 |
| 6 | Entrenamiento | 3,9 | 4,8 | 24 | 3,6 | 0 |
| 7 | Entrenamiento | 2,7 | 0,3 | 22 | 2,4 | 1 |
| 8 | Entrenamiento | 5,4 | 1,5 | 7 | 2,0 | 1 |
| 9 | Entrenamiento | 4,1 | 4,1 | 22 | 3,9 | 0 |
| 10 | Entrenamiento | 5,1 | 0,9 | 40 | 2,8 | 1 |
| 11 | Entrenamiento | 0,8 | 2,5 | 9 | 2,3 | 0 |
| 12 | Entrenamiento | 5,9 | 4,1 | 46 | 4,0 | 0 |
| 13 | Entrenamiento | 2,5 | 2,6 | 16 | 2,7 | 0 |
| 14 | Entrenamiento | 5,5 | 3,8 | 36 | 4,0 | 0 |
| 15 | Prueba | 4,6 | 4,2 | 28 | 3,1 | 0 |
| 16 | Prueba | 5,4 | 3,1 | 43 | 2,1 | 1 |
| 17 | Prueba | 4,3 | 3,6 | 45 | 2,5 | 1 |
| 18 | Prueba | 0,7 | 0,9 | 38 | 3,2 | 0 |
| 19 | Prueba | 5,5 | 3,3 | 29 | 3,6 | 1 |
| 20 | Prueba | 4,3 | 1,9 | 37 | 3,1 | 1 |

---

## T28 · ¿El arquero ataja este penal?

**Dominio:** futbol · **IA declarada:** Gemini

**Situación.** El entrenador de arqueros prepara una definición por penales estudiando a los pateadores rivales. Cada caso es un penal de un rival.

**Quién decide.** El entrenador de arqueros.

**La pregunta.** Para cada caso, ¿SÍ o NO? **SÍ** = el arquero ataja el penal.

**Si el sistema se equivoca**
- Falso positivo (dice SÍ y era NO): Prepararse para atajar un penal que entra.
- Falso negativo (dice NO y era SÍ): No estudiar al pateador al que se le podía atajar.

**Datos** (también en `datos/T28.csv`)

| Caso | Conjunto | Penales del pateador al mismo palo (% de su historial) | Carrera de impulso (pasos) | Penales del pateador en su carrera (cantidad) | Resultado real (1 = SÍ) |
|---|---|---|---|---|---|
| 1 | Entrenamiento | 77 | 2 | 7 | 0 |
| 2 | Entrenamiento | 38 | 7 | 17 | 0 |
| 3 | Entrenamiento | 79 | 5 | 1 | 1 |
| 4 | Entrenamiento | 34 | 3 | 8 | 0 |
| 5 | Entrenamiento | 77 | 9 | 32 | 1 |
| 6 | Entrenamiento | 62 | 5 | 19 | 0 |
| 7 | Entrenamiento | 87 | 6 | 32 | 0 |
| 8 | Entrenamiento | 63 | 6 | 21 | 0 |
| 9 | Entrenamiento | 58 | 5 | 4 | 0 |
| 10 | Entrenamiento | 36 | 10 | 3 | 0 |
| 11 | Entrenamiento | 36 | 6 | 24 | 0 |
| 12 | Entrenamiento | 68 | 8 | 32 | 0 |
| 13 | Entrenamiento | 48 | 5 | 23 | 0 |
| 14 | Entrenamiento | 36 | 4 | 5 | 0 |
| 15 | Prueba | 92 | 2 | 24 | 0 |
| 16 | Prueba | 70 | 3 | 10 | 0 |
| 17 | Prueba | 43 | 4 | 25 | 0 |
| 18 | Prueba | 47 | 3 | 1 | 0 |
| 19 | Prueba | 72 | 3 | 14 | 0 |
| 20 | Prueba | 90 | 3 | 18 | 1 |

---
