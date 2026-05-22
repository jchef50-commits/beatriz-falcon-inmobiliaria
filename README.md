# NOVA Inmobiliaria — Sitio Web Profesional

Plataforma web completa para agente inmobiliario. Lista para deploy en Vercel o GitHub Pages.

## Personalización rápida (antes de lanzar)

Busca y reemplaza en `index.html`:

| Busca | Reemplaza con |
|-------|--------------|
| `521XXXXXXXXXX` | Tu número de WhatsApp con código de país (ej. `5215512345678`) |
| `NOVA` | Tu nombre o marca |
| `Lic. Carlos Mendoza` | Tu nombre completo |
| `contacto@novainmobiliaria.mx` | Tu correo real |
| `novainmobiliaria` | Tu usuario en redes sociales |
| `g.page/r/XXXXXXXX/review` | Tu enlace de Google Business |

## Deploy en Vercel (recomendado — gratis)

1. Sube el proyecto a un repositorio de GitHub
2. Ve a [vercel.com](https://vercel.com) → New Project
3. Importa tu repositorio
4. Click **Deploy** — listo en 30 segundos
5. Conecta tu dominio propio en Vercel Dashboard → Settings → Domains

## Deploy en GitHub Pages

1. Sube a GitHub con rama `main`
2. Settings → Pages → Source: **GitHub Actions**
3. El workflow `.github/workflows/deploy.yml` se ejecuta automáticamente
4. Tu sitio estará en `https://TU-USUARIO.github.io/TU-REPO`

## Integración de leads con WhatsApp Business

El formulario de contacto envía el lead directo a WhatsApp con todos los datos del prospecto.

Para automatizar aún más, conecta a:
- **HubSpot CRM** (gratuito hasta 1M contactos)
- **Make (Integromat)** — formulario → Google Sheets → notificación WhatsApp
- **Zapier** — formulario → CRM + email automático

## Páginas y secciones incluidas

- Hero con estadísticas y CTA doble
- Buscador de propiedades con filtros
- Catálogo de propiedades (3 cards demo)
- 6 servicios completos
- Proceso de 4 pasos
- Calculadora de hipoteca en tiempo real
- Testimonios
- Zonas/colonias con links a WhatsApp
- Perfil del agente con contacto directo
- Dashboard de leads (preview visual del CRM)
- Formulario de captación de leads
- Barra flotante de contacto rápido (WhatsApp + Llamar + Email)
- Footer completo con redes sociales

## Canales de captación recomendados

### Redes sociales
- **Instagram**: Reels de propiedades + historia diaria con "link en bio" a tu sitio
- **Facebook**: Anuncios de captación con formulario nativo → webhook a WhatsApp
- **TikTok**: Tours virtuales de 30s + CTA al sitio

### Tráfico local
- **Google Business Profile**: Completa al 100%, solicita reseñas activamente
- **Google Ads**: Keywords como "casas en venta [colonia]", "departamentos renta [ciudad]"
- **SEO local**: Actualiza el meta description con tu ciudad real

## Métricas clave a rastrear

Instala Google Analytics 4 (gratuito):
```html
<!-- Pega antes de </head> en index.html -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

Convierte los clics a WhatsApp como eventos:
```js
// Pega en el <script> del index.html
document.querySelectorAll('a[href*="wa.me"]').forEach(el => {
  el.addEventListener('click', () => {
    gtag('event', 'whatsapp_click', { event_category: 'lead' });
  });
});
```
