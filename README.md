# HEARTS Arcade: toma de presión

Juego para proveedores de salud: 60 segundos de retos rápidos sobre la técnica correcta de toma de presión y los valores de referencia. Funciona en el navegador del celular (iOS y Android) y en computadora.

Archivos:

- `index.html`: el juego completo, en un solo archivo.
- `Codigo-Apps-Script.gs`: el código que guarda los resultados en una hoja de Google, que después se descarga como Excel.

## Parte 1. Hoja de resultados en Google (unos 10 minutos)

Hazla primero, porque te da la dirección que necesita el juego. Si no quieres ranking ni Excel, sáltala: el juego funciona igual.

1. En Google Drive crea una hoja de cálculo nueva, por ejemplo «HEARTS Arcade - Resultados».
2. En el menú, abre **Extensiones > Apps Script**.
3. Borra lo que aparece, pega todo el contenido de `Codigo-Apps-Script.gs` y presiona **Guardar**.
4. Arriba a la derecha, presiona **Implementar > Nueva implementación**.
5. En el engranaje junto a «Seleccionar tipo», elige **Aplicación web** y configura:
   - Ejecutar como: **Yo**.
   - Quién tiene acceso: **Cualquier usuario**.
6. Presiona **Implementar** y autoriza el acceso con tu cuenta. Si Google muestra «Google no verificó esta app», entra a **Configuración avanzada > Ir a … (no seguro)** y presiona **Permitir**; es tu propio script.
7. Copia la **URL de la aplicación web**; termina en `/exec`.
8. Abre `index.html` con un editor de texto y busca esta línea, cerca del inicio del código:

   ```js
   const SHEET_URL = '';
   ```

   Pega tu URL entre las comillas y guarda:

   ```js
   const SHEET_URL = 'https://script.google.com/macros/s/.../exec';
   ```

## Parte 2. Publicar el juego en GitHub Pages

1. Entra a [github.com](https://github.com) con tu cuenta, o crea una gratis.
2. Presiona **New** para crear un repositorio nuevo:
   - Nombre: por ejemplo `hearts-arcade`.
   - Visibilidad: **Public**, porque GitHub Pages gratis lo requiere.
   - Presiona **Create repository**.
3. En la página del repositorio, entra a **uploading an existing file**, arrastra `index.html` y `README.md`, y presiona **Commit changes**.
4. Ve a **Settings > Pages** y en «Build and deployment» configura:
   - Source: **Deploy from a branch**.
   - Branch: **main**, carpeta **/ (root)**.
   - Presiona **Save**.
5. Espera uno o dos minutos y recarga la página. Arriba aparecerá la dirección del juego, por ejemplo:
   `https://TU-USUARIO.github.io/hearts-arcade/`

Esa dirección es la que compartes con el personal de salud por WhatsApp, correo o un código QR.

Para cambiar algo después, por ejemplo pegar la URL de la hoja si no lo hiciste antes, abre `index.html` en GitHub, presiona el lápiz para editar, haz el cambio y presiona **Commit changes**. La página se actualiza sola en uno o dos minutos.

## Parte 3. Descargar el Excel

Cada partida agrega una fila a la pestaña **Resultados** de tu hoja, ordenada de mayor a menor puntaje, con fecha, nombre, servicio de salud, puntos, aciertos y retos jugados.

Para tenerla en Excel: **Archivo > Descargar > Microsoft Excel (.xlsx)**.

El ranking dentro del juego muestra el top 10, con el mejor puntaje de cada persona. La hoja guarda todas las partidas.

## Antes de compartirlo

- **Prueba:** juega una partida desde tu celular y revisa que aparezca la fila en la hoja.
- **Si cambias el código de Apps Script:** usa **Implementar > Administrar implementaciones > Editar (lápiz) > Versión: Nueva versión > Implementar**. Así la URL no cambia.
- **El enlace es abierto:** cualquiera que lo tenga puede jugar y enviar resultados. Si vas a dar premios, revisa la hoja antes.
- **Datos personales:** el juego guarda el nombre y el servicio de salud que cada persona escribe. Avísalo a quienes jueguen.
