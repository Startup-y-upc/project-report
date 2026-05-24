# Capítulo IV — Entrega AV2 (Hito 3) — Sprint 2 (Resguardado)

Este archivo contiene las secciones del Capítulo IV que corresponden a la entrega AV2 (Sprint Review - Hito 3). Las secciones fueron movidas desde `chapter4.md` para mantener `chapter4.md` centrado en el entregable TB1 (Semana 7).

## Backend - Deployment Preparation (migrado desde chapter4.md)

**Backend - Deployment Preparation:**

**Plataforma:** AWS EC2 / Azure App Service (en preparación)

**Status:** En configuración para Sprint 2

**Steps realizados en Sprint 1:**

1. Creación de Docker image para Spring Boot
2. Configuración de MySQL RDS en AWS
3. Setup de GitHub Actions workflow para CI/CD
4. Configuración de secrets en GitHub (DB credentials, etc.)
5. Testing de deployment en ambiente local

[Insert screenshot: Docker build exitoso]
[Insert screenshot: GitHub Actions workflow setup]

## Database Deployment

**Plataforma:** AWS RDS MySQL 8.0

**Steps realizados:**

1. Creación de instancia RDS MySQL
2. Ejecución de scripts de schema para Vehicle Catalog
3. Configuración de security groups
4. Testing de conexión desde aplicación

[Insert screenshot: AWS RDS instance created]
[Insert screenshot: Database schema verification]

---

## Notas para AV2

- Completar despliegue del backend en entorno público (staging -> producción).
- Publicar Swagger UI en URL pública y actualizar `chapter4.md` con enlaces finales.
- Incluir evidencia de despliegue, logs de CI/CD y tests de humo en AV2.

---
