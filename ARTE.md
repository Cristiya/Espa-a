# Guía de arte · España (misión 1: Belchite, 1937)

Estilo decidido: **isométrico clásico** (tipo Commandos), **noche con luz cálida**, imágenes **generadas con IA** (o por un artista).

El juego ya funciona sin ninguna imagen (todo se dibuja por código). Cada PNG que pongas en la carpeta `assets/` **sustituye automáticamente** a su dibujo por código. Puedes ir añadiéndolas poco a poco. En la pantalla de briefing verás `Gráficos: N de 41 imágenes cargadas`.

---

## 1. Reglas generales (importante para que todo encaje)

| Tema | Regla |
|---|---|
| Proyección | Isométrica 2:1 (dimétrica). Una casilla = rombo de **64×32 px** en el arte. El juego lo reduce al 62,5 % (40×20 px en pantalla). |
| Formato | PNG. Personajes y props con **fondo transparente**. Texturas sin transparencia. |
| Iluminación | **Neutra y plana**, sin sombras proyectadas ni luces dentro de la imagen. El juego añade la oscuridad, las farolas y las sombras. |
| Paleta | Tierra, ocre, adobe, piedra gris, teja apagada. Tonos sucios y desaturados; el único color vivo es la luz cálida de las farolas (la pone el juego). |
| Sin símbolos | Sin banderas, escudos ni insignias políticas legibles. Mantiene el foco en los personajes y evita problemas. |
| Época | Aragón, agosto de 1937: pueblo de piedra y adobe, tejas árabes, calles de tierra, plaza empedrada. |

**Truco para que el estilo salga coherente:** genera primero una imagen "de referencia" (una casa) y úsala como imagen de estilo (style reference / image prompt) en todas las demás.

### Prefijo de prompt común (en inglés, funciona mejor)
```
hand-painted 2D game asset, muted earthy palette, Spanish Civil War era 1937, Aragon village, gritty realistic painted style like Commandos 2 and Desperados, flat neutral lighting, no cast shadows, no text, no flags or political symbols
```

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

**Cómo mantener un personaje coherente en 4 direcciones:** genera una *hoja de personaje* con vistas de frente y espalda, y a partir de ella pide cada ángulo con la misma imagen como referencia. Si la IA falla con un ángulo, puedes **voltear horizontalmente** `se↔sw` y `ne↔nw` (conviene que el personaje sea casi simétrico, o aceptar que el fusil cambie de mano).

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
