# Guía de arte · España (misión 1: Belchite, 1937)

Estilo decidido: **isométrico clásico** (tipo Commandos), **noche con luz cálida**, imágenes **generadas con IA** (o por un artista).

El juego ya funciona sin ninguna imagen (todo se dibuja por código). Cada PNG que pongas en la carpeta `assets/` **sustituye automáticamente** a su dibujo por código. Puedes ir añadiéndolas poco a poco. En la pantalla de briefing verás `Gráficos: N de 70 imágenes cargadas`.

---

## 1. Reglas generales (importante para que todo encaje)

| Tema | Regla |
|---|---|
| Proyección | Isométrica 2:1 (dimétrica). Una casilla = rombo de **64×32 px** en el arte. El juego lo reduce al 62,5 % (40×20 px en pantalla). |
| Formato | PNG. Personajes y props con **fondo transparente**. Texturas sin transparencia. |
| Iluminación | Sombreado suave **sobre el propio objeto** (luz arriba-izquierda), pero **sin sombra proyectada en el suelo** ni luces ni oscuridad dentro de la imagen. El juego añade la noche, las farolas y las sombras. |
| Paleta | Tierra, ocre, adobe, piedra gris, teja apagada. Tonos sucios y desaturados; el único color vivo es la luz cálida de las farolas (la pone el juego). |
| Sin símbolos | Sin banderas, escudos ni insignias políticas legibles. Mantiene el foco en los personajes y evita problemas. |
| Época | Aragón, agosto de 1937: pueblo de piedra y adobe, tejas árabes, calles de tierra, plaza empedrada. |

**Truco para que el estilo salga coherente:** genera primero una imagen "de referencia" (una casa) y úsala como imagen de estilo (style reference / image prompt) en todas las demás. Fija siempre la misma semilla (seed) o el mismo modelo/versión.

### El look "táctico clásico" (tipo Commandos), descrito con rasgos
Los juegos de esa época (1998-2003) se ven así porque los sprites se **prerenderizaban en 3D y se pintaban encima a mano**, con estos rasgos. Pídele a la IA justo esto:

| Rasgo | Cómo pedirlo |
|---|---|
| Cámara | Isométrica 2:1, cámara alta (unos 30° sobre el horizonte), sin perspectiva cónica |
| Acabado | Prerenderizado con texturas pintadas a mano, bordes nítidos, mucho detalle pequeño (grietas, tejas sueltas, manchas) |
| Sombreado de forma | Luz suave desde arriba a la izquierda **sobre el propio objeto** (cara izquierda más clara, derecha más oscura). Sin sombra proyectada en el suelo: la pone el juego |
| Personajes | Pequeños y legibles: silueta clara, ropa con 3-4 colores, pliegues marcados, cabeza y manos bien definidas; proporciones realistas, no de dibujo animado |
| Paleta | Tierras, ocres, verdes apagados y rojos de teja. Sombras marrón-rojizas, nunca negro puro. Contraste medio-alto |
| Terreno | Muy trabajado: tierra con piedras, hierba rala, barro, huellas de carro, losas desgastadas. Nada liso |
| Ambiente | Realismo sucio de posguerra: muros desconchados, agujeros de metralla, sacos, alambre |

### Prefijo de prompt común (en inglés, funciona mejor; sin nombres de juegos para poder publicar)
```
pre-rendered isometric tactical stealth game asset, 2:1 isometric camera, hand-painted textures over 3D render, late 1990s PC game look, crisp edges, rich fine detail, soft form shading lit from upper left, no ground cast shadow, muted earthy palette with warm reddish-brown shadows, Spanish Civil War 1937 Aragon village, gritty realism, no text, no flags or political symbols
```
Para personajes añade: `small readable sprite, realistic proportions, strong silhouette, 3/4 view`. Para texturas añade: `seamless tileable, orthographic flat view, heavily detailed and weathered`.

### Herramientas que suelen dar bien este estilo
- **Midjourney** o **Leonardo**: usa la imagen de referencia (`--sref` / Image Guidance) y la misma semilla. Pide cada pieza sobre fondo liso y quita el fondo después.
- **Scenario** o **Stable Diffusion** con un LoRA isométrico: más control para mantener el mismo estilo en las 40 piezas.
- Quitar fondo: remove.bg, Photoshop o `rembg`. Escala después al tamaño de la tabla (genera a 2x o 4x y reduce: da más nitidez).
- Revisa siempre la licencia de uso comercial de la herramienta antes de publicar.

---

## 2. Lista de assets (nombres exactos)

Colócalos en `assets/` con el nombre indicado y extensión `.png`.

### A. Texturas planas (máximo impacto visual, empieza por aquí)
El juego las deforma a la perspectiva isométrica y las repite. Por eso deben ser **vistas planas y sin perspectiva**, y **repetibles (seamless)**.

