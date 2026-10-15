# Galosoft Contable · sitio web

## Estructura
- `index.html`: Inicio
- `servicios.html`, `tramites-sat.html`, `nosotros.html`, `contacto.html`, `aviso-de-privacidad.html`
- Landings de campaña (sin menú, con el formulario arriba):
  - `declaracion-anual.html`
  - `regularizacion-sat.html`
  - `efirma.html`
- `assets/`: estilos, JS, favicon, ícono táctil e imagen para vistas previas en WhatsApp y Facebook (`og-contable.png`).

## Publicar
1. Sube todo el contenido de esta carpeta a `public_html` de galosoftcontable.com, respetando la carpeta `assets`.
2. Configura en el hosting que `www` y la versión sin `www` apunten al mismo sitio. La URL canónica usa **https://www.galosoftcontable.com**.
3. En `assets/main.js`, reemplaza `WEBHOOK` por la URL de producción de tu webhook de n8n.
4. En n8n, configura el nodo Webhook así:
   - Método POST.
   - Responder con código 200.
   - En "Allowed Origins (CORS)", agrega `https://www.galosoftcontable.com`.

   El JSON que recibe trae estos campos: `nombre`, `telefono`, `regimen`, `necesidad`, `acepto`, `marca`, `origen`, `pagina`, `utm` y `fecha`. El campo `origen` indica de qué página o landing viene el contacto.
5. Prueba el formulario y la vista previa compartiendo el enlace por WhatsApp.

## Pendientes antes de publicar
- [ ] URL real del webhook de n8n (`assets/main.js`).
- [ ] Logo definitivo. El isotipo "G" del encabezado, del pie y del favicon es provisional. Sustituye la variable `LOGO` (SVG) o envíame el archivo.
- [ ] Aviso de privacidad: si agregas Google Analytics o Meta Pixel, menciónalo en la sección de cookies. Recomiendo que un abogado revise el texto.
- [ ] Testimonios: la sección está comentada en `index.html`. Actívala solo con reseñas reales de Google.
- [ ] Confirmar el código postal (54474 o 54476) contra tu Constancia de Situación Fiscal.
- [ ] Confirmar que el usuario @galosoftcontable existe en redes antes de enlazarlo. Hoy el sitio no lo enlaza.
