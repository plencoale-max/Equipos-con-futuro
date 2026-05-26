# Equipos con futuro · 333

Sistema en vivo para la sesión de Team Building "Equipos con futuro".
Dos URLs públicas:

- **Dashboard** (lo que Alejo proyecta): `dashboard.html`
- **App de carga** (lo que abre cada escriba de grupo): `carga.html`

## Cómo subir a GitHub

### Paso 1 — Crear el repositorio

1. Andá a https://github.com/new
2. Repository name: **equipos-con-futuro**
3. Public (importante para que GitHub Pages funcione gratis)
4. Marcá "Add a README file"
5. Click en "Create repository"

### Paso 2 — Subir los 2 archivos

En el repo recién creado:

1. Click en "Add file" → "Upload files"
2. Arrastrá `dashboard.html` y `carga.html`
3. Commit message: "Versión inicial"
4. Click en "Commit changes"

### Paso 3 — Activar GitHub Pages

1. En el repo, click en **Settings** (engranaje arriba)
2. Menú izquierdo: **Pages**
3. En "Source", elegí **Deploy from a branch**
4. Branch: **main** · Folder: **/ (root)**
5. Click en **Save**

Esperá 1-2 minutos. Después arriba aparece el cartel:
**"Your site is live at https://plencoale-max.github.io/equipos-con-futuro/"**

### Paso 4 — URLs finales para usar el día de la sesión

- Dashboard: `https://plencoale-max.github.io/equipos-con-futuro/dashboard.html`
- App de carga: `https://plencoale-max.github.io/equipos-con-futuro/carga.html`

## Cómo se usa durante la sesión

1. Alejo abre el **dashboard** en su laptop y comparte pantalla en Teams.
2. A cada escriba de grupo se le manda por chat el link de **carga**.
3. Cada escriba abre el link, ingresa el código de su grupo (G1, G2, G3...) y su nombre.
4. A medida que cada miembro del grupo cuenta su historia, el escriba la carga.
5. Las historias aparecen en el dashboard en vivo (1-3 segundos de delay).

## Reset de datos

Si querés borrar todas las historias después de un piloto o entre sesiones,
andá al panel de Supabase → SQL Editor → corré esto:

```sql
delete from historias;
```

## Soporte técnico

Si el día de la sesión algo no funciona:

- **Dashboard no muestra historias** → recargar la pestaña (F5 o Cmd+R). Hay un refresh automático cada 30 segundos como respaldo.
- **App de carga dice "SIN CONEXIÓN"** → verificar internet. Si persiste, el escriba puede tomar nota en papel y cargar después.
- **Error al guardar una historia** → reintentar. Si vuelve a fallar, copiar el texto a otro lado por seguridad.

## Configuración técnica

- Base de datos: Supabase (proyecto `bwirfscpncqnzpbuflax`)
- Realtime: activado en tabla `historias`
- Frontend: HTML puro + JS, hosteado en GitHub Pages
- Sin dependencias adicionales más allá del CDN de Supabase JS
<!-- deploy refresh -->