| Archivo | Tamaño | Qué es |
|---|---|---|
| `tex_ground_dirt.png` | 256×256 | Tierra batida de calle, vista desde arriba, seamless |
| `tex_ground_cobble.png` | 256×256 | Empedrado de la plaza, vista desde arriba, seamless |
| `tex_wall_house.png` | 256×192 | Fachada de casa de piedra/adobe encalado, vista frontal plana, sin ventanas ni puertas, seamless en horizontal, suelo en el borde inferior |
| `tex_wall_church.png` | 256×192 | Muro de sillar de iglesia, gris, vista frontal plana, seamless en horizontal |
| `tex_wall_depot.png` | 256×192 | Muro de almacén: ladrillo/tablas sucias, vista frontal plana, seamless en horizontal |
| `tex_wall_hall.png` | 256×192 | Muro del ayuntamiento: piedra clara con zócalo, vista frontal plana |
| `tex_roof_house_a.png` | 256×256 | Tejas árabes terracota, vista desde arriba, seamless |
| `tex_roof_house_b.png` | 256×256 | Variante más oscura/desgastada de la anterior |
| `tex_roof_church.png` | 256×256 | Tejado de iglesia gris pizarra/teja vieja, vista desde arriba |
| `tex_roof_depot.png` | 256×256 | Tejado de almacén: chapa o teja oscura, vista desde arriba |
| `tex_roof_hall.png` | 256×256 | Tejado del ayuntamiento, teja roja más oscura |

Decoraciones que se pegan sobre las paredes (vista frontal plana, con transparencia):

| Archivo | Tamaño | Qué es |
|---|---|---|
| `door_house.png` | 64×110 | Puerta de madera de casa con marco de piedra |
| `door_depot.png` | 128×110 | Portón doble de almacén, madera y herrajes |
| `window_dark.png` | 48×64 | Ventana con contraventanas, cristal oscuro |
| `window_lit.png` | 48×64 | La misma ventana con luz cálida de vela dentro |

### B. Props (sprites isométricos, fondo transparente)
Anclaje: **centro-abajo**. Para cajas, sacos y camión, el punto inferior del rombo de la base va al borde inferior de la imagen, centrado.

| Archivo | Tamaño | Qué es |
|---|---|---|
| `prop_crate.png` | 64×56 | Caja de madera, ocupa 1×1 casilla |
| `prop_sandbag.png` | 64×44 | Montón de sacos terreros bajo, 1×1 casilla |
| `prop_truck.png` | 160×112 | Camión militar de época, ocupa 3×2 casillas, visto en isométrico con el morro hacia la derecha (este) |
| `prop_lamp.png` | 32×64 | Farola de hierro o farol colgado en poste, **apagada** (la luz la pone el juego) |
| `prop_pole.png` | 32×96 | Poste de teléfono de madera con travesaño, sin cables (los pone el juego) |

### C. Personajes (4 direcciones cada uno, 48×72 px)
Sprites isométricos de pie (sin animar, el juego los desplaza). Fondo transparente. **Pies centrados, dejando ~4 px de margen debajo.**

Direcciones (sufijo del nombre):
- `se` = mira hacia abajo-derecha (hacia la cámara, a la derecha)
- `sw` = mira hacia abajo-izquierda
- `nw` = mira hacia arriba-izquierda (de espaldas)
- `ne` = mira hacia arriba-derecha (de espaldas)

| Personaje | Archivos | Descripción |
|---|---|---|
| Minero asturiano | `char_minero_se/sw/nw/ne.png` | Ropa de trabajo oscura, gorra, bolsa con cartuchos de dinamita, cuchillo al cinto |
| Tirador aragonés | `char_tirador_se/sw/nw/ne.png` | Boina, chaqueta de pana, fusil largo con mira, alpargatas |
| Enlace del pueblo | `char_enlace_se/sw/nw/ne.png` | Ropa sencilla de campo, pañuelo al cuello, zurrón, cuchillo |
| Soldado sublevado | `char_soldado_se/sw/nw/ne.png` | Uniforme caqui, casco o gorrillo, correaje, fusil Mauser. También es el "disfraz" del jugador |
| Ametrallador | `char_ametrallador_se/sw/nw/ne.png` | Igual que el soldado, agachado tras una ametralladora de trípode |
| Cuerpo caído | `cuerpo_soldado.png` (64×32) | Soldado tumbado en isométrico |

> **Atajo:** si de un personaje solo pones una dirección (por ejemplo `char_soldado_se.png`), el juego la usa en espejo para las demás. Es una solución provisional que ya sustituye al dibujo por código. Para empezar rápido, mira [PACK_INICIAL.md](PACK_INICIAL.md).

