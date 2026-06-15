# Biblioteca Digital Android - versión online

Proyecto Android WebView que carga directamente la versión publicada de la biblioteca digital:

`https://edukaj.com.mx/liceo-universitario-demo`

Esta variante está pensada para que la app se vea igual que la web que ya funciona en navegador. No reconstruye el diseño en Android nativo; solo abre la página dentro de una WebView de pantalla completa.

## Recomendado para compilar sin Android Studio: GitHub Actions

Esta versión incluye:

`.github/workflows/build-apk.yml`

Ese workflow genera automáticamente un APK de prueba usando una máquina Linux en la nube.

### Pasos

1. Crea un repositorio nuevo en GitHub. Para evitar costos, usa un repositorio público.
2. Descomprime este ZIP.
3. Sube a GitHub el contenido de la carpeta `BibliotecaDigitalAndroid`, no el ZIP completo.
4. En GitHub, entra al repositorio y abre la pestaña **Actions**.
5. Selecciona **Build APK**.
6. Presiona **Run workflow**.
7. Cuando termine, abre el resultado del workflow y descarga el artifact:

   `BibliotecaDigital-debug-apk`

8. Descomprime ese artifact. Dentro estará el APK, normalmente:

   `app-debug.apk`

## Instalación en Android

- Copia `app-debug.apk` al teléfono.
- Abre el archivo desde Android.
- Permite instalación desde fuentes desconocidas si Android lo solicita.

## Notas importantes

- Esta versión requiere internet, porque carga la web publicada.
- Debe verse igual que la URL en Chrome móvil, con la misma fuente, imágenes, CSS, animaciones y responsive.
- Los enlaces dentro de `edukaj.com.mx` se mantienen dentro de la app.
- Los PDFs, mailto, tel y enlaces externos se abren con la app correspondiente del dispositivo.
- No tiene ícono personalizado de launcher.
- Es un APK debug para pruebas. Para publicar en Google Play se requiere un build release firmado.

## Cambiar URL

Edita este archivo:

`app/src/main/java/com/liceoloscabos/bibliotecadigital/MainActivity.java`

Y cambia:

```java
private static final String START_URL = "https://edukaj.com.mx/liceo-universitario-demo";
```
