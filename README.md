
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

## Configuración Firebase:
La autenticación de usuarios usa Firebase Authentication nativo con proveedor Correo/Contraseña.
- Registro: `createUserWithEmailAndPassword`
- Login: `signInWithEmailAndPassword`
- Recuperación: `sendPasswordResetEmail`
- Verificación: `sendEmailVerification`
- Datos de usuario: Firestore en `users/{UID}` (UID real de Firebase)
- No se guarda la contraseña en Firestore ni en localStorage.

En Firebase Console debes habilitar Authentication → Sign-in method → Email/Password y agregar el dominio de producción en Authentication → Settings → Authorized domains.
Proyecto configurado: `nutritrack-v2-ab92f`.

## Seguridad:
- Invitado = volátil y separado de las cuentas.
- Usuario autenticado = UID real de Firebase como namespace.
- La contraseña solo la gestiona Firebase Authentication.
- Firestore usa `users/{UID}` para los datos de la cuenta.
- La sesión y las operaciones de correo/contraseña se validan con Firebase Auth.

## Versión: v1.0


## NutriSport Pro / Monetización
- Google Sign-In conservado.
- Cuenta Pro de prueba fija por UID `6oRhKb66WdNrc0ZJnD4dpjo3E4i2` y correo `luisangelesquerra@gmail.com`.
- También reconoce futuros usuarios con `isPremium: true`, `plan: "pro"` o `subscriptionStatus: "active"` en el perfil de Firestore.
- El anuncio de Monetag se carga únicamente al entrar al dashboard de usuarios no-Pro y una vez por visita al dashboard.
- Se amplió el catálogo de alimentos y ejercicios.

> Nota: el bloqueo visual de Pro del frontend no sustituye una validación segura de suscripción en backend/Firestore Rules. Para cobros reales, el estado premium debe ser escrito por un backend o proveedor de pagos confiable.