**Cómo mantener un personaje coherente en 4 direcciones:** genera una *hoja de personaje* con vistas de frente y espalda, y a partir de ella pide cada ángulo con la misma imagen como referencia. Si la IA falla con un ángulo, puedes **voltear horizontalmente** `se↔sw` y `ne↔nw` (conviene que el personaje sea casi simétrico, o aceptar que el fusil cambie de mano).


### D. Misión 2 (Teruel, nieve) · texturas y personaje extra
Mismas reglas que las texturas de la sección A (planas, seamless, sin sombras proyectadas). Ahora hay un ambiente de **invierno nocturno**: paleta azul-grisácea fría, nieve y hielo.

| Archivo | Tamaño | Qué es |
|---|---|---|
| `tex_ground_snow.png` | 256×256 | Nieve virgen vista desde arriba, seamless, con grumos y matices azulados |
| `tex_snow_trodden.png` | 256×256 | Nieve pisada y sucia (andén, caminos), seamless |
| `tex_wall_station.png` | 256×192 | Muro de ladrillo rojizo de estación, vista frontal plana, seamless en horizontal |
| `tex_wall_shed.png` | 256×192 | Muro de tablas grises (cobertizos, cabina de señales, cocheras), vista frontal plana |
| `tex_roof_snow_a.png` | 256×256 | Tejado de casa cubierto de nieve, vista desde arriba, seamless |
| `tex_roof_snow_b.png` | 256×256 | Variante con más teja asomando |
| `tex_roof_station.png` | 256×256 | Tejado de estación: pizarra o teja oscura, con algo de nieve |
| `tex_roof_signal.png` | 256×256 | Tejado de la cabina de señales, verde apagado o chapa |
| `tex_rubble.png` | 256×256 | Escombros de piedra vistos desde arriba (ruinas del convento de San Rafael, misión 1), seamless |
| `char_maquinista_se/sw/nw/ne.png` | 48×72 | Maquinista ferroviario: mono azul, gorra de visera, farol o llave inglesa. 4 direcciones como el resto de personajes |

Prompts (con el prefijo común, añadiendo `winter night, snow, cold blue-grey palette`):
```
seamless tileable texture, orthographic top-down view, untouched snow with small clumps and ice, cold blue tint
seamless tileable texture, orthographic top-down view, trampled dirty snow and mud, footpath
seamless tileable texture, orthographic flat front view, reddish brick railway station wall, soot stains, no windows no doors
seamless tileable texture, orthographic flat front view, weathered grey wooden plank wall, frost
seamless tileable texture, orthographic top-down view, terracotta roof tiles covered in snow, some tiles showing
isometric 2:1 view, full body small game character sprite, standing, facing down-right, 1930s Spanish railway worker, blue overalls, peaked cap, lantern, transparent background
```
> De momento el **tren, la locomotora, los carriles, la torre de agua, la dresina y el foco** se dibujan por código. Si quieres arte para ellos, dímelo y añado soporte de imágenes (`prop_locomotora`, `prop_vagon`, `prop_dresina`...).


### E. Tipos de defensor (aspecto histórico aproximado)
Variantes del soldado enemigo. **Opcionales**: si no pones imágenes de estas, el juego usa el sprite `char_soldado_*`. Detalles y límites de la fidelidad en [UNIFORMES_Y_ARMAS.md](UNIFORMES_Y_ARMAS.md).

| Archivo | Tamaño | Qué es |
|---|---|---|
| `char_guardia_se/sw/nw/ne.png` | 48×72 | Guardia civil: uniforme verde oliva, **tricornio negro**, fusil Mauser, correaje |
| `char_falange_se/sw/nw/ne.png` | 48×72 | Falangista: **camisa azul**, gorro oscuro, fusil Mauser |
| `char_requete_se/sw/nw/ne.png` | 48×72 | Requeté: **boina roja**, uniforme caqui apagado, fusil Mauser |

