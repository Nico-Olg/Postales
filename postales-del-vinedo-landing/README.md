# 🍇 Postales del Viñedo - Landing Page

Landing page premium para el complejo vitivinícola residencial en La Paz, Entre Ríos.

## 🎨 Características

### Diseño y Experiencia
- ✅ Diseño premium con estética "Lujo Orgánico Argentino"
- ✅ Animaciones fluidas con Framer Motion
- ✅ Efectos parallax y scroll reveal
- ✅ Responsive 100% (mobile-first)
- ✅ Optimizado para conversión

### Secciones Incluidas
1. **Hero Section** - Impacto visual inmediato con parallax
2. **Concepto** - Los 3 pilares del proyecto
3. **Galería Visual** - Imágenes del complejo (placeholders incluidos)
4. **Inversión** - Breakdown del precio y beneficios
5. **Escasez** - Solo 15 lotes + testimonios
6. **Amenities** - Todo lo que incluye el complejo
7. **Ubicación** - Mapa y accesibilidad
8. **Timeline** - Roadmap del proyecto
9. **Contacto** - Formulario optimizado para leads
10. **Footer** - Links y redes sociales

### Optimizaciones
- 🚀 Performance optimizada con Vite
- 📱 Mobile-first responsive
- ♿ Accesibilidad (WCAG 2.1)
- 🎯 SEO-friendly
- 📊 Listo para analytics

## 🛠️ Instalación

### Prerequisitos
- Node.js 16+ instalado
- npm o yarn

### Pasos de Instalación

1. **Crear carpeta del proyecto**
```bash
mkdir postales-del-vinedo-landing
cd postales-del-vinedo-landing
```

2. **Copiar archivos**
Copia todos los archivos proporcionados a esta carpeta:
- `package.json`
- `vite.config.js`
- `index.html`
- `main.jsx`
- `App.jsx`
- `PostalesDelVinedoLanding.jsx`
- `PostalesDelVinedo.css`

3. **Instalar dependencias**
```bash
npm install
```

4. **Iniciar servidor de desarrollo**
```bash
npm run dev
```

La aplicación se abrirá automáticamente en `http://localhost:3000`

5. **Build para producción**
```bash
npm run build
```

Los archivos optimizados estarán en la carpeta `dist/`

## 🎯 Personalización

### 1. Colores y Branding

Edita las variables CSS en `PostalesDelVinedo.css`:

```css
:root {
  --primary: #2c5f2d;        /* Verde principal */
  --secondary: #97bc62;      /* Verde secundario */
  --accent: #d4a373;         /* Dorado/tierra */
  --cream: #f5f1ed;          /* Crema de fondo */
}
```

### 2. Imágenes Reales

**IMPORTANTE:** Reemplaza los placeholders con tus fotos reales.

En `PostalesDelVinedoLanding.jsx`, busca:

```jsx
// Hero Section - línea ~45
<div className="hero-image" />
```

Reemplaza con:
```jsx
<img 
  src="/images/hero-vineyard.jpg" 
  alt="Viñedos al atardecer" 
  className="hero-image"
/>
```

Crea una carpeta `public/images/` y agrega:
- `hero-vineyard.jpg` (1920x1080px) - Viñedos al atardecer
- `vineyard-sunset.jpg` - Atardecer en viñedos
- `winery.jpg` - Interior bodega
- `cabin.jpg` - Cabañas
- `glamping.jpg` - Glamping
- `wine-glass.jpg` - Copa de vino
- `family-walk.jpg` - Familia entre viñedos
- `aerial-view.jpg` - Vista aérea

### 3. Información del Formulario

El formulario actualmente simula el envío. Para conectarlo a tu backend:

En `PostalesDelVinedoLanding.jsx`, busca la función `handleSubmit` (~línea 480):

