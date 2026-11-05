# Configuración de GitHub App para Decap CMS v3

## Requisitos Previos

Decap CMS v3 utiliza **OAuth del usuario** a través de GitHub App. NO requiere tokens de servicio ni secrets en el workflow de despliegue.

---

## Paso 1: Crear GitHub App

1. Ve a: **Settings** → **Developer settings** → **GitHub Apps** → **New GitHub App**
2. Configura los siguientes campos:

| Campo | Valor |
|-------|-------|
| **App name** | Decap CMS for AGPCursos |
| **Description** | Decap CMS integration for AGPCursos website |
| **URL** | https://andryugp.github.io/agpcursos/ |
| **Callback URL** | https://andryugp.github.io/agpcursos/admin/ |

---

## Paso 2: Configurar Permisos

En la pestaña **Permissions**:

| Permiso | Nivel de acceso |
|---------|-----------------|
| Repository contents | Read and write |
| Metadata | Read |
| Pages | Read and write |

---

## Paso 3: Configurar Suscripción

En la pestaña **Subscribe to events** (puedes dejar todo por defecto).

---

## Paso 4: Generar Private Key (Opcional)

> **Nota**: No es necesario para el flujo OAuth básico de Decap CMS v3. Solo necesario si planeas usar GitHub App para integraciones adicionales.

---

## Paso 5: Instalar el App

1. Ve a **Install App**
2. Selecciona tu cuenta/organización
3. Suscríbe al repositorio `agpcursos`

---

## Flujo de Trabajo

Decap CMS v3 usa **OAuth directo del usuario**:
1. El usuario accede a `https://andryugp.github.io/agpcursos/admin/`
2. Hace clic en "Login with GitHub"
3. Se autentica directamente con GitHub
4. No se necesitan secrets ni tokens de servicio

---

## Verificación

1. Accede a: `https://andryugp.github.io/agpcursos/admin/`
2. Deberías ver el formulario de login de GitHub
3. Inicia sesión con tu cuenta de GitHub
4. El CMS debería cargar sin errores

---

## ¿Qué se configuró?

- **admin/config.yml**: Backend configurado para GitHub con OAuth
- **deploy.yml**: Workflow de GitHub Actions sin tokens (correcto para Decap CMS v3)
- **Seguridad**: Autenticación OAuth segura, sin tokens en el repositorio

---

## Solución de Problemas

### Error: "GitHub App not found"
1. Asegúrate de que el GitHub App está instalado en el repositorio `agpcursos`
2. El App ID se muestra en la página del App (no es necesario agregarlo como secret)

### Error: "Permission denied"
Asegúrate de que el App tiene permisos de "Read and write" para Repository contents y Pages.

### Error: "App not installed"
Ve a la página del App y haz clic en "Install App" para el repositorio agpcursos.

### Error: Página en blanco o 404
Verifica que `admin/index.html` está en el repositorio y que el despliegue se completó:
1. Ve a **Actions** → **Deploy to GitHub Pages**
2. Verifica que el workflow se ejecutó correctamente