# AGPCursos - Plataforma de Cursos Online

¡Aprende sin distracciones! Plataforma de cursos online con videos embebidos sin anuncios molestos.

## 🚀 Características

- **Sin anuncios**: Videos embebidos sin publicidad intrusiva
- **Gratuito**: Hospedado en GitHub Pages
- **Responsive**: Diseño adaptable para móviles y escritorio
- **Rápido**: Carga instantánea con TailwindCSS
- **Accesible**: Cumple estándares de accesibilidad

## 📚 Categorías

- **Desarrollo**: Programación (Python, Java, C#, JavaScript), desarrollo web, videojuegos, móvil y bases de datos
- **Negocios**: Emprendimiento, comunicación, gestión de proyectos, ventas, estrategia
- **Finanzas**: Contabilidad, análisis financiero, criptomonedas, economía e inversiones
- **Informática**: Redes, ciberseguridad, sistemas operativos, servidores
- **Inteligencia Artificial**: ML, IA, Deep Learning
- **Productividad**: Excel, Google Workspace, SAP
- **Desarrollo Personal**: Liderazgo, inteligencia emocional, crecimiento
- **Diseño**: Photoshop, Illustrator, Canva, UX/UI
- **Marketing**: SEO, redes sociales, publicidad, growth hacking
- **Salud**: Yoga, nutrición, entrenamiento
- **Música**: Instrumentos, producción, teoría
- **Enseñanza**: Ciencias, matemáticas, humanidades

## 🛠️ Tecnología

- **Stack**: HTML + TailwindCSS + JavaScript (vanilla)
- **Hospedaje**: GitHub Pages (gratis)
- **Base de datos**: JSON estático (`data/cursos.json`)
- **Reproductor**: Plyr.io con fallback a Invidious (yewtu.be)
- **CMS**: Decap CMS (interfaz de administración)

## 🚀 Demo

👉 **[Ver plataforma](https://andryugp.github.io/agpcursos)**

📋 **[Panel de Administración](https://andryugp.github.io/agpcursos/admin/)** (requiere login de GitHub)

## 📂 Estructura

```
CURSOS/
├── index.html          # Página principal
├── cursos.html         # Lista de cursos
├── curso.html          # Vista individual del curso
├── data/
│   └── cursos.json     # Base de datos de cursos
├── admin/
│   ├── index.html      # Interfaz de Decap CMS
│   └── config.yml      # Configuración del CMS
└── README.md
```

## ⚙️ Configuración de GitHub Pages

1. En el repositorio, ve a **Settings > Pages**
2. En **Source**, selecciona la rama `master` y carpeta `/ (root)`
3. Guarda los cambios
4. El sitio estará disponible en `https://andryugp.github.io/agpcursos/`

> **Nota**: La primera carga puede tardar unos minutos en procesarse.

## 🤝 Contribuir

1. Fork del repositorio
2. Crear rama para cambios: `git checkout -b feature/nueva-funcionalidad`
3. Realizar cambios
4. Commit y push: `git commit -m "Añadida nueva funcionalidad"`
5. Crear Pull Request

## 📝 Licencia

Este proyecto está bajo licencia MIT - libre para uso personal y comercial.

## 📧 Contacto

Andrés Ruiz - [@andryugp](https://github.com/andryugp)

<!-- Commit: v2.0 - Configuración Decap CMS con PAT token -->
<!-- GitHub Actions workflow will inject PAT for CMS authentication -->