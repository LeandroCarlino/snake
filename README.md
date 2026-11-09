# Snake

El clásico Snake en canvas, con siete temas visuales, niveles con obstáculos y audio sintetizado en vivo (sin archivos de sonido).

**Demo:** https://leandrocarlino.github.io/snake/

## Cómo se juega

| Acción | Teclado | Táctil |
|---|---|---|
| Mover | Flechas o WASD | Swipe o cruzeta en pantalla |
| Pausa / menú | `Esc` | — |
| Gamepad | Cruceta o stick izquierdo | — |

- **Modo niveles**: cada nivel pide más comida y suma obstáculos fijos y móviles. El progreso queda guardado y podés empezar en cualquier nivel desbloqueado.
- **Modo infinito**: sin niveles, la velocidad sube con cada punto.
- **Ajustes**: idioma (es/en), tema (7), partículas, volumen y música.

## Qué cambió en este pase

- **`user-scalable=no` eliminado**: el viewport bloqueaba el zoom, un problema de accesibilidad serio.
- **La comida ya no aparece debajo de la serpiente** ni sobre obstáculos móviles (antes solo miraba los fijos), y el bucle de búsqueda tiene tope para no colgarse con el tablero lleno.
- **Pausa automática al cambiar de pestaña**: antes volvías y estabas muerto.
- **`<html lang>` se actualiza** al cambiar de idioma (antes quedaba siempre en `es`).
- **Cruzeta táctil** para móvil, además del swipe.
- **`localStorage` protegido**: en modo privado o con la cuota llena, el juego ya no se rompe.
- **Foco visible** en botones, enlaces y controles (antes no había).
- **Peso y altura con `100dvh`** para que no salte con la barra del navegador móvil.
- Metadatos: descripción, `theme-color`, Open Graph, favicon y un título real.

## Estructura

```
index.html   # HUD, menú y canvas
style.css    # temas por variables CSS, menú y cruzeta táctil
game.js      # motor: bucle, colisiones, obstáculos, audio, i18n
favicon.svg
```

Todo el juego vive en `game.js` sin dependencias ni build step. Los temas se aplican como variables CSS (`--bg-color`, `--accent`, …) y el canvas lee los mismos colores desde `themeData`.

## Correrlo

Es estático: alcanza con abrir `index.html`, o levantar un servidor.

```bash
npx serve .
# o
python -m http.server 8000
```

## Créditos

Creado por [Leandro Carlino](https://www.linkedin.com/in/leandro-carlino/) como práctica, con ayuda de Gemini 3.1 Pro.
