# EcoVida Mobile — Guía de Compilación de APK Instalable

Esta guía explica cómo importar este proyecto en **Android Studio**, compilarlo y generar el archivo **APK instalable** para tu teléfono Android.

---

## 1. Requisitos Previos
- **Android Studio** (versión Hedgehog 2023.1 o superior / Ladybug recomendada).
- **JDK 17** (incluido por defecto en Android Studio).
- Dispositivo Android con versión 7.0+ (Nougat, API 24+) o emulador configurado.

---

## 2. Pasos para Importar en Android Studio
1. Descarga el paquete ZIP generado desde la pestaña **"Código Android & APK"** en EcoVida Mobile.
2. Descomprime el archivo en una carpeta de tu preferencia (ej: `C:\Proyectos\EcoVidaMobile`).
3. Abre **Android Studio** y selecciona:
   - **File** → **Open...**
   - Selecciona la carpeta raíz donde se encuentra `build.gradle.kts`.
4. Espera a que Gradle sincronice las dependencias automáticas (tarda de 1 a 3 minutos en la primera apertura).

---

## 3. Compilar APK de Depuración (Debug APK)
El APK de depuración es perfecto para instalar directamente en cualquier teléfono sin configurar certificados de firma:

### Opción A: Desde la interfaz de Android Studio
1. En el menú superior, haz clic en **Build** → **Build Bundle(s) / APK(s)** → **Build APK(s)**.
2. Al terminar la compilación aparecerá una notificación: *"APK(s) generated successfully"*.
3. Haz clic en el enlace azul **"locate"** para abrir la carpeta con el archivo:
   `app/build/outputs/apk/debug/app-debug.apk`

### Opción B: Desde la Terminal integrada
Ejecuta el siguiente comando en la pestaña Terminal de Android Studio:
```bash
# En Windows (PowerShell / CMD):
.\gradlew.bat assembleDebug

# En macOS / Linux:
./gradlew assembleDebug
```

---

## 4. Cómo Instalar el APK en tu Dispositivo Android
1. **Conexión USB directa (ADB):**
   - Activa las *Opciones de Desarrollador* en tu teléfono (tocando 7 veces el *Número de compilación* en Ajustes).
   - Activa *Depuración por USB*.
   - Conecta el cable y en Android Studio presiona el botón verde **Run (▶)**.

2. **Instalación manual del archivo APK:**
   - Copia el archivo `app-debug.apk` a tu teléfono (por WhatsApp, Google Drive, Telegram o cable USB).
   - En tu teléfono, abre el explorador de archivos y toca el archivo `app-debug.apk`.
   - Si el sistema te lo pide, autoriza *"Instalar aplicaciones desconocidas"* para ese origen.
   - ¡Listo! EcoVida Mobile aparecerá en tu menú de aplicaciones con su icono verde y acceso sin conexión completo.

---

## 5. Generar APK Firmado para Distribución (Release)
1. En Android Studio, ve a **Build** → **Generate Signed Bundle / APK...**
2. Selecciona **APK** y haz clic en **Next**.
3. Crea un nuevo Keystore (*Create new...*) o selecciona uno existente.
4. Selecciona la variante **release**.
5. El APK firmado quedará listo en `app/release/app-release.apk` para distribución a colegios, comunidades o subir a tiendas.
