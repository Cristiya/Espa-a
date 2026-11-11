# Pack inicial: 6 imágenes para ver el cambio ya

Objetivo: con solo **6 imágenes** vas a notar un salto claro en el aspecto del pueblo y de los personajes. El resto de piezas (hasta 53) pueden venir después. Todo lo que falte se sigue dibujando por código.

Las medidas, el estilo completo y el resto de prompts están en [ARTE.md](ARTE.md). Esta ficha es el camino corto.

## Antes de empezar (2 minutos)
1. Elige una herramienta de imágenes (Midjourney, Leonardo, Scenario, DALL·E, Stable Diffusion...). Mira que su licencia permita uso comercial si vas a publicar el juego.
2. Copia este **prefijo de estilo** y úsalo delante de todos los prompts:

```
pre-rendered isometric tactical stealth game asset, 2:1 isometric camera, hand-painted textures over 3D render, late 1990s PC game look, crisp edges, rich fine detail, soft form shading lit from upper left, no ground cast shadow, muted earthy palette with warm reddish-brown shadows, Spanish Civil War 1937 Aragon village, gritty realism, no text, no flags or political symbols
```

3. Genera siempre a un tamaño mayor (por ejemplo el doble) y reduce después a la medida de la tabla: queda más nítido.

## Las 6 imágenes

| # | Archivo (nombre exacto) | Medida | Dónde se nota |
|---|---|---|---|
| 1 | `tex_wall_house.png` | 256×192 | Las paredes de todas las casas |
| 2 | `tex_roof_house_a.png` | 256×256 | Los tejados rojos de las casas |
| 3 | `tex_ground_dirt.png` | 256×256 | El suelo de toda la misión 1 |
| 4 | `char_soldado_se.png` | 48×72 | Los soldados enemigos (y tu disfraz) |
| 5 | `char_minero_se.png` | 48×72 | Tu minero asturiano |
| 6 | `prop_crate.png` | 64×56 | Las cajas de madera |

### Prompts

**1. Pared** (vista frontal plana, repetible en horizontal)
```
{PREFIJO}, seamless tileable texture, orthographic flat front view, whitewashed rough stone and adobe wall of a village house, subtle cracks and stains, no windows no doors, repeats horizontally
```

**2. Tejado** (vista desde arriba, repetible)
```
{PREFIJO}, seamless tileable texture, orthographic top-down view, terracotta Spanish clay roof tiles, weathered, some moss
```

**3. Suelo** (vista desde arriba, repetible)
```
{PREFIJO}, seamless tileable texture, orthographic top-down view, packed dirt street with small pebbles and cart tracks
```

**4. Soldado** (fondo transparente o liso para quitarlo después)
```
{PREFIJO}, isometric 2:1 view, full body small game character sprite, standing, facing down-right, Spanish soldier 1937, khaki uniform, steel helmet, leather ammunition belts, bolt-action rifle, no insignia, transparent background
```

**5. Minero**
```
{PREFIJO}, isometric 2:1 view, full body small game character sprite, standing, facing down-right, Asturian miner 1937, dark work clothes and cap, satchel of dynamite sticks, knife on belt, transparent background
```

**6. Caja**
```
{PREFIJO}, isometric 2:1 view, wooden supply crate, transparent background
```

## Dónde guardarlas
En la carpeta `assets/`, junto a `index.html`, con el **nombre exacto** de la tabla (en minúsculas, extensión `.png`). Recarga la página: el briefing indica cuántas imágenes se han cargado ("Gráficos: 6 de 53...").

## Trucos
- **Personajes: basta una sola dirección.** Si solo pones `char_soldado_se.png`, el juego la **voltea en espejo** para las otras direcciones (sw, ne, nw). No será perfecto (el fusil cambiará de mano y de espaldas se verá igual), pero ya sustituye al dibujo por código. Más adelante puedes añadir las otras tres direcciones.
- Si la pared o el tejado muestran **líneas o costuras** al repetirse, pide "seamless" con más insistencia o usa la función de teselado de tu herramienta.
- Si alguna imagen se ve **demasiado grande, pequeña o desplazada** en el juego, dime el nombre del archivo y lo ajusto en el código, sin que tengas que regenerarla.

## Y después
Pásame cómo queda (una captura basta) y vemos juntos qué piezas ampliar primero: suelo y paredes de la misión 2, el resto de direcciones de los personajes, y los props (camión, farola, poste).
