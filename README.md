# EcoVida Mobile (com.ecovida.mobile)
Contenedor Android nativo (Kotlin + WebView seguro) que empaqueta EcoVida_Oficial.html y funciona sin conexión.

## Opción A — Sin instalar nada (GitHub)
1. Crea un repositorio en github.com y sube TODO el contenido de esta carpeta (incluida la carpeta oculta .github).
2. Pestaña Actions > Build APK > Run workflow.
3. Al terminar, descarga el artefacto EcoVida-Mobile-debug-apk (zip con app-debug.apk).
4. Pasa el APK al teléfono, ábrelo y permite "instalar apps desconocidas" cuando Android lo pida.

## Opción B — Android Studio
1. File > Open > carpeta EcoVidaMobile (descarga Gradle y SDK 34 automáticamente).
2. Build > Build Bundle(s)/APK(s) > Build APK(s). Ruta: app/build/outputs/apk/debug/app-debug.apk
3. Con el teléfono en depuración USB: botón Run.

## APK firmado de distribución
Build > Generate Signed Bundle / APK > APK > crea un keystore (guárdalo) > variante release.
