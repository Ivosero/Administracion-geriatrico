# Serena — administración integral de geriátricos

Demo navegable de un centro operativo y una historia clínica electrónica para residencias geriátricas. Incluye resumen por turno, medicación, signos vitales, cuidados, residentes, contactos familiares, HCE, alertas y perfiles de acceso.

La HCE de demostración permite adjuntar PDF, imágenes, videos, documentos Word, planillas Excel, CSV y texto. Medicina y Enfermería pueden cargar medicación, y cada integrante de Enfermería puede registrar su turno y horario desde el encabezado.

### Mi ronda de medicación

Al ingresar con Enfermería, la sección Medicación abre por defecto **Mi ronda**: muestra únicamente residentes asignados, orden de recorrido, habitación, horario, medicamento, dosis, presentación, vía e indicaciones especiales. Permite registrar en un toque `Administrada` o seleccionar `Rechazada`, `Ausente`, `Omitida por indicación médica` y `No disponible`, conservando usuario y hora. Medicina y coordinación pueden acceder a la vista general.

> **Importante:** todos los nombres y datos son ficticios. Esta versión es una muestra y no debe utilizarse con información clínica real.

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2FIvosero%2FAdministracion-geriatrico)

## Acceso a la demostración

La pantalla de ingreso permite elegir rápidamente los cuatro perfiles. Las credenciales completas están documentadas en [DEMO_USERS.md](./DEMO_USERS.md).

- Administrador
- Médica
- Enfermería
- Administrativo

Después de cada inicio de sesión aparece un aviso sobre protección de datos personales y confidencialidad. Puede cerrarse con la **X** o con **Entendido, continuar**.

## Ejecutar localmente con Docker

Requisitos: Docker Desktop con Docker Compose.

```bash
git clone https://github.com/Ivosero/Administracion-geriatrico.git
cd Administracion-geriatrico
docker compose up --build -d
```

Abrir `http://localhost:3001`. Para detenerla, ejecutar `docker compose down`.

## Desarrollo sin Docker

```bash
npm install
npm run dev
```

Frontend: `http://localhost:5173` · API local: `http://localhost:3001`.

## Publicar desde GitHub en Vercel

1. Iniciar sesión en Vercel y elegir **Add New → Project**.
2. Importar `Ivosero/Administracion-geriatrico`.
3. Vercel detectará Vite; conservar `npm run build` y el directorio `dist`.
4. Seleccionar **Deploy**. Esta demo frontend no necesita variables de entorno.
5. Cada push a `main` actualizará producción; ramas y pull requests generarán previews.

La configuración de seguridad y rutas SPA está en `vercel.json`. El workflow `.github/workflows/ci.yml` comprueba que cada cambio compile.

## Arquitectura

- React + TypeScript + Vite.
- API local Express.
- PostgreSQL 16 y esquema en `database/init.sql`.
- Docker Compose para ejecución completa local.
- Modo ficticio autocontenido para la muestra en Vercel.

En la demo de Vercel los archivos se representan dentro de la sesión del navegador y no se conservan al recargar. Para producción, `clinical_attachments` almacena los metadatos y debe conectarse a almacenamiento privado mediante URLs firmadas.

## Seguridad y privacidad

Revisar [SECURITY.md](./SECURITY.md) y [PRIVACY.md](./PRIVACY.md). La autenticación incluida facilita la demostración y **no es apta para datos reales**.

## Comandos

```bash
npm run dev
npm run build
npm start
```
