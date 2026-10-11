# Pizarra de Números

Juego de matemáticas y lectura para primero y quinto de básica. La tele muestra la pizarra y lee en voz alta. El celular sirve como control y micrófono: los niños dicen la respuesta y el juego la revisa. Si se equivocan, la pizarra les explica el proceso paso a paso.

## Qué tiene

Cada juego tiene 5 niveles. El nivel sube con 3 aciertos seguidos y baja si fallan seguido. Al primer error reciben una pista; al segundo, la profe explica cómo se hace y les da un ejercicio parecido para practicar.

**Números.** Primero: contar, sumar y restar con objetos. Quinto: suma, resta, multiplicación y división en columna.

**Números para primero:** además de contar, sumar y restar, **Forma el número** usa regletas de colores como en la escuela: ¿qué regleta falta para formar el 6, el 9 o el 10? Si se equivoca, la profe cuenta los cuadritos vacíos uno por uno.

**Letras para primero de básica**

| Juego | Qué practica |
|---|---|
| Mi cuaderno | Abecedario de la A a la Z. Cada letra tiene una lección (mayúscula, minúscula, familia de sílabas y palabras con dibujo) y una práctica de 8 ejercicios como los del cuaderno: reconocer la letra, escuchar la sílaba, sílabas inversas (am, em…), aplausos, leer palabras, dictado, regleta fonológica (contar sonidos) y contar palabras de una oración. **Solo usa palabras con las letras que ya conoce**: vocales y M al inicio. Papá o mamá activan cada letra nueva en «Letras que ya conoce». |
| ¿Con qué empieza? | Ven un dibujo y eligen la vocal o la sílaba inicial (MA ME MI MO MU). Después, la sílaba que falta. |
| Arma la palabra | Ordenan sílabas para formar la palabra del dibujo. |
| Lee y busca | Leen una palabra u oración y eligen su dibujo. |
| Rimas | Eligen la palabra que rima, y al final cuál no rima. |
| Adivinanzas | Adivinanzas populares con dibujos para responder. |
| Cuentos | Cuentos cortos: la profe lee resaltando cada palabra y luego hace preguntas. Con el celular pueden leer ellos y el juego revisa qué palabras dijeron. |
| Trabalenguas | Escuchan despacio y rápido, y luego lo dicen al micrófono. |

**Letras para quinto de básica**

| Juego | Qué practica |
|---|---|
| Lectura | Cuentos, fábulas, una leyenda de Quito, textos sobre Galápagos y el Chimborazo, una carta y un instructivo. Preguntas literales, inferenciales y de vocabulario; si fallan, se marca en el texto dónde está la respuesta. |
| Refranes y dichos | Qué significan, completar el refrán y elegir el refrán para una situación. |
| Ortografía | B/V, M antes de B y P, C/S/Z, G/J, H, LL/Y, R/RR y tildes, siempre con la regla. |
| Vocabulario | Sinónimos, antónimos, palabras en contexto, prefijos y sufijos, analogías. |
| Ordena la oración | Arman oraciones; la profe explica sujeto, predicado y signos. |
| Adivinanzas y trabalenguas | Versiones más largas y difíciles. |

Para agregar cuentos, refranes o palabras, edita `lecturas.js`. Cada texto tiene su nivel (`n`) y las preguntas indican la oración donde está la respuesta (`ev`).

## Archivos

| Archivo | Para qué |
|---|---|
| `index.html` | El juego. Se abre en la tele. |
| `control.html` | El control. Se abre en el celular. |
| `vendor/peerjs.min.js` | Conexión directa tele ↔ celular (PeerJS 1.5.4). |
| `vendor/qrcode.js` | Dibuja el código QR (qrcode-generator 2.0.4). |
| `lecturas.js` | Todo el contenido de lectura: palabras, cuentos, textos, refranes, ortografía. |
| `img/` | Dibujos de las palabras (Twemoji). |

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
   - o el nombre de un botón: «Grande», «Peque», «Números», «Letras», «Sumar»;
   - en los juegos de opciones, la respuesta o su letra: «mu», «la be»;
   - en cuentos y trabalenguas, el texto completo en voz alta: el juego marca en verde lo que leyeron bien y en rosado lo que faltó.

El código de la tele se guarda, así que el celular se reconecta solo la próxima vez. Pueden conectarse dos celulares a la vez, uno por niño.

## Si no se escucha la voz

La voz la produce el navegador que tiene abierto el juego. Hay dos causas comunes:

1. **Falta un toque en la tele.** Los navegadores no dejan hablar a una página hasta que alguien presiona algo en esa misma pantalla. Si todo se controla desde el celular, aparece un aviso amarillo: presiona **OK en el control remoto de la tele** una vez. Mientras tanto, el celular dice las frases.
2. **El navegador de la tele no tiene voz** (pasa en muchos navegadores de televisores). Entra a **Probar sonido** en la pantalla de inicio: muestra si hay voz, cuántas voces en español tiene y el resultado de una prueba. Si no tiene voz:
   - abre el juego en **Chrome del celular** y usa **Enviar pantalla** a la tele: la imagen y la voz salen por la tele;
   - o deja que hable el celular: en el control, el botón **Voz en el celular** tiene tres modos: «solo si la tele no habla» (predeterminado), «siempre» y «apagada».

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

## Créditos

Dibujos: [Twemoji](https://github.com/jdecked/twemoji), © Twitter, Inc. y colaboradores, licencia CC-BY 4.0. Cuentos, textos y preguntas: originales; refranes, adivinanzas y trabalenguas: tradición popular.
