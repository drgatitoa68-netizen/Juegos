# Pizarra de Números

Juego de matemáticas para primero y quinto de básica. La tele muestra la pizarra y lee en voz alta. El celular sirve como control y micrófono: los niños dicen la respuesta y el juego la revisa. Si se equivocan, la pizarra les explica el proceso paso a paso.

## Archivos

| Archivo | Para qué |
|---|---|
| `index.html` | El juego. Se abre en la tele. |
| `control.html` | El control. Se abre en el celular. |
| `vendor/peerjs.min.js` | Conexión directa tele ↔ celular (PeerJS 1.5.4). |
| `vendor/qrcode.js` | Dibuja el código QR (qrcode-generator 2.0.4). |

No hay backend ni base de datos. El progreso se guarda en el navegador de la tele.

## Publicarlo (GitHub Pages, gratis)

El micrófono del celular solo funciona en una página con **HTTPS**. GitHub Pages lo da sin costo.

1. Crea un repositorio, por ejemplo `juegos`, y sube estos archivos tal cual (con la carpeta `vendor`).
2. En el repo: **Settings → Pages → Build and deployment → Deploy from a branch → `main` / `root`**.
3. En uno o dos minutos queda en `https://drgatitoa68-netizen.github.io/juegos/`.

## Usarlo

1. **Tele:** abre `https://drgatitoa68-netizen.github.io/juegos/` en el navegador de la tele y guárdalo en favoritos. En Android TV o Google TV puedes instalar un navegador como TV Bro.
2. **Celular:** escanea el QR que aparece en la tele, o abre `control.html` y escribe el código de 5 números.
3. La primera vez, Chrome pide permiso para el micrófono: acéptalo.
4. Toca **«Toca y habla»** y di:
   - el número de la respuesta: «ochenta y cinco», «12»;
   - o un comando: «siguiente», «otra vez», «ayuda», «comprobar», «atrás», «salir»;
   - o el nombre de un botón: «Grande», «Peque», «Sumar», «Dividir».

El código de la tele se guarda, así que el celular se reconecta solo la próxima vez. Pueden conectarse dos celulares a la vez, uno por niño.

## Cómo funciona la conexión

- La tele se registra como `pizarra-numeros-<código>` en el servidor público de PeerJS (`0.peerjs.com`). Ese servidor solo presenta los dos dispositivos.
- Los mensajes van directo de la tele al celular por WebRTC.
- La tele envía al celular los botones de la pantalla actual. El celular manda de vuelta qué se tocó o qué se dijo.
- El reconocimiento de voz lo hace Chrome en el celular y necesita internet. La tele interpreta el texto y responde o pulsa el botón que corresponde.

**Servidor propio (opcional).** Si el servidor público falla, levanta uno:

```
npx peer --port 9000
```

Luego abre `index.html?peer=tu-servidor:9000`. El QR ya incluye ese parámetro para el celular.

## Si algo no funciona

- **El celular dice «No encuentro la tele»:** revisa que el juego esté abierto en la tele y que el código sea el mismo.
- **«El micrófono está bloqueado»:** en Chrome, toca el candado de la barra de direcciones → Permisos → Micrófono → Permitir.
- **La tele dice «Celular: sin conexión»:** la tele no tiene internet. Se puede seguir jugando con el control remoto (flechas y OK).