Prompts (con el prefijo común y `facing down-right ... no insignia, on a plain solid bright green background`):
```
1930s Spanish Civil Guard soldier, olive green uniform, black tricorn hat, bolt-action rifle, leather belts
1930s Spanish militiaman, dark blue shirt, dark side cap, bolt-action rifle, no insignia
1930s Spanish Carlist volunteer, red beret, khaki uniform, bolt-action rifle, no insignia


### F. Retratos de personaje (tarjetas de la parte inferior)
Opcionales. Si existe `portrait_<personaje>.png` en `assets/`, se muestra junto al nombre en la tarjeta del personaje. Se recorta automáticamente a cabeza y hombros (zona central y alta), así que conviene un retrato **de busto, centrado, con fondo blanco o liso**.

| Archivo | Tamaño orientativo | Personaje |
|---|---|---|
| `portrait_minero.png` | 576×800 (la proporción es lo importante) | Minero asturiano |
| `portrait_tirador.png` | igual | Tirador aragonés |
| `portrait_enlace.png` | igual | Enlace del pueblo |
| `portrait_maquinista.png` | igual | Maquinista (misión 2) |

**Diseño del minero (referencia aportada):** hombre de unos 30 años, pelo corto castaño, barba de pocos días, camisa de rayas finas con las mangas remangadas y peto de trabajo con tirantes, manos ásperas. Sin gorra. El sprite del juego sigue este diseño.

Prompt para los demás retratos (mismo estilo que el del minero):
```
painted half-body portrait, 1930s Spanish worker, realistic, muted earthy palette, soft light, plain white background, no text
```
> Si usas una imagen generada o de otra persona, comprueba que tengas derechos para usarla en el juego.

---

## 3. Prompts listos para usar

Sustituye `{PREFIJO}` por el prefijo común de la sección 1.

### Texturas
```
{PREFIJO}, seamless tileable texture, orthographic top-down view, packed dirt street with small pebbles and cart tracks
{PREFIJO}, seamless tileable texture, orthographic top-down view, old worn cobblestone square
{PREFIJO}, seamless tileable texture, orthographic flat front view, whitewashed rough stone and adobe wall of a village house, subtle cracks and stains, no windows no doors, repeats horizontally
{PREFIJO}, seamless tileable texture, orthographic flat front view, grey ashlar limestone church wall, weathered
{PREFIJO}, seamless tileable texture, orthographic flat front view, dirty brick and plank warehouse wall, no windows no doors
{PREFIJO}, seamless tileable texture, orthographic top-down view, terracotta Spanish clay roof tiles, weathered, some moss
```

### Decoración de paredes
```
{PREFIJO}, flat orthographic front view, old wooden village house door in a stone frame, transparent background
{PREFIJO}, flat orthographic front view, large double wooden warehouse door with iron hinges, transparent background
{PREFIJO}, flat orthographic front view, small shuttered window with dark glass, transparent background
{PREFIJO}, flat orthographic front view, small shuttered window with warm candlelight glowing inside, transparent background
```

### Props
```
{PREFIJO}, isometric 2:1 view, wooden supply crate, transparent background
{PREFIJO}, isometric 2:1 view, low stack of sandbags, transparent background
{PREFIJO}, isometric 2:1 view, 1930s military cargo truck with canvas cover, front facing down-right, transparent background
{PREFIJO}, isometric 2:1 view, old wrought-iron street lamp post, unlit, transparent background
{PREFIJO}, isometric 2:1 view, wooden telephone pole with crossbar, no wires, transparent background
```

### Personajes (repite con cada ángulo: facing down-right / down-left / up-left / up-right)
```
{PREFIJO}, isometric 2:1 view, full body small game character sprite, standing, facing down-right, Asturian miner 1937, dark work clothes and cap, satchel of dynamite sticks, knife on belt, transparent background
{PREFIJO}, isometric 2:1 view, full body small game character sprite, standing, facing down-right, Aragonese sharpshooter 1937, beret, corduroy jacket, long scoped rifle, rope sandals, transparent background
{PREFIJO}, isometric 2:1 view, full body small game character sprite, standing, facing down-right, village courier 1937, simple country clothes, neckerchief, shoulder bag, transparent background
{PREFIJO}, isometric 2:1 view, full body small game character sprite, standing, facing down-right, Spanish soldier 1937, khaki uniform, steel helmet, leather ammunition belts, bolt-action rifle, no insignia, transparent background
{PREFIJO}, isometric 2:1 view, small game sprite, soldier kneeling behind a tripod machine gun, 1937, no insignia, transparent background
{PREFIJO}, isometric 2:1 view, small game sprite, fallen soldier lying on the ground, khaki uniform, no insignia, transparent background
```

---

## 4. Flujo de trabajo recomendado

1. Genera las **11 texturas + 4 decoraciones** → es lo que más cambia el aspecto del pueblo. Comprueba que se repiten sin costuras.
2. Genera los **5 props**.
3. Genera los **personajes** (empieza por `se` de los 5 y revisa que combinan con el pueblo).
4. Quita el fondo con tu herramienta habitual (si la IA no da transparencia) y exporta a PNG.
5. Copia los archivos a `assets/` con el **nombre exacto**.
6. Recarga `belchite.html` (la carpeta `assets/` debe estar junto al archivo). Si con doble clic no carga las imágenes, ábrelo desde un servidor local: `python -m http.server` en la carpeta y `http://localhost:8000/belchite.html`.
7. Mira el briefing: debe indicar cuántas imágenes se han cargado.

Si algo se ve mal (escala, anclaje, brillo), dime el archivo y lo ajusto en el código sin que tengas que regenerar nada.

> Revisa la licencia de la herramienta de IA que uses antes de publicar el juego.
