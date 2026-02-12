# Guía de Deployment - JABA References

## Paso 1: Crear cuenta en GitHub (si no tenés)
1. Andá a https://github.com
2. Hacé click en "Sign up"
3. Seguí los pasos para crear tu cuenta

## Paso 2: Crear un nuevo repositorio
1. Una vez logueado, hacé click en el "+" en la esquina superior derecha
2. Seleccioná "New repository"
3. Completá:
   - Repository name: `jaba-references` (o el nombre que quieras)
   - Description: "Visual reference board for creative inspiration"
   - Marcá como Public
   - NO marques "Add a README file" (ya tenemos uno)
4. Hacé click en "Create repository"

## Paso 3: Subir los archivos a GitHub

### Opción A: Desde la interfaz web (más fácil)
1. En tu repositorio nuevo, hacé click en "uploading an existing file"
2. Arrastrá estos archivos:
   - index.html
   - README.md
   - .gitignore
   - vercel.json
3. Escribí un mensaje de commit: "Initial commit"
4. Hacé click en "Commit changes"

### Opción B: Desde la terminal (si sabés usar git)
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/TU_USUARIO/jaba-references.git
git push -u origin main
```

## Paso 4: Crear cuenta en Vercel (si no tenés)
1. Andá a https://vercel.com
2. Hacé click en "Sign Up"
3. Elegí "Continue with GitHub" (es más fácil)
4. Autorizá a Vercel para acceder a tus repos de GitHub

## Paso 5: Deployar en Vercel
1. Una vez logueado en Vercel, hacé click en "Add New..."
2. Seleccioná "Project"
3. Buscá tu repositorio `jaba-references`
4. Hacé click en "Import"
5. En la configuración:
   - Framework Preset: "Other"
   - Root Directory: ./ (dejar por defecto)
   - Build Command: (dejar vacío)
   - Output Directory: (dejar vacío)
6. Hacé click en "Deploy"

## Paso 6: ¡Listo!
Después de 30-60 segundos, tu sitio va a estar live. Vercel te va a dar una URL tipo:
`https://jaba-references-tu-usuario.vercel.app`

## Compartir con otros
- Simplemente compartí la URL de Vercel
- Cualquiera que entre va a poder ver y usar la app
- **IMPORTANTE**: Cada persona va a tener su propia colección de referencias (porque localStorage es local a cada navegador)

## Actualizaciones futuras
Cada vez que hagas cambios:
1. Subí los archivos actualizados a GitHub
2. Vercel automáticamente va a re-deployar tu sitio

---

## ⚠️ Nota importante sobre compartir datos

Actualmente, esta app usa localStorage, lo que significa:
- ❌ Los datos NO se comparten entre usuarios
- ❌ Cada persona tiene su propia colección
- ❌ No hay sincronización

Si querés que TODOS vean y editen las MISMAS referencias, necesitás agregar una base de datos (Firebase, Supabase, etc.). Avisame si querés que te ayude con eso después.
