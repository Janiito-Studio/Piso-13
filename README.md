# PISO 13 — DEMO PÚBLICA (solo planta 1)

------------------------------------------------------------------------
1. ESPAÑOL — INFORMACIÓN DE LA DEMO
------------------------------------------------------------------------

**Piso 13** es un juego narrativo de terror psicológico en pixel art,
dirigido por **Jan Lamarca** y desarrollado por **[Janiito Studio](https://studio.janiito.com)**.

Esta carpeta contiene una demo pública del juego, no el juego completo.
En esta versión se pueden jugar la recepción, la cabina del ascensor y el
rellano del portero. Al llegar a ese punto, la demo termina.

El juego completo está disponible en:

**[janiito.com/piso13](https://janiito.com/piso13)**

## Qué hay dentro

| Archivo | Contenido |
|---|---|
| `index.html` | La página principal de la demo. |
| `js/piso13-demo.*.js` | El juego empaquetado, con el motor y solo la planta 1. |
| `css/style.css` | Los estilos principales del juego. |
| `css/demo.css` | Los estilos y avisos específicos de la demo. |
| `assets/` | Iconos, logotipos y otros recursos visuales. |
| `README.md`, `AVISO-LEGAL.md`, `LICENSE` | Documentación, aviso legal y licencia. |

## Qué no hay en esta versión

El contenido siguiente no forma parte de esta demo:

- Las plantas **2 a 12** y sus diálogos.
- El **piso 13**, los tres finales y el resto de la historia.
- Los recuerdos, las misiones, el evento del bombero y la escalera de
  emergencia.
- Los minijuegos.
- La canción con licencia de terceros, *«My Gal»*.
- El código fuente legible. El JavaScript está minificado y los diálogos
  están cifrados.

La demo utiliza el **MODO STREAMER**, que genera la música directamente en
el navegador.

No hay contenido oculto que se pueda desbloquear. Las plantas, escenas y
archivos que no pertenecen a esta versión no están incluidos en el paquete.

## Cómo jugar en local

La demo es una página estática. Puedes abrir `index.html` directamente o
servir la carpeta con Python:

```bash
python3 -m http.server 8080 --directory .
```

**Dominios permitidos:**

- `*.janiito.com`
- `localhost`
- `127.0.0.1`
- `*.e2b.app`
- `file://`

Si abres la demo desde otro dominio, aparecerá el aviso de *copia no
verificada* y el juego no permitirá jugar. Esto ocurre porque la clave de
los diálogos depende del dominio desde el que se carga la demo.

Los dominios `e2b.app` y `file://` también están permitidos para realizar
pruebas y utilizar el visor de desarrollo, que carga la demo dentro de un
`iframe`.

## Cómo está protegida

La demo incluye varias comprobaciones para dificultar las copias y las
modificaciones no autorizadas:

1. **Diálogos cifrados.** Los textos de cada idioma se guardan en bloques
   cifrados con ChaCha20 y codificados en base64. Cada compilación utiliza
   una clave y un nonce nuevos.

2. **Clave dependiente del dominio.** La clave se forma con varios
   fragmentos repartidos por el archivo y una máscara que depende del
   dominio. Si la demo se abre desde otro sitio, la clave no coincide.

3. **Comprobación de los datos.** El empaquetador firma el bloque cifrado.
   Si alguien modifica los diálogos, la comprobación deja de coincidir.

4. **Comprobación del archivo JavaScript.** La demo comprueba que el archivo
   JavaScript tenga la misma huella que tenía al generarse. Si se modifica,
   aunque solo sea un espacio o un salto de línea, la demo lo detecta.

5. **Contenido fuera del paquete.** Las plantas y los finales que no forman
   parte de esta versión no se incluyen en los archivos publicados.

6. **Avisos dentro del juego.** La demo muestra una cinta de DEMO en el
   título, una marca de agua durante la partida y un aviso al llegar al
   final.

7. **Identificador de compilación.** Cada versión tiene un identificador
   propio (`P13D-…`) que aparece en la consola y en el aviso final.

8. **Guardado separado.** La demo utiliza nombres de guardado propios
   (`p13demo.*`) para no mezclar sus partidas con las del juego completo.

Nada de esto es completamente infalible. Todo lo que se ejecuta en un
navegador puede acabar siendo analizado. La finalidad de estas medidas es
dificultar las copias y evitar publicar en esta demo el contenido que no
forma parte de ella.

## Publicación de la demo

Esta demo no está autorizada para su publicación, redistribución o
alojamiento por terceros.

Sin autorización previa y por escrito de Jan Lamarca o Janiito Studio, no
puedes:

- Publicar la demo completa o una parte de ella en otro dominio.
- Subirla a otro repositorio, servidor, portal o tienda digital.
- Crear una copia, espejo o versión descargable de la demo.
- Redistribuir sus archivos, el paquete JavaScript o sus recursos.
- Alojarla dentro de otra página mediante `iframe`, `embed` u otro sistema
  similar.
- Modificarla y volver a publicarla como si fuera una versión oficial.
- Venderla, monetizarla o incluirla en productos, cursos, recopilatorios o
  servicios de pago.
- Eliminar los avisos, créditos, logotipos, marcas de agua o sistemas de
  identificación de la demo.

Puedes enlazar a la demo o a sus páginas oficiales, pero no copiarla,
publicarla ni mostrarla desde un sitio externo sin autorización.

Si tienes autorización para preparar una versión concreta, la carpeta debe
subirse sin modificar sus archivos generados. El servidor debe entregar el
archivo `.js` exactamente igual que fue creado.

En Cloudflare, desactiva para ese archivo Auto Minify, Rocket Loader y
cualquier otra opción que pueda modificar el JavaScript. Tampoco introduzcas
código de analítica dentro del archivo.

No cambies manualmente el nombre del archivo `.js`, porque contiene la
huella de la compilación. Para generar una versión nueva, utiliza:

```bash
npm run build:demo
```

## Licencia

**Copyright © 2026 Jan Lamarca (Janiito Studio). Todos los derechos reservados.**

Se permite leer, ejecutar y estudiar esta demo dentro de los límites
permitidos por la ley.

No se permite publicar, redistribuir, alojar, vender, modificar y volver a
publicar, incrustar en páginas de terceros ni incorporar esta demo o sus
archivos a otro proyecto sin autorización previa y por escrito.

Tampoco se permite utilizar el código, los diálogos, la historia, los
personajes o los recursos protegidos de la demo para entrenar modelos de
inteligencia artificial cuando dicho uso requiera autorización.

Para más información, consulta:

- [`LICENSE`](./LICENSE)
- [`AVISO-LEGAL.md`](./AVISO-LEGAL.md)

- **Juego completo:** [janiito.com/piso13](https://janiito.com/piso13)
- **Estudio:** [studio.janiito.com](https://studio.janiito.com)
- **Contacto:** [piso13@janiito.com](mailto:piso13@janiito.com)

------------------------------------------------------------------------
2. ENGLISH — DEMO INFORMATION
------------------------------------------------------------------------

**Piso 13** is a pixel-art psychological horror narrative game directed by
**Jan Lamarca** and developed by **[Janiito Studio](https://studio.janiito.com)**.

This folder contains a public demo of the game, not the complete game.
This version includes the reception area, the elevator cabin and the
caretaker’s landing. The demo ends when that point is reached.

The complete game is available at:

**[janiito.com/piso13](https://janiito.com/piso13)**

## What is included

| File | Contents |
|---|---|
| `index.html` | The demo’s main page. |
| `js/piso13-demo.*.js` | The packaged game, including the engine and floor 1 only. |
| `css/style.css` | The game’s main styles. |
| `css/demo.css` | The demo-specific styles and notices. |
| `assets/` | Icons, logos and other visual resources. |
| `README.md`, `AVISO-LEGAL.md`, `LICENSE` | Documentation, legal notice and license. |

## What is not included

The following content is not part of this demo:

- Floors **2 to 12** and their dialogue.
- The **13th floor**, the three endings and the rest of the story.
- Memories, missions, the firefighter event and the emergency staircase.
- The minigames.
- The third-party licensed song *“My Gal”*.
- Readable source code. The JavaScript is minified and the dialogue is
  encrypted.

The demo uses **STREAMER MODE**, which generates the music directly in the
browser.

There is no hidden content that can be unlocked. The floors, scenes and
files that do not belong to this version are not included in the package.

## How to play locally

The demo is a static webpage. You can open `index.html` directly or serve
the folder with Python:

```bash
python3 -m http.server 8080 --directory .
```

**Allowed domains:**

- `*.janiito.com`
- `localhost`
- `127.0.0.1`
- `*.e2b.app`
- `file://`

If you open the demo from another domain, a *copy not verified* notice will
appear and the game will not allow play. This happens because the dialogue
key depends on the domain from which the demo is loaded.

The `e2b.app` and `file://` domains are also allowed for testing and for
using the development viewer, which loads the demo inside an `iframe`.

## How it is protected

The demo includes several checks intended to make unauthorized copying and
modification more difficult:

1. **Encrypted dialogue.** The text for each language is stored in
   ChaCha20-encrypted blocks encoded in base64. Each build uses a new key
   and nonce.

2. **Domain-dependent key.** The key is formed from several fragments
   distributed throughout the file and a mask based on the domain. If the
   demo is opened from another site, the key does not match.

3. **Data verification.** The encrypted block is signed during packaging.
   If someone modifies the dialogue, the verification no longer matches.

4. **JavaScript file verification.** The demo checks that the JavaScript
   file has the same hash it had when it was generated. If it is modified,
   even by a single space or line break, the demo detects it.

5. **Content excluded from the package.** Floors and endings that are not
   part of this version are not included in the published files.

6. **In-game notices.** The demo displays a DEMO banner on the title screen,
   a watermark during gameplay and a notice when the demo ends.

7. **Build identifier.** Each version has its own identifier (`P13D-…`),
   which appears in the console and in the final notice.

8. **Separate save data.** The demo uses separate save names (`p13demo.*`)
   so that its saves do not mix with those from the complete game.

None of these measures is completely infallible. Anything that runs in a
browser can eventually be analyzed. Their purpose is to make copying more
difficult and, above all, to avoid publishing content that is not part of
this demo.

## Publishing the demo

This demo is not authorized for publication, redistribution or hosting by
third parties.

Without prior written permission from Jan Lamarca or Janiito Studio, you
may not:

- Publish the complete demo or any part of it on another domain.
- Upload it to another repository, server, portal or digital store.
- Create a copy, mirror or downloadable version of the demo.
- Redistribute its files, JavaScript package or resources.
- Host it inside another webpage through an `iframe`, `embed` or similar
  system.
- Modify it and republish it as if it were an official version.
- Sell, monetize or include it in products, courses, compilations or paid
  services.
- Remove the demo’s notices, credits, logos, watermarks or identification
  systems.

You may link to the demo or its official pages, but you may not copy,
publish or display it from an external website without authorization.

If you are authorized to prepare a specific version, the folder must be
uploaded without modifying its generated files. The server must deliver the
`.js` file exactly as it was created.

On Cloudflare, disable Auto Minify, Rocket Loader and any other option that
may modify the JavaScript file. Do not inject analytics code into the file.

Do not manually rename the `.js` file, as its name contains the build hash.
To generate a new version, run:

```bash
npm run build:demo
```

## License

**Copyright © 2026 Jan Lamarca (Janiito Studio). All rights reserved.**

You may read, run and study this demo within the limits permitted by law.

You may not publish, redistribute, host, sell, modify and republish, embed
on third-party websites, or incorporate this demo or its files into another
project without prior written permission.

You may not use the demo’s code, dialogue, story, characters or protected
resources to train artificial-intelligence models where such use requires
authorization.

For more information, see:

- [`LICENSE`](./LICENSE)
- [`AVISO-LEGAL.md`](./AVISO-LEGAL.md)

- **Complete game:** [janiito.com/piso13](https://janiito.com/piso13)
- **Studio:** [studio.janiito.com](https://studio.janiito.com)
- **Contact:** [piso13@janiito.com](mailto:piso13@janiito.com)