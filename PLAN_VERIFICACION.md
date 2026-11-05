# Plan de Verificación - AGPCursos

## ✅ Estado Actual

| Elemento | Estado | Comentario |
|----------|--------|------------|
| Estructura de archivos | ✅ Completada | admin/, data/, index.html, cursos.html, curso.html |
| JSON de cursos | ✅ Bien formado | 3 cursos con estructura válida |
| Videos embebidos | ✅ Configurados | YouTube + fallback Invidious |
| TailwindCSS | ✅ CDN cargado | Desde CDN |
| Plyr.io | ✅ CDN cargado | Reproductor accesible |
| Decap CMS config | ⚠️ Parcial | client_id configurado, client_secret opcional |

---

## 📋 Archivos Principales

### admin/config.yml
- Backend: GitHub OAuth con client_id configurado
- Colectiones: cursos, categorias, filtros
- **Nota**: client_secret es opcional en modo implícito

### data/cursos.json
```json
{
  "cursos": [
    {"id": "curso-001", "titulo": "Python desde Cero", "categoria": "Desarrollo", ...},
    {"id": "curso-002", "titulo": "Marketing Digital", "categoria": "Marketing", ...},
    {"id": "curso-003", "titulo": "Excel Avanzado", "categoria": "Productividad", ...}
  ],
  "categorias": [...],
  "filtros": {"niveles": [...], "modulos": [...]}
}
```

---

## 🔧 Pasos de Verificación Pendientes

### 1. Verificar GitHub Pages (OBLIGATORIO)
**Tiempo estimado:** 1-5 minutos

1. Ve a: https://github.com/andryugp/agpcursos/settings/pages
2. En "Build and deployment":
   - **Source:** `master` branch
   - **Folder:** `/ (root)`
3. URL del sitio: `https://andryugp.github.io/agpcursos/`
4. **Primer despliegue:** Puede tardar 1-5 minutos

### 2. Probar Panel de Administración
**URL a probar:** `https://andryugp.github.io/agpcursos/admin/`

Si el panel solicita credenciales:
- Inicia sesión con tu cuenta de GitHub
- Si hay error de OAuth, el client_secret puede ser necesario

### 3. Verificar Navegación
- Home: `https://andryugp.github.io/agpcursos/`
- Cursos: `https://andryugp.github.io/agpcursos/cursos.html`
- Detalle curso: `https://andryugp.github.io/agpcursos/curso.html?id=curso-001`
- Admin: `https://andryugp.github.io/agpcursos/admin/`

---

## 🛠️ Solución a Problemas Comunes

### Error: "Page build failed"
- Verifica que `index.html` esté en la raíz
- Asegúrate de que no hay archivos con extensión incorrecta

### Error: "Authentication failed" en Decap CMS
- El client_secret NO es obligatorio
- Si es necesario, agrega a `admin/config.yml`:
```yaml
client_secret: "PEGA_AQUI_TU_CLIENT_SECRET"
```

### Cursos no aparecen
- Verifica `data/cursos.json` existe en GitHub
- Reinicia el servidor o espera 2 min

---

## 📊 Cronología de Pruebas

- [ ] Verificar GitHub Pages activo y funcionando
- [ ] Probar acceso a `/admin/`
- [ ] Verificar edición de cursos desde el panel
- [ ] Probar videos en cursos.html
- [ ] Probar filtro por categoría
- [ ] Verificar responsive en móvil

---

## 🚀 Próximos Pasos

1. **GitHub Pages activo** - Una vez verificado, el sitio está en producción
2. **Panel de admin funcional** - Puedes añadir/editar cursos fácilmente
3. **Considerar HTTPS local** - Para desarrollo local, usa `npx serve .`

---

## 📞 Contacto

- GitHub: [@andryugp](https://github.com/andryugp)

---

## 📦 Archivos del Proyecto

```
agpcursos/
├── admin/
│   ├── config.yml       # Configuración Decap CMS
│   └── index.html       # Panel de administración
├── data/
│   └── cursos.json      # Base de datos de cursos
├── index.html           # Página principal
├── cursos.html          # Lista de cursos
├── curso.html           # Detalle del curso
├── PLAN_VERIFICACION.md # Este archivo
└── README.md            # Documentación
```