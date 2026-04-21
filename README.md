# Web de Marta Fernández-Golfín

Sitio web estático, bilingüe (ES/EN), listo para publicar.

---

## Archivos

- `index.html` — el sitio completo en un solo archivo (HTML + CSS + JS inline)
- `assets/marta.jpg` — foto de perfil
- `README.md` — este archivo

---

## Cómo verlo en local

Abre `index.html` directamente en tu navegador haciendo doble clic. Funciona sin servidor.

Si prefieres servidor local (opcional):
```bash
cd web_marta
python3 -m http.server 8000
# Abre http://localhost:8000
```

---

## Cómo publicarlo online

Tienes dos caminos. Recomiendo el primero.

### Opción A — Netlify (más sencillo, 10 minutos)

1. Ve a https://netlify.com y crea cuenta gratis con tu gmail
2. Desde el dashboard, arrastra la carpeta `web_marta` completa a la zona que dice "Drag and drop your site folder here"
3. Netlify te da una URL tipo `random-name-abc123.netlify.app` — ya está online
4. **Para conectar el dominio propio:**
   - Compra `martafernandezgolfin.com` en Cloudflare (10€/año) o Namecheap
   - En Netlify: Site settings → Domain management → Add custom domain
   - Netlify te da 2 registros DNS (tipo `A` y `CNAME`)
   - Los pegas en el panel de DNS de tu registrador
   - SSL automático en 5-10 minutos

**Coste total:** dominio 10€/año. Hosting 0€. SSL 0€.

### Opción B — Vercel

Mismo procedimiento que Netlify. Funciona igual de bien.

---

## Cómo editar el contenido

El sitio usa un sistema bilingüe con atributos `data-es` y `data-en` en cada elemento de texto. Para editar cualquier texto:

1. Abre `index.html` con cualquier editor (VS Code, Sublime Text, TextEdit)
2. Busca el texto que quieras cambiar
3. **Verás dos versiones:** una en `data-es="..."` y otra en `data-en="..."`, seguidas del texto visible.
4. **Edita las tres:** el atributo `data-es`, el atributo `data-en`, y el texto que hay dentro del elemento
5. Guarda y re-sube a Netlify (arrastre simple)

Ejemplo:
```html
<p data-es="Texto en español"
   data-en="Text in English">
  Texto en español
</p>
```

Si solo cambias el texto visible pero no los atributos `data-*`, el cambio desaparece al cambiar de idioma.

---

## Cómo conectar Calendly

Actualmente el CTA "Reservar primera sesión" apre un email (`mailto:`). Para sustituirlo por Calendly:

1. Crea cuenta en Calendly y configura tu evento "Sesión exploratoria 30 min"
2. En `index.html`, busca: `href="mailto:hola@martafernandezgolfin.com?subject=Sesi%C3%B3n%20exploratoria"`
3. Reemplázalo por: `href="https://calendly.com/tu-usuario/sesion-exploratoria"`
4. Guarda. Re-sube.

**Para embeber el calendario directamente en la página** (en vez de redirigir):

Busca el bloque `<section class="book" id="reserva">` y sustituye el botón por este código:

```html
<div class="calendly-inline-widget"
     data-url="https://calendly.com/TU-USUARIO/sesion-exploratoria?hide_gdpr_banner=1&background_color=2B2520&text_color=F4EFE6&primary_color=C9986E"
     style="min-width:320px;height:700px;margin-top:2rem;"></div>
<script type="text/javascript" src="https://assets.calendly.com/assets/external/widget.js" async></script>
```

Los parámetros `background_color`, `text_color` y `primary_color` hacen que el widget se integre visualmente con el fondo oscuro de la sección.

---

## Email profesional

Ahora el sitio apunta a `hola@martafernandezgolfin.com`. Para que ese email funcione:

1. Una vez tengas el dominio en Cloudflare: Email → Email Routing → Enable
2. Create address: `hola@martafernandezgolfin.com` → redirige a `martafernandezgolfincoach@gmail.com`
3. Tarda 5 minutos. Gratis.

Mientras no tengas el dominio, puedes dejar `martafernandezgolfincoach@gmail.com` en su lugar — busca todos los sitios donde aparece `hola@martafernandezgolfin.com` en `index.html` y reemplázalos.

---

## Stack técnico

- HTML + CSS + JavaScript vanilla, sin dependencias
- Fuentes: Cormorant Garamond (display) + Inter (body), desde Google Fonts
- Peso total: ~600 KB (incluye foto)
- Mobile-first responsive
- Accesibilidad: dark mode no, `prefers-reduced-motion` respetado, semántica HTML correcta
- SEO: title, meta description, lang attribute dinámico

---

## Qué NO hace este sitio todavía

Cosas que podrías añadir más adelante si te hacen falta:

- Formulario de contacto (ahora es solo email)
- Testimonios (espera a tener clientas reales)
- Blog o contenido
- Analytics (considera Plausible, 9€/mes, GDPR-compliant sin cookies)
- Favicon personalizado (Framer/Netlify te generan uno genérico)

---

## Contacto con quien te ayudó

Si algo no funciona o quieres añadir algo, tráeme el archivo modificado y lo resolvemos en la siguiente conversación.
