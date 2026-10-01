# Teo Fassardi · Portfolio

Portfolio personal desarrollado para el **Trabajo Práctico N.º 1: Portfolio**. Presenta mi perfil como Full Stack Developer y estudiante de Ingeniería en Sistemas, mis tecnologías, proyectos y datos de contacto.

## Enlaces de entrega

- **Sitio publicado en Vercel:** [portfolio-nine-swart-86.vercel.app](https://portfolio-nine-swart-86.vercel.app/)
- **Repositorio público:** [github.com/fassardi245/Portfolio](https://github.com/fassardi245/Portfolio)
- **CV en PDF:** [Descargar CV](https://portfolio-nine-swart-86.vercel.app/CV-Teo-Fassardi.pdf)

## Stack elegido

- **Astro 7:** generación del sitio estático y componentes.
- **HTML semántico y CSS:** estructura, diseño responsive y temas claro/oscuro.
- **TypeScript:** validación del formulario, cambio de tema, navegación activa y copia de email.
- **Astro Assets:** optimización del retrato a WebP con tamaños responsive.
- **DM Sans y Barlow Condensed:** fuentes alojadas localmente; sus licencias OFL se incluyen en `public/fonts/`.
- **Git y GitHub:** control de versiones y repositorio.
- **Vercel:** publicación del sitio.

Se eligió Astro porque el portfolio es principalmente contenido estático y permite incorporar las interacciones necesarias con poco JavaScript.

## Cómo ejecutarlo localmente

Requisitos: **Node.js 22.12 o superior** y **npm**.

```sh
git clone https://github.com/fassardi245/Portfolio.git
cd Portfolio
npm install
npm run dev -- --background
```

Abrir la URL indicada en la terminal, normalmente **http://localhost:4321**.

Para consultar o detener el servidor en segundo plano:

```sh
npm run astro -- dev status
npm run astro -- dev logs
npm run astro -- dev stop
```

En Windows, si PowerShell bloquea `npm.ps1`, utilizar `npm.cmd` en lugar de `npm`.

## Compilación y publicación

```sh
npm run build
npm run preview
```

La compilación genera el sitio en `dist/`. El segundo comando permite revisar ese resultado localmente; abrir la URL que indique la terminal.

Configuración en Vercel:

| Opción | Valor |
| --- | --- |
| Framework | Astro |
| Comando de compilación | `npm run build` |
| Directorio de salida | `dist` |
| Variables de entorno | No requiere |

## Secciones del portfolio

- **Hero:** nombre, rol profesional, presentación, foto y botones para ver los proyectos y descargar el CV.
- **Sobre mí:** biografía y habilidades agrupadas en frontend, backend, bases de datos y herramientas.
- **Proyectos:** tres trabajos con descripción, tecnologías y enlaces.
- **Contacto:** email, GitHub, LinkedIn y formulario con validación.
- **Navegación:** menú por secciones y logo para volver al inicio.

### Proyectos incluidos

| Proyecto | Descripción | Enlaces |
| --- | --- | --- |
| SmartCloth Logistics | Plataforma de comercio electrónico, inventario y gestión logística, desarrollada en equipo como proyecto final académico. | [Repositorio](https://github.com/fassardi245/Diplomaa) |
| Task Manager | Aplicación full stack de gestión de tareas con autenticación y filtros por estado y prioridad. | [Repositorio](https://github.com/fassardi245/TaskManager) |
| Futbolle | Juego de adivinanza de futbolistas con tres dificultades, pistas, puntuación e historial de partidas. | [Repositorio](https://github.com/fassardi245/Futbolle-Final-Web) · [Demo](https://fassardi245.github.io/Futbolle-Final-Web/) |

## Formulario de contacto

El formulario valida:

- **Nombre:** entre 2 y 80 caracteres, sin aceptar un valor compuesto únicamente por espacios.
- **Email:** formato válido y máximo de 254 caracteres.
- **Mensaje:** entre 10 y 2000 caracteres.

Los errores se muestran junto a cada campo y el foco se lleva al primer campo inválido. Se conservan los datos ingresados para poder corregirlos.

Al continuar, se abre la aplicación de correo del visitante con el destinatario, asunto y mensaje preparados mediante `mailto:`. **El visitante debe completar el envío desde su aplicación de correo.** El sitio no envía emails automáticamente ni almacena los mensajes. También ofrece el enlace de email directo y un botón para copiar la dirección.

## Responsive, accesibilidad y extras

- Diseño revisado a **360, 768 y 1280 px**, sin scroll horizontal.
- Uso de `header`, `nav`, `main`, `section` y `footer`, con un único `h1`.
- Texto alternativo en la foto, etiquetas de formulario y mensajes de error accesibles.
- Enlaces y controles utilizables con teclado, foco visible y enlace para saltar al contenido.
- **Modo claro y oscuro**, con preferencia del sistema y elección guardada en `localStorage`.
- **Interacciones sutiles** que respetan `prefers-reduced-motion`.
- **CV descargable en PDF** desde el Hero.
- Informes de Lighthouse disponibles en [`docs/lighthouse/`](docs/lighthouse/). Cada informe identifica la URL y el entorno medido.

## Estructura principal

```text
public/
  CV-Teo-Fassardi.pdf
  fonts/
src/
  assets/teo-fassardi.jpeg
  components/
    ContactForm.astro
    Icon.astro
  layouts/Layout.astro
  pages/index.astro
  styles/
    fonts.css
    global.css
docs/lighthouse/
```

## Autor y contacto

**Teo Fassardi** · Full Stack Developer · Estudiante de Ingeniería en Sistemas.

- [teofassardi123@gmail.com](mailto:teofassardi123@gmail.com)
- [GitHub](https://github.com/fassardi245)
- [LinkedIn](https://www.linkedin.com/in/teo-fassardi-4207b4366/)
