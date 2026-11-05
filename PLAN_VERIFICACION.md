# Plan de Verificación - AGPCursos

## ✅ Estado Actual

| Elemento | Estado | Comentario |
|----------|--------|------------|
| Estructura de archivos | ✅ Completada | admin/, data/, index.html, cursos.html, curso.html |
| JSON de cursos | ✅ Bien formado | 3 cursos con estructura válida |
| Videos embebidos | ✅ Configurados | YouTube + fallback Invidious |
| TailwindCSS | ✅ CDN cargado | Desde CDN |
| Plyr.io | ✅ CDN cargado | Reproductor accesible |
| Decap CMS config | ✅ Configurado | client_id configurado, client_secret opcional |
| GitHub Actions workflow | ✅ Commitado y push | deploy.yml con permisos pages: write, id-token: write |

---

## 🔧 Configuración Pendiente (Manual)

### Paso 1: Configurar GitHub Pages
**Ubicación:** GitHub → Settings → Pages

**Configuración requerida:**
1. Source: **Branch `master`**, folder **`/`** (raíz)
2. Guardar cambios
3. Esperar a que se genere la URL automáticamente

**URL esperada:** `https://andryugp.github.io/agpcursos/`

---

### Paso 2: Verificar Workflow de GitHub Actions
**Ubicación:** GitHub → Actions → "Deploy to GitHub Pages"

1. Verificar que el workflow se ejecutó correctamente tras el push
2. Chequear logs del job "Deploy to GitHub Pages"
3. Confirmar estado "Success"

---

### Paso 3: Probar el sitio
Una vez configurado GitHub Pages y completado el workflow:

1. Visitar: `https://andryugp.github.io/agpcursos/`
2. Verificar:
   - Página de inicio carga correctamente
   - Lista de cursos visible
   - Navegación entre páginas funciona
   - Videos se reproducen

---

## 🛠️ Archivos Pendientes de Commit

| Archivo | Estado | Acción requerida |
|---------|--------|------------------|
| `.github/workflows/deploy.yml` | ✅ Commitado | Listo |
| `.gitignore` | ✅ Commitado | Listo |
| `PLAN_VERIFICACION.md` | 📝 Actual | Este archivo |

---

## 🔐 Configuración Decap CMS

### Requisitos para el panel de administración:
1. **OAuth App** configurada en GitHub con:
   - Client ID: `Ov23liIGvELSXRwjZvfn`
   - Callback URL: `https://andryugp.github.io/agpcursos/admin/`

2. **Permisos necesarios** del OAuth App:
   - public_repo (para lectura/escritura del repositorio)

3. **Acceso al panel:**
   - URL: `https://andryugp.github.io/agpcursos/admin/`
   - Requiere login GitHub

---

## 📋 Checklist de Verificación Final

- [ ] GitHub Pages configurado en Settings → Pages
- [ ] Branch `master` seleccionada como source
- [ ] Workflow de GitHub Actions ejecutado exitosamente
- [ ] URL principal funcionando: `https://andryugp.github.io/agpcursos/`
- [ ] Panel de administración accesible: `/admin/`
- [ ] Login GitHub funciona en el panel de administración
- [ ] Edición de cursos JSON posible desde el panel

---

## 🚨 Notas Importantes

1. **GitHub Pages** debe configurarse **manualmente** desde Settings del repositorio
2. El primer despliegue puede tardar unos minutos en completarse
3. El panel de administración Decap CMS requiere autenticación GitHub
4. Los cambios en `data/cursos.json` se reflejarán inmediatamente en el sitio

---

## 🎯 Próximos Pasos

1. Configurar GitHub Pages manualmente desde Settings
2. Verificar el despliegue automático
3. Probar el panel de administración
4. Documentar resultados