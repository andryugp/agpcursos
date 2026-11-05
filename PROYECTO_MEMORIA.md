# 📚 PROYECTO MEMORIA - Plataforma de Cursos Online

**Última actualización:** 2026-11-04

## 🎯 Visión
Plataforma web de cursos en línea ultra-ligera con videos embebidos y bloqueo de anuncios.

---

## 🛠️ Estado Actual del Proyecto

| Aspecto | Estado |
|---------|--------|
| Tecnologías elegidas | **Pendiente - PASO 1** |
| Hosting | **Pendiente - PASO 1** |
| Base de datos | **Pendiente - PASO 1** |
| Bloqueo anuncios | **Pendiente - PASO 1** |

---

## 🧱 Arquitectura Propuesta

### Stack Tecnológico (RECOMENDADO)
- **Frontend:** HTML5 + TailwindCSS + JavaScript vanilla
- **Hosting:** GitHub Pages (gratis)
- **Base de datos:** JSON estático
- **Reproductor:** Plyr.io + alternativa invidious

### Estructura de Datos
```json
{
  "cursos": [
    {
      "id": "curso-001",
      "titulo": "",
      "descripcion": "",
      "categoria": "",
      "nivel": "",
      "video_url": "",
      "modulo": ""
    }
  ],
  "categorias": []
}
```

---

## 📁 Índice de Archivos Creados

| Archivo | Estado | Propósito |
|---------|--------|-----------|
| PROYECTO_MEMORIA.md | ✅ CREADO | Fuente de verdad |
| index.html | ⏳ PENDIENTE | Página principal |
| cursos.js | ⏳ PENDIENTE | Lógica de cursos |
| data/cursos.json | ⏳ PENDIENTE | Base de datos |
| assets/css/tailwind.css | ⏳ PENDIENTE | Estilos |

---

## 🔧 Cambios Pendientes

1. ✅ Crear estructura básica
2. ⏳ Implementar página principal
3. ⏳ Configurar Plyr.io
4. ⏳ Crear base de datos de ejemplo

---

## 📌 Notas Clave

- **No alojar videos en servidor** → Ahorro de ancho de banda
- **Reproductor limpio** → Menos distracciones
- **JSON estático** → Sin backend necesario