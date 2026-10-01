# Portfolio de Teo Fassardi

Portfolio personal de Teo Fassardi, Full Stack Developer y estudiante de Ingeniería en Sistemas. Trabajo Práctico N.º 1.

- **Sitio público:** https://portfolio-nine-swart-86.vercel.app/
- **Repositorio:** https://github.com/fassardi245/Portfolio

## Stack

- Astro 7 para generar el sitio estático.
- HTML semántico y CSS responsive, sin frameworks de estilos.
- TypeScript para las interacciones de tema, navegación y copia de email.
- DM Sans y Barlow Condensed alojadas en `public/fonts`, con licencias OFL y fuentes de respaldo.
- Retrato personal optimizado a WebP con Astro, versiones responsive y encuadre mediante CSS.
- Identidad visual en negro, amarillo y rojo, con modo claro y oscuro.

## Ejecutar localmente

Requiere Node.js 22.12 o superior y npm.

```sh
npm install
npm run dev -- --background
```

Abrir la URL que indica Astro (por defecto http://localhost:4321).

En Windows, si PowerShell bloquea `npm.ps1`, usar `npm.cmd` en lugar de `npm`.

```sh
npm run astro -- dev status
npm run astro -- dev logs
npm run astro -- dev stop
```

## Producción

```sh
npm run build
npm run preview
```

El sitio generado queda en `dist/`. Para Vercel o Netlify, importar el repositorio con el preset Astro, usar `npm run build` como comando y `dist` como directorio de publicación. No requiere variables de entorno.

## Contenido y accesibilidad

Hero, tres proyectos reales, biografía, tecnologías agrupadas, CV descargable en PDF y contacto. La navegación lleva a cada sección; el email abre el cliente de correo. El botón de copia usa el portapapeles cuando está disponible (HTTPS o localhost).

El formulario valida nombre (2–80 caracteres), email y mensaje (10–2000 caracteres), muestra errores junto a cada campo y enfoca el primer error. Al completarlo prepara un enlace `mailto:` con el asunto y mensaje codificados: el visitante debe revisar y enviar el correo desde su aplicación. No hay servicio de envío automático ni almacenamiento de mensajes. Los datos se conservan en los campos mientras permanezca en la página. Sin JavaScript se ofrece el enlace de email directo.

El CV se encuentra en `public/CV-Teo-Fassardi.pdf` y se descarga desde el Hero.

El tema inicial respeta el sistema; al cambiarlo se guarda la preferencia en localStorage. El sitio incluye foco visible, enlace para saltar al contenido, un único h1 y soporte de `prefers-reduced-motion`.

- `src/pages/index.astro`: contenido e interacciones.
- `src/layouts/Layout.astro`: metadatos, fuentes y tema inicial.
- `src/styles/global.css`: estilos y responsive.
- `src/assets/teo-fassardi.jpeg`: imagen original del retrato.
- `src/components/Icon.astro`: iconos SVG.
- `src/components/ContactForm.astro`: formulario y validación accesible.

## Lighthouse

Verificación del deploy: la URL pública respondió correctamente, incluido el PDF. Lighthouse móvil midió **87 Performance / 100 Accessibility** ([informe público](docs/lighthouse/public.html)). Se optimizó la carga alojando las fuentes WOFF2 en el proyecto: el build actualizado obtuvo **100 / 100 localmente** ([informe optimizado](docs/lighthouse/fonts-local.html)). Esta optimización debe subirse a GitHub y medirse nuevamente en Vercel; el resultado local no sustituye la medición pública.

Medición del 1 de octubre de 2026 con Lighthouse 13.5.0, sobre `npm run build` servido localmente con `npm run preview`. Las puntuaciones no corresponden todavía a un deploy público.

| Perfil | Performance | Accessibility | Informe |
| --- | --- | --- | --- |
| Móvil | 92 | 100 | [Abrir HTML](docs/lighthouse/mobile.html) |
| Escritorio | 99 | 100 | [Abrir HTML](docs/lighthouse/desktop.html) |

La medición móvil incluye el último rediseño del botón de CV y del formulario. El informe de escritorio corresponde a la versión anterior a ese ajuste visual.

Para repetir la medición con el preview iniciado:

```sh
npx lighthouse http://localhost:4321 --only-categories=performance,accessibility --chrome-flags="--headless=new" --output=html --output-path=lighthouse-mobile.html
```

Usar la URL que indique el preview y agregar `--preset=desktop` para escritorio. Repetir sobre la URL pública después del deploy: el entorno de carga puede cambiar las puntuaciones. Las pruebas automáticas se complementaron con revisión responsive en 360, 768 y 1280 px, navegación de teclado, temas y validación del formulario.

## Entrega

Subir al aula virtual los enlaces del sitio público y del repositorio indicados al inicio. Revisar que el historial refleje commits progresivos del desarrollo, como exige la consigna.
