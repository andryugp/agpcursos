# Configuración de GitHub App para Decap CMS

## Configuración de GitHub App

Decap CMS ahora utiliza **GitHub App** en lugar de Personal Access Token (PAT) para una autenticación más segura.

### Paso 1: Crear GitHub App

1. Ve a: **Settings** → **Developer settings** → **GitHub Apps** → **New GitHub App**
2. Configura los siguientes campos:

| Campo | Valor |
|-------|-------|
| **App name** | Decap CMS for AGPCursos |
| **Description** | Decap CMS integration for AGPCursos website |
| **URL** | https://andryugp.github.io/agpcursos/ |
| **Callback URL** | https://andryugp.github.io/agpcursos/admin/ |

### Paso 2: Configurar Permisos

En la pestaña **Permissions**:

| Permiso | Nivel de acceso |
|---------|-----------------|
| Repository contents | Read and write |
| Metadata | Read |
| Pages | Read and write |

### Paso 3: Configurar Suscripción

En la pestaña **Subscribe to events** (puedes dejar todo por defecto).

### Paso 4: Generar Private Key

1. Haz clic en **Generate a private key**
2. Descarga el archivo `private-key.pem`
3. **NO** compartas este archivo

### Paso 5: Instalar el App

1. Ve a **Install App**
2. Selecciona tu cuenta/organización
3. Suscríbe a los repositorios necesarios (selecciona solo `agpcursos`)

### Paso 6: Agregar Secrets al Repositorio

Ve a **Settings** → **Secrets and variables** → **Actions** y agrega:

| Nombre del Secret | Valor |
|-------------------|-------|
| `APP_ID` | [Tu App ID numérico] |
| `APP_PRIVATE_KEY` | [Contenido del archivo private-key.pem] |

> **Nota**: Puedes pegar el contenido del private key directamente sin las comillas iniciales y finales.

### Paso 7: Verificar Configuración

El workflow `Deploy to GitHub Pages` se ejecutará automáticamente en el siguiente push, o puedes forzar un despliegue manual:

1. Ve a **Actions**
2. Selecciona el workflow "Deploy to GitHub Pages"
3. Haz clic en **Run workflow**
4. Ejecuta el workflow

---

## Verificación

Una vez configurado correctamente:

1. Accede a: `https://andryugp.github.io/agpcursos/admin/`
2. Deberías ver el formulario de login de GitHub
3. Inicia sesión con tu cuenta de GitHub
4. El CMS debería cargar sin errores

---

## ¿Qué cambios se realizaron?

- **admin/config.yml**: Eliminado el token PAT, ahora usa variables de entorno
- **workflow**: Usa `actions/create-github-app-token@v1` para generar tokens efímeros
- **Seguridad**: Los tokens nunca se almacenan en el repositorio

---

## Solución de Problemas

### Error: "GitHub App not found"
Verifica que `APP_ID` está correctamente configurado como número (sin comillas).

### Error: "Permission denied"
Asegúrate de que el App tiene permisos de "Read and write" para Repository contents.

### Error: "App not installed"
Ve a la página del App y haz clic en "Install App" para el repositorio agpcursos.