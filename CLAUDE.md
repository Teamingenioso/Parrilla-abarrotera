# Parrilla de contenido · Abarrotera Sánchez

Página estática: `index.html`. Las piezas viven en `<script type="application/json" id="piezas">`.

## Regla fija: botón de Notion en todas las piezas

Cada pieza (las actuales y toda nueva de aquí en adelante) lleva su botón a la tarea de Notion:

- `"nlabel"`: texto del botón, con el código de la tarea. Ejemplo: `"VER DABS-NOV-01 EN NOTION"`.
- `"nurl"`: enlace a la tarea en la base Contenido, en la forma `https://app.notion.com/<id de 32 caracteres>`.

El modal (`open(i)`) lo dibuja con la clase `vid`, igual que los botones de Facebook y Drive, justo después de ellos.

Al agregar una pieza nueva o cambiar de tarea, buscar su tarea en Notion (base Contenido, por código o por nombre) y llenar `nlabel` y `nurl` en el mismo cambio. Si de verdad no existe la tarea, avisar en vez de dejar la pieza sin botón.

## Estados y colores (siempre los mismos en leyenda, tablero, calendario y anillo)

| Estado | Color | Notion | `cls` |
|---|---|---|---|
| Publicado | verde `#22c55e` | Finalizada + casilla Publicado | `pub` |
| Terminado | violeta `#8b5cf6` | Finalizada, sin marcar publicada | `fin` |
| En revisión | ámbar `#f59e0b` | En revisión | `apr` |
| En producción | azul `#3b82f6` | En curso | `rev` |
| Sin empezar | rojo `#e5484d` | Sin empezar | `sin` |

El tablero tiene una columna por estado (Terminado y Publicado van separados). Si una pieza ya salió en Facebook aunque Notion no tenga la casilla, se deja como Publicado. Al sincronizar con Notion se actualizan estado y fecha; el anillo y el resumen de arriba se recalculan a mano.

## Publicación

Cambios en una rama; cuando estén listos pasan a `main` sin preguntar. El sitio sale de `main` en GitHub Pages.
