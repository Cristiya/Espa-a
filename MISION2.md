# Misión 2 · La estación (Teruel, diciembre de 1937)

*Documento de diseño. **Programada** en `index.html` con las decisiones tomadas: el tren se desvía con la palanca, el maquinista es obligatorio y las huellas en la nieve son una mecánica central.*

## Contexto histórico
La batalla de Teruel empezó el 15 de diciembre de 1937, en pleno invierno, con nevadas y un frío extremo. La ofensiva republicana rodeó la ciudad, que cayó en manos republicanas en enero de 1938 y fue recuperada por los sublevados en febrero. Las comunicaciones por ferrocarril fueron clave para llevar refuerzos y munición.

Marco real, misión ficticia: una estación pequeña de la línea de Teruel, que no existió tal cual.

## Resumen
**Madrugada del 14 al 15 de diciembre.** Un tren blindado con munición y refuerzos llegará al amanecer a una estación del frente. El grupo debe infiltrarse en la nieve, tomar el control de la cabina de señales, desviar el tren a una vía muerta y volar los vagones de munición. Después, huir en una dresina por la vía.

**Tono:** frío, silencio, vapor, nieve que delata las huellas. Es la misión "de ingenio": menos fuerza, más usar el entorno.

## El equipo (4 personajes)
| Personaje | Habilidades |
|---|---|
| Minero asturiano | Dinamita, cuchillo |
| Tirador aragonés | Fusil, apaga focos y farolas |
| Enlace del pueblo | Piedras, cuchillo, corta cables |
| **Maquinista** (nuevo, se libera en la misión) | Maneja palancas de agujas y la dresina, ve el horario del tren. Con su mono de ferroviario **pasa desapercibido dentro de la zona de la estación** |

El maquinista empieza **preso en el calabozo de la estación**. Rescatarlo es obligatorio: sin él no se puede conducir la dresina. Es el momento Commandos de la misión: el equipo crece a mitad de partida.

## Objetivos
**Principales**
1. Conseguir la llave del calabozo (la lleva el jefe de estación) y liberar al maquinista.
2. Entrar en la **cabina de señales** y poner las agujas para desviar el tren al apartadero.
3. Cuando el tren entre en el apartadero, volar los **vagones de munición**.
4. Escapar los cuatro en la **dresina** por la vía.

**Opcionales**
- Cortar el telégrafo (los guardias no pueden pedir refuerzos).
- Robar el horario de trenes del despacho (da 60 segundos extra de margen).
- Apagar el foco giratorio (el tirador, de un disparo).

## Mapa (esquema)
```
  N · colina y zanja de entrada (los tres empiezan aquí)
 ───────────────────────────────────────────────────────────────────────
  [Casas del pueblo]     [Almacén de mercancías]     [TORRE DE AGUA + ametralladora]
 ═════════════ VÍA PRINCIPAL (el tren llega por el oeste) ═══════════════════►
  [ESTACIÓN: andén,         [CABINA DE SEÑALES        
   despacho, calabozo]       palanca de agujas]
 ═════════════ APARTADERO / VÍA MUERTA (vagones de munición) ═══════╗
  [Cocheras + DRESINA]                       [Foco giratorio]
 ───────────────────────────────────────────────────────────────────────
  S · camino de salida alternativo, a pie, más largo y peligroso
```
Tamaño previsto: igual que la misión 1 (50 × 32 casillas) o algo mayor (60 × 36).

## Enemigos
| Quién | Dónde | Notas |
|---|---|---|
| 4 patrullas | Calles, andén y vías | Rutas largas, se cruzan en la estación |
| Jefe de estación | Despacho | Lleva la llave. Si lo eliminas sin ruido, la cabina queda libre |
| Ametrallador | Torre de agua | Domina la vía principal. Se le baja con el fusil o por detrás |
| Foco giratorio | Tejado de las cocheras | Cono de luz fuerte que barre; si te toca, alarma inmediata |
| Dotación del tren blindado | Llega con el tren | Si llegas a este momento sin haber volado nada, la misión se complica mucho |

## Mecánicas nuevas
- **Huellas en la nieve.** Cada personaje deja pisadas. Un centinela que las ve las sigue hasta el último punto. Solo se borran con el paso de los minutos, o pisando la vía o el andén, donde no se marcan.
- **Palancas y agujas.** La cabina de señales contiene la palanca. Cambiarla redirige el tren cuando llegue.
- **Tren con horario.** Una cuenta atrás de unos 6 minutos. Cuando llega, entra por la vía que tengas puesta.
- **Foco giratorio.** Un cono que gira y no se bloquea con la luz de las farolas.
- **Ropa de ferroviario.** Los guardias ignoran a quien lleva el mono dentro de la zona de la estación, pero no en el campo abierto.
- **Dresina.** Salida final: todos los vivos suben y la misión termina con una pequeña escena.
- **Frío.** Aliento visible, ventiscas ocasionales que reducen el campo de visión de todos (también el de los guardias) durante unos segundos.

## Cronología
1. **0:00** Entrada por la zanja. Primeras patrullas.
2. **1:30** Despacho: jefe de estación y llave.
3. **2:30** Calabozo: sale el maquinista.
4. **3:30** Cabina de señales: palanca y, si quieres, telégrafo.
5. **6:00** Llega el tren al apartadero.
6. **6:30** Se dinamita la munición.
7. **7:00** Dresina y huida. Los guardias reaccionan a la explosión.

## Dificultad (cómo se siente)
- **Fácil:** el tren tarda más, las huellas duran menos y el foco es más lento.
- **Normal:** como está descrito.
- **Difícil:** el tren llega antes, hay un guardia más en la torre y el foco es rápido.

## Arte nuevo necesario
Se suma a la guía de arte de [ARTE.md](ARTE.md): suelo de nieve y nieve pisada, tejados nevados, ladrillo de estación, vía (carril y traviesas), locomotora, vagón de munición, dresina, torre de agua, cabina de señales, foco, semáforo, barriles, traviesas apiladas y el personaje del maquinista (4 direcciones).

## Trabajo técnico (orden recomendado)
1. **Separar las misiones en datos.** Hoy todo está pensado para Belchite. Hay que mover mapa, enemigos, objetivos y equipo a una definición de misión para poder tener varias.
2. **Cuarto personaje** que entra a mitad de partida.
3. **Vías y tren** como objeto móvil.
4. **Huellas, foco giratorio, palancas.**
5. **Arte nuevo** (la parte que depende de ti).
6. Pruebas y equilibrio.

## Decisiones que cambian el diseño
1. ¿Prefieres que **el tren se desvíe** (más ingenio) o que **se vuele directamente** (más sencillo)?
2. ¿El maquinista **obligatorio** (más Commandos) u opcional (más libre)?
3. ¿Las **huellas en la nieve** como mecánica central o solo como adorno visual?
