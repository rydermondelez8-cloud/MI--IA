# Mi AI — proyecto Android

Aplicación inicial en español para Android con:
- Chat y redacción mediante Gemini API (modelo predeterminado `gemini-2.5-flash`).
- Exportación de texto a `.doc` compatible con Word y a `.txt`.
- Generación de imágenes mediante un proveedor HTTP configurable.
- Lectura en voz alta con la síntesis de voz del dispositivo.

## Requisitos
- Node.js 20+
- Android Studio y Android SDK (para compilar localmente)
- Una clave de Gemini API creada en Google AI Studio: https://aistudio.google.com/apikey

## Probar en navegador
Abre `www/index.html` desde un servidor local. Para usar el chat, guarda tu clave en **Ajustes** dentro de la app.

## Crear APK debug en tu computadora
```bash
npm install
npx cap add android
npx cap sync android
npx cap open android
```
En Android Studio: **Build > Build Bundle(s) / APK(s) > Build APK(s)**.

## Crear APK automáticamente con GitHub Actions
1. Sube estos archivos a un repositorio de GitHub.
2. Abre **Actions** y ejecuta el flujo **Build Mi AI APK**.
3. Descarga `Mi-AI-debug-apk` en Artifacts. Es un APK de prueba/debug.

## Servicios y costos
- Gemini ofrece un nivel gratuito con límites, disponibilidad y condiciones que pueden cambiar.
- La generación de imágenes necesita un proveedor compatible. Configura su URL en Ajustes; el endpoint de ejemplo es solo una plantilla y puede requerir una clave o tener límites.
- La voz usa las voces instaladas en Android y no necesita una API externa.

## Seguridad
La clave API se guarda localmente en el dispositivo para facilitar el uso personal. No publiques el APK con tu clave ya configurada: una clave incluida en una app cliente puede extraerse. Para distribuirla a otras personas, usa un backend propio con autenticación y límites de uso.
