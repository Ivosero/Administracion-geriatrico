# Política de seguridad

## Alcance

Este repositorio es una demostración con datos ficticios. No está habilitado para almacenar historias clínicas reales.

## Controles incorporados

- Separación conceptual de roles.
- Aviso de confidencialidad posterior al inicio de sesión.
- Baja lógica de residentes para preservar trazabilidad.
- Modelo de auditoría en PostgreSQL.
- Variables sensibles excluidas del repositorio.
- Encabezados CSP, anti-iframe, `nosniff`, política de referentes y permisos restrictivos en Vercel.
- CI que compila cada cambio y cada pull request.

## Requisitos antes de producción

- Autenticación servidor con MFA y sesiones seguras (`HttpOnly`, `Secure`, `SameSite`).
- Autorización RBAC en cada endpoint, no solamente en la interfaz.
- Cifrado TLS y cifrado de datos y copias de seguridad en reposo.
- Registro de acceso, modificación, exportación, anulación y administración de usuarios.
- Política de mínimo privilegio, revisiones periódicas de acceso y baja inmediata.
- Gestión de consentimiento/base legal, plazos de conservación y ejercicio de derechos.
- Copias de seguridad probadas, plan de continuidad y respuesta a incidentes.
- Evaluación del proveedor, ubicación de datos y transferencias internacionales.
- Pruebas de seguridad, dependencias, secretos y revisión profesional previa al lanzamiento.

## Reporte de vulnerabilidades

No publicar datos sensibles en un issue. Contactar privadamente al responsable del repositorio.
