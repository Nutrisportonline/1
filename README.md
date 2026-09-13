
# NutriSport v1.0 - PWA Builder Ready

## Incluye:
- index.html (app completa rica v1.0)
- public/icon-192.png, icon-512.png, favicon.png, apple-touch-icon.png (flama verde)
- manifest.json + public/manifest.json
- sw.js + public/sw.js
- README

## Para PWA Builder (APK):
1. Sube este proyecto a GitHub (todo el contenido de esta carpeta en root)
2. Ve a https://www.pwabuilder.com
3. Pega URL de tu GitHub Pages (ej: https://tuusuario.github.io/nutrisport/)
4. PWA Builder detectará manifest y service worker
5. Click Build -> Android -> Genera APK/AAB

## Configuración Firebase (opcional):
La app ya tiene namespace seguro por usuario:
- nutritrack_v2_{hash}
- nutrisport_photo_{hash}
- customFoods_{hash}
Intenta guardar en Firestore si configuras Firebase con projectId nutritrack-v2-ab92f

## Seguridad:
- Invitado = volátil, nunca lee localStorage previo
- Usuario = namespaced por hash email
- Racha 1/día, solo quitar hoy, sync servidor
- Perfil requiere contraseña para guardar

## Versión: v1.0