```jsx
const handleSubmit = async (e) => {
  e.preventDefault();
  setIsSubmitting(true);
  
  // REEMPLAZAR ESTO CON TU API
  try {
    const response = await fetch('https://tu-api.com/leads', {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(formData)
    });
    
    if (response.ok) {
      setIsSubmitted(true);
      // Enviar a Google Analytics
      if (window.gtag) {
        window.gtag('event', 'generate_lead', {
          event_category: 'Contact Form',
          event_label: 'Landing Page Submission'
        });
      }
    }
  } catch (error) {
    console.error('Error:', error);
  } finally {
    setIsSubmitting(false);
  }
};
```

### 4. Datos del Proyecto

Actualiza los datos específicos en las constantes:

```jsx
// Inversión - línea ~200
const features = [
  "Viñedo privado plantado y mantenido",
  "Participación en bodega común",
  // ... actualiza según corresponda
];

// Timeline - línea ~350
const phases = [
  { quarter: "2025 Q1", title: "...", desc: "..." },
  // ... actualiza fechas reales
];
```

### 5. Información de Contacto

En el Footer (~línea 550):

```jsx
<a href="mailto:TU-EMAIL@ejemplo.com">
<a href="tel:+54TUNUMERO">
<a href="https://wa.me/54TUNUMERO">
```

## 📊 Analytics y Conversión

### Google Analytics

Agrega en `index.html` antes del `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=TU-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'TU-ID');
</script>
```

### Facebook Pixel

```html
<!-- Facebook Pixel -->
<script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', 'TU-PIXEL-ID');
  fbq('track', 'PageView');
</script>
```

## 🚀 Deployment

### Opción 1: Vercel (Recomendado)

1. Sube tu código a GitHub
2. Conecta con Vercel (vercel.com)
3. Deploy automático

### Opción 2: Netlify

1. Arrastra la carpeta `dist/` a netlify.com
2. O conecta con GitHub para deploy automático

### Opción 3: Hosting tradicional

1. Ejecuta `npm run build`
2. Sube el contenido de `dist/` a tu servidor vía FTP

## 📱 Testing

### Checklist Pre-Lanzamiento

- [ ] Reemplazar todas las imágenes placeholder
- [ ] Actualizar todos los textos con info real
- [ ] Configurar formulario con API backend
- [ ] Agregar Google Analytics
- [ ] Agregar Facebook Pixel
- [ ] Actualizar meta tags y SEO
- [ ] Probar en móviles reales
- [ ] Verificar todos los links
- [ ] Probar formulario de contacto
- [ ] Optimizar imágenes (WebP)
- [ ] Configurar dominio
- [ ] SSL/HTTPS activo

## 🎨 Diseño de Marca

### Paleta de Colores

```
Verde Viñedo:    #2c5f2d (Primary)
Verde Natural:   #97bc62 (Secondary)
Dorado Tierra:   #d4a373 (Accent)
Crema Elegante:  #f5f1ed (Background)
```

### Tipografías

- **Display/Títulos:** Playfair Display (elegante, serif)
- **Lectura:** Lora (legible, serif)
- **UI/Botones:** Inter (moderna, sans-serif)

## 📞 Soporte

Para consultas sobre esta landing page:
- Email: tu-email@ejemplo.com
- WhatsApp: +54 9 xxx xxxx

## 📄 Licencia

© 2025 Postales del Viñedo. Todos los derechos reservados.

---

## 🎯 Próximos Pasos Recomendados

1. **Conseguir fotos profesionales del terreno**
   - Contratar fotógrafo con drone
   - Golden hour (atardecer) para mejores resultados
   - Mínimo 10 fotos high-res

2. **Generar renders 3D** (si todavía no existen construcciones)
   - Bodega
   - Cabañas
   - Glamping
   - Vista aérea del masterplan

3. **Video testimonial** (opcional pero poderoso)
   - 30-60 segundos
   - Propietarios interesados o inversores confirmados
   - Agregar en Hero section

4. **Configurar CRM/Leads**
   - Conectar formulario a tu sistema
   - Email automation de bienvenida
   - WhatsApp Business API

5. **Campaña de Ads**
   - Facebook/Instagram Ads
   - Google Ads
   - Pixel de conversión configurado

---

**¡La landing está lista para enamorar a tus futuros propietarios!** 🍇🏡✨
