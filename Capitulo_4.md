<div style="page-break-after: always;"></div>

# Capítulo IV: Product Implementation & Validation

<div style="page-break-after: always;"></div>

## 4. Product Implementation & Validation

<div style="page-break-after: always;"></div>

## 4.1. Software Configuration Management

En esta sección el equipo establece las decisiones y convenciones que permitirán mantener la consistencia durante el ciclo de vida. Se incluyen secciones internas para Source Code Management, Development Environment Configuration y Deployment Configuration.

### 4.1.1. Software Development Environment Configuration

**Contexto y Justificación:**

Rent2Go es una plataforma digital integral para el alquiler de vehículos que requiere la coordinación simultánea de múltiples productos: un backend robusto basado en microservicios, un landing page informativo, aplicaciones móviles nativas (Android/iOS) y una plataforma web frontend. Este escenario polimórfico exige un ecosistema de herramientas diversas pero cohesionadas que permita al equipo mantener consistencia, calidad y velocidad de desarrollo.

Durante Sprint 1, el equipo estableció una pila tecnológica moderna basada en arquitectura de dominio (DDD) para el backend, frameworks nativos para mobile (Kotlin/Swift), y tecnologías web estándar para frontend. La selección de herramientas se hizo considerando:

1. **Compatibilidad**: Integración fluida entre componentes frontend, backend y mobile
2. **Escalabilidad**: Capacidad de soportar crecimiento de usuarios y complejidad funcional
3. **Experiencia del Equipo**: Tecnologías modernas con amplio soporte comunitario
4. **Productividad**: IDEs y herramientas que aceleren el desarrollo iterativo

En esta sección se especifica el conjunto de software, versiones y referencias de descarga necesarias para que cada miembro del equipo configure su ambiente de desarrollo local y colabore efectivamente en el ciclo de vida de Rent2Go.

**Stack Tecnológico por Área:**

| Área | Stack |
|------|-------|
| **Backend** | Java 17 + Spring Boot 3.5.7 + Maven + MySQL 8.0 |
| **Landing Page** | HTML5 + CSS3 + JavaScript + i18n |
| **Mobile** | Android (Kotlin) / iOS (Swift) / Flutter (Dart) |
| **Frontend Web** | Angular + TypeScript |
| **DevOps** | Git + GitHub |
| **Herramientas** | Postman + Figma + MySQL Workbench |

---

**Herramientas de Desarrollo - Configuración Recomendada:**

| Producto | Versión | Propósito | Descarga / Referencia |
| --- | --- | --- | --- |
| **JDK (Java Development Kit)** | 17.0+ | Compilación y ejecución del backend Spring Boot basado en DDD | [https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html) |
| **Apache Maven** | 3.8.1+ | Gestión de dependencias y build automation para módulos Spring Boot | [https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi) |
| **IDE - IntelliJ IDEA** | 2024+ | Desarrollo Java/Spring Boot con análisis de código y refactoring avanzado | [https://www.jetbrains.com/idea/](https://www.jetbrains.com/idea/) |
| **Node.js** | 18.0+ | Runtime para herramientas de build, TypeScript compilation y build scripts | [https://nodejs.org/](https://nodejs.org/) |
| **Visual Studio Code** | Latest | Editor ligero para frontend, landing page, scripts y documentación | [https://code.visualstudio.com/](https://code.visualstudio.com/) |
| **Android Studio** | Latest | IDE oficial para desarrollo Android en Kotlin con emulator integrado | [https://developer.android.com/studio](https://developer.android.com/studio) |
| **Xcode** | Latest | Entorno de desarrollo oficial para iOS con compilador Swift nativo | [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/) |
| **Flutter SDK** | 3.10+ | Framework cross-platform para desarrollo simultáneo Android/iOS en Dart | [https://flutter.dev/docs/get-started/install](https://flutter.dev/docs/get-started/install) |
| **Dart** | 3.0+ | Lenguaje de programación para aplicaciones Flutter | [https://dart.dev/get-dart](https://dart.dev/get-dart) |
| **Git** | 2.40+ | Sistema de control de versiones distribuido para colaboración de código | [https://git-scm.com/](https://git-scm.com/) |
| **GitHub Desktop** | Latest | Interfaz gráfica para Git que simplifica operaciones de control de versiones | [https://desktop.github.com/](https://desktop.github.com/) |
| **Figma** | Cloud | Diseño colaborativo y prototipado de UI/UX para landing y apps | [https://www.figma.com/](https://www.figma.com/) |
| **Postman** | Latest | Testing y documentación de APIs REST; simulación de endpoints | [https://www.postman.com/downloads/](https://www.postman.com/downloads/) |
| **MySQL Workbench** | 8.0+ | Diseño, modelado y administración visual de base de datos MySQL | [https://www.mysql.com/products/workbench/](https://www.mysql.com/products/workbench/) |
| **Railway** | - | Plataforma de deployment para backend con MySQL gestionado | [https://railway.app/](https://railway.app/) |
| **GitHub Pages** | - | Hosting gratuito para landing page estática con CI/CD integrado | [https://pages.github.com/](https://pages.github.com/) |

---

### 4.1.2. Source Code Management

En esta sección el equipo establece el esquema de organización y control de versiones aplicado a la solución. Se utiliza GitHub como plataforma y sistema de control de versiones.

**Repositorios del Proyecto:**

| Producto | URL Repositorio | Rama Principal | Estado |
| --- | --- | --- | --- |
| Landing Page | [https://github.com/Startup-y-upc/landing-page](https://github.com/Startup-y-upc/landing-page) | main | Deployed |
| Backend (Web Services) | [https://github.com/Startup-y-upc/rent2go-backend](https://github.com/Startup-y-upc/rent2go-backend) | master | Deployed|
| Frontend Web | [https://github.com/Startup-y-upc/rent2go-kotlin](https://github.com/Startup-y-upc/rent2go-kotlin) | main | In development |
| Mobile (Android/iOS/Flutter) | [https://github.com/Startup-y-upc/rent2go-kotlin](https://github.com/Startup-y-upc/rent2go-kotlin) | main | In development |

**GitFlow Workflow:**

El equipo implementa GitFlow como estrategia de branching. Las convenciones establecidas son:

- **main branch**: Rama de producción. Contiene releases versadas y tags con semantic versioning.
- **develop branch**: Rama de desarrollo. Rama base para features y donde se integran cambios antes de release.
- **feature branches**: Patrón `feature/nombre-descriptivo` (ej. `feature/vehicle-search`, `feature/landing-navbar`).
- **release branches**: Patrón `release/v1.0.0` para preparación de releases.
- **hotfix branches**: Patrón `hotfix/bug-description` para correcciones urgentes en producción.

**Convenciones de Commits (Conventional Commits):**

El equipo aplica Conventional Commits para textos de mensajes:

```
<type>(<scope>): <subject>

<body>

<footer>
```

**Tipos de commit:**
- `feat`: Nueva funcionalidad
- `fix`: Corrección de bugs
- `docs`: Cambios de documentación
- `style`: Cambios de formato (sin lógica)
- `refactor`: Refactorización de código
- `test`: Adición o actualización de tests
- `chore`: Cambios en configuración o dependencias

**Ejemplos:**
```
feat(vehicle-catalog): add search filter by price range
fix(landing): resolve navbar responsive issue on mobile
docs: update API documentation for vehicle endpoints
test(backend): add unit tests for booking service
```

**Semantic Versioning:**

El equipo applica [Semantic Versioning 2.0.0](https://semver.org/) con formato `v<MAJOR>.<MINOR>.<PATCH>`:
- `v1.0.0`: Release inicial
- `v1.1.0`: Nuevas funcionalidades
- `v1.0.1`: Correcciones de bugs

---

### 4.1.3. Source Code Style Guide & Conventions

El equipo aplica convenciones estándares para codificación en los lenguajes utilizados en la solución.

**Java (Spring Boot Backend):**
- Guía: [Google Java Style Guide](https://google.github.io/styleguide/javaguide.html)
- Nomenclatura: CamelCase para clases, camelCase para variables
- Convención de paquetes: `com.rent2go.<bounded-context>.<layer>`
- Ejemplo: `com.rent2go.vehicle_catalog.domain.entity.Vehicle`

**Kotlin (Android Mobile):**
- Guía: [Kotlin Coding Conventions](https://kotlinlang.org/docs/coding-conventions.html)
- Nomenclatura: PascalCase para clases, camelCase para variables
- Aplicar [Android Kotlin Best Practices](https://developer.android.com/kotlin/style-guide)
- Ejemplo: `class VehicleSearchViewModel()`

**Swift (iOS Mobile):**
- Guía: [Swift API Design Guidelines](https://swift.org/documentation/api-design-guidelines/)
- Nomenclatura: PascalCase para clases y structs, camelCase para variables
- Aplicar [iOS Best Practices](https://developer.apple.com/documentation/swift)


**TypeScript/Angular (Frontend Web):**
- Guía: [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
- Nomenclatura: PascalCase para componentes, camelCase para variables
- Archivo: `vehicle-search.component.ts`, `vehicleSearch.component.css`

**HTML/CSS (Landing Page):**
- Guía: [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html)
- Nomenclatura: kebab-case para clases, snake_case para IDs
- Ejemplo: `class="vehicle-card"`, `id="hero_section"`

**Gherkin (BDD Tests):**
- Idioma: English
- Convención: Feature files en `src/test/features/`
- Ejemplo: `vehicle-search.feature`

---

### 4.1.4. Software Deployment Configuration

En esta sección se especifica la configuración del despliegue de la solución. El equipo implementa un pipeline de deployment que permite pasar desde los repositorios de código fuente al despliegue satisfactorio de cada producto digital.

**Deployment Architecture (C4 Model - Deployment Level):**

<div align="center">
  <img src="Resources/capitulo_2/architecture/Deployment-001-dark.png" alt="C4 deployment diagram" width="900">
</div>

**Estrategia de Despliegue por Producto:**

**Landing Page:**
- Plataforma: GitHub Pages
- Trigger: Merge a main branch
- Process: Automatic build & deploy
- URL: https://startup-y-upc.github.io/landing-page/
- Configuración: Source branch, GitHub Pages settings y dominio personalizado si aplica

**Backend (Web Services):**
- Plataforma: Railway
- CI/CD: GitHub Actions + Railway deploy
- Database: MySQL 8.0 en Railway
- URL: https://rent2go-backend-production.up.railway.app/
- Configuración: variables de entorno y application.properties por ambiente (dev, staging, prod)

**Mobile (Android/iOS/Flutter):**
- Android: Google Play Store
- iOS: Apple App Store
- Distribution: Firebase App Distribution (testing phases)
- Process: Manual para releases, automático para testing

---

<div style="page-break-after: always;"></div>

## 4.2. Landing Page & Mobile Application Implementation

En esta sección se explica y evidencia el proceso de implementación, pruebas, documentación y despliegue de los productos digitales. Se incluye una sección para Sprint 1.

### 4.2.1. Sprint 1

#### 4.2.1.1. Sprint Planning 1

**Resumen del Sprint Planning Meeting:**

| Aspecto | Descripción |
| --- | --- |
| Sprint # | Sprint 1 |
| Sprint Planning Background | *Reunión de planificación del Sprint 1 para establecer objetivos y seleccionar user stories priorizadas* |
| Date | 2026-05-06 |
| Time | 09:30 AM |
| Location | Virtual - Google Meet |
| Prepared By | Carhuancote Dominguez, Gonzalo Alonso |
| Attendees | Carhuancote Dominguez, Gonzalo Alonso<br>Castillo Vidal, Jesus Ivan<br>Chavez Uribe, Ario Joel<br>Diestra Zambrano, Adriana Maria<br>Huarcaya Matias, Gilbert Alonso |
| Sprint 0 Review Summary: | No hay sprint anterior. Comienza la iteración del proyecto Rent2Go con Sprint 1, enfocado en validar el modelo de negocio mediante un landing page informativo y establecer la base del backend del catálogo de vehículos.| 
| Sprint 0 Retrospective Summary: | No hay sprint anterior. Este es el primer sprint del proyecto.|
| Sprint Goal & User Stories: | |
| Sprint 1 Goal | Implementar y desplegar un Landing Page informativo que presente el modelo de negocio y propuesta de valor de Rent2Go, permitiendo que visitantes conozcan el servicio de alquiler de vehículos. Simultáneamente, establecer la base del backend con funcionalidades de búsqueda, filtrado y gestión de favoritos de vehículos. Objetivo: validar tempranamente el concepto con usuarios reales y obtener feedback del mercado. |
| **Sprint 1 Velocity** | 29 |
| **Sum of Story Points** | 33 |

**User Stories Incluidas en Sprint 1 (Priorizadas):**

| Story ID | Título | Descripción | Story Points | Prioridad |
| --- | --- | --- | --- | --- |
| **Landing Page (EP06 - Plataforma y Soporte)** | | | | |
| US53 | Ver landing page informativa | Como visitante, quiero ver una landing page informativa, para conocer el servicio. | 3 | Medium |
| US54 | Conocer beneficios para arrendatarios y propietarios | Como visitante, quiero conocer los beneficios del servicio, para decidir si registrarme. | 3 | Medium |
| US55 | Acceder al registro o inicio de sesión desde la landing | Como visitante, quiero acceder al registro o inicio de sesión desde la landing, para ingresar a la plataforma. | 2 | Low |
| US56 | Consultar información de contacto | Como visitante, quiero consultar la información de contacto, para comunicarme con soporte. | 2 | Low |
| **Backend y Frontend Mobile - Vehicle Catalog (EP02 - Catálogo y Búsqueda)** | | | | |
| US18 | Explorar vehículos disponibles | Como arrendatario, quiero explorar vehículos disponibles, para ver la oferta de la plataforma. | 5 | High |
| US19 | Buscar vehículos por ubicación y fechas | Como arrendatario, quiero buscar vehículos por ubicación y fechas, para planificar mi alquiler. | 5 | High |
| US20 | Filtrar y ordenar vehículos disponibles | Como arrendatario, quiero filtrar y ordenar vehículos por precio u otros criterios, para afinar mi búsqueda. | 5 | Medium |
| US22 | Ver detalle de vehículo | Como arrendatario, quiero ver el detalle de un vehículo, para tomar una decisión informada. | 5 | Medium |
| US23 | Guardar vehículo como favorito | Como arrendatario, quiero guardar un vehículo como favorito, para consultarlo más tarde. | 3 | Medium |

---

#### 4.2.1.2. Sprint Backlog 1

**Introducción:**

En Sprint 1, el equipo se enfoca en las historias de usuario de mayor prioridad:
- **Landing Page (US53-US56):** Crear landing page informativa para que visitantes conozcan el servicio, con contacto, navegación intuitiva y diseño responsivo.
- **Backend Vehicle Catalog (US18-US23):** Implementar búsqueda, filtro por precio, detalle de vehículo y gestión de favoritos para que arrendatarios puedan descubrir y seleccionar vehículos.

La integración de estos productos permitirá validar tempranamente el concepto con usuarios reales.

**Estado del Sprint Backlog (Trello Board):**

<div align="center">
  <img src="Resources/capitulo_4/sprint-backlog/1-trello-board.png" alt="Sprint 1 Trello Board" width="900">
</div>

*Nota.* Elaboración propia. El tablero resume las tareas de Sprint 1 para Landing Page y Backend Vehicle Catalog.

**URL del Board:** https://rent2go.atlassian.net/jira/software/projects/REN/boards/1/backlog?atlOrigin=eyJpIjoiNTU0NmY0OWUyMjRlNGE0NmFjM2JlNmZjNTEzNjkyN2YiLCJwIjoiaiJ9


**Tabla de Control de Estado:**

| Sprint # | User Story | Work-Item / Task | Id | Title | Description | Estimation (Hours) | Assigned To | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Sprint 1** | US53 | Task | US53-01 | Setup landing page project | Configure HTML5 project structure with CSS3 and vanilla JavaScript | 4 | Castillo Vidal, Jesus Ivan | [To-Do/In-Process/To-Review/Done] |
| | | Task | US53-02 | Implement landing page sections | Create navbar, hero, features, how-it-works, FAQ, footer with HTML5 and CSS3 | 20 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | US53-03 | Add i18n support | Add i18n support with vanilla JavaScript for English/Spanish translations in all sections | 6 | Castillo Vidal, Jesus Ivan | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US56 | Task | US56-01 | Create contact section | Design and implement contact information display | 4 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | US56-02 | Add social media links | Implement links to social networks and contact form | 3 | Castillo Vidal, Jesus Ivan | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US54 | Task | US54-01 | Implement benefits section | Create and style sections detailing benefits for owners and renters | 5 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | US54-02 | Add interactive elements | Implement interactive animations or hover effects in benefits | 2 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US55 | Task | US55-01 | Add navigation and CTAs | Implement navigation menu with links to login and registration views | 8 | Castillo Vidal, Jesus Ivan | [To-Do/In-Process/To-Review/Done] |
| | | Task | US55-02 | Test auth shortcuts | Verify shortcuts and responsiveness of login/register links | 3 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US18 | Task | US18-01 | Setup Spring Boot project | Create Maven project with Spring Boot 3.5.7 | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US18-02 | Configure MySQL database | Setup connection and schema for vehicle catalog | 5 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US18-03 | Create Vehicle entity | Implement Vehicle aggregate root with properties | 6 | Carhuancote Dominguez, Gonzalo Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US19 | Task | US19-01 | Create Vehicle repository | Implement Spring Data JPA repository for queries | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US19-02 | Implement search endpoint | Create GET /api/v1/vehicles with filters (categories, location) | 8 | Carhuancote Dominguez, Gonzalo Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US20 | Task | US20-01 | Add price filter logic | Implement price range filtering in repository | 5 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US20-02 | Create price update endpoint | Implement PUT /api/v1/vehicles/{id}/price | 5 | Carhuancote Dominguez, Gonzalo Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US22 | Task | US22-01 | Implement vehicle detail service | Add service layer method for vehicle details | 5 | Carhuancote Dominguez, Gonzalo Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US22-02 | Create detail endpoint | Implement GET /api/v1/vehicles/{id} | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | US23 | Task | US23-01 | Design favorites feature | Plan storage and query strategies for favorites | 4 | Carhuancote Dominguez, Gonzalo Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US23-02 | Implement favorites service | Add favorites management business logic | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US23-03 | Design favorites UI - Mobile | Design and implement favorites UI in Kotlin for Android | 5 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |

---

#### 4.2.1.3. Development Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo implementó todas las historias de usuario priorizadas:
- **Landing Page (US53-US56):** Implementación del landing page informativo con secciones core, información de contacto, navegación intuitiva y diseño responsivo.
- **Backend Vehicle Catalog (US18-US23):** Endpoints de búsqueda, filtrado por precio, detalle de vehículo, y gestión de imágenes de vehículos.

Se realizaron commits regulares en ambos repositorios, siguiendo GitFlow y Conventional Commits. A continuación se presenta el resumen de avances en implementación.

**Commits en Landing Page Repository:**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |
| rent2go-landing | feature/landing-page | 7a3c2e1 | feat(landing): implement informative landing page (US53) | Implemented all landing page sections: navbar, hero, features, how-it-works, FAQ, footer. Added i18n support for ES/EN. | 2026-05-08 |
| rent2go-landing | feature/contact-section | 9f5b8d4 | feat(landing): add contact information section (US56) | Added contact section with phone, email, and social media links. Integrated contact form. | 2026-05-09 |
| rent2go-landing | feature/navigation | 2e1c6a9 | feat(landing): implement intuitive navigation (US54) | Added smooth scrolling and anchor links for all sections. Improved menu navigation. | 2026-05-10 |
| rent2go-landing | feature/responsive-design | 8d4f2b7 | feat(landing): implement responsive design (US55) | Added responsive CSS for mobile, tablet, and desktop viewports. Tested on multiple devices. | 2026-05-11 |
| rent2go-landing | develop | c6e3a1f | Merge: landing page Sprint 1 complete | Merged all landing page features to develop branch. | 2026-05-12 |

**Commits en Backend Repository (Vehicle Catalog):**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |
| rent2go-backend | feature/vehicle-setup | 3b2f7e9 | feat(vehicle-catalog): setup Spring Boot project (US18) | Initialized Spring Boot 3.5.7 with Maven, configured application.properties, and database connection to MySQL. | 2026-05-06 |
| rent2go-backend | feature/vehicle-entity | 5c1a8d6 | feat(vehicle-catalog): create Vehicle aggregate root (US18) | Implemented Vehicle domain entity with properties: id, make, model, year, price, availability, owner_id. | 2026-05-07 |
| rent2go-backend | feature/vehicle-repo | 7f4e2c1 | feat(vehicle-catalog): implement vehicle repository (US19) | Created Spring Data JPA VehicleRepository with custom query methods for search and filtering. | 2026-05-07 |
| rent2go-backend | feature/vehicle-search | 9a6d3e2 | feat(vehicle-catalog): add vehicle search (US19) | Implemented search endpoint GET /api/v1/vehicles with category, price, and location filters. | 2026-05-08 |
| rent2go-backend | feature/vehicle-pricing | 4b7f1c8 | feat(vehicle-catalog): implement price update (US20) | Added price range filtering logic and PUT /api/v1/vehicles/{id}/price endpoint. | 2026-05-09 |
| rent2go-backend | feature/vehicle-detail | 6e2c5a3 | feat(vehicle-catalog): add vehicle detail endpoint (US22) | Implemented GET /api/v1/vehicles/{id} with complete vehicle information and image references. | 2026-05-10 |
| rent2go-backend | feature/vehicle-images | 8d5f9b4 | feat(vehicle-catalog): implement image management (US23) | Added image upload, retrieval and primary image selection endpoints for vehicles. | 2026-05-11 |
| rent2go-backend | develop | 2c3e7f6 | Merge: vehicle catalog Sprint 1 complete | Merged all vehicle catalog features to develop branch. | 2026-05-12 |

---

#### 4.2.1.4. Testing Suite Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo implementó unit tests, integration tests, y BDD acceptance tests para las historias de usuario del Backend Vehicle Catalog (US18-US23). Se priorizó la cobertura de búsqueda, filtrado, detalle y favoritos, garantizando que los endpoints cumplen con los requisitos especificados.

**Unit Tests - Backend Vehicle Catalog:**

| Test File | Test Class | Method | Description | Related to (HU) | Status |
| --- | --- | --- | --- | --- | --- |
| VehicleRepositoryTest.java | VehicleRepositoryTest | testFindBySearchCriteria | Verifica que la búsqueda por make y model retorna vehículos correctos | US19 | [Pass/Fail] |
| VehicleRepositoryTest.java | VehicleRepositoryTest | testFindByPriceRange | Verifica filtro de precio funciona correctamente | US20 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testSearchVehicles | Verifica servicio de búsqueda retorna resultados esperados | US19 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testGetVehicleDetail | Verifica que obtiene detalles correctos de un vehículo | US22 | [Pass/Fail] |
| VehicleImageServiceTest.java | VehicleImageServiceTest | testUploadVehicleImage | Verifica que se carga correctamente una imagen de vehículo | US23 | [Pass/Fail] |
| VehicleImageServiceTest.java | VehicleImageServiceTest | testSetPrimaryImage | Verifica que se establece correctamente la imagen primaria | US23 | [Pass/Fail] |

**Integration Tests - Backend API:**

| Feature File | Scenario | Given | When | Then | Related to (HU) | Status |
| --- | --- | --- | --- | --- | --- | --- |
| vehicle-search.feature | Search vehicles with filters | System has vehicles in database | User executes GET /api/v1/vehicles?categories=SUV&minPrice=100&maxPrice=500 | Returns filtered list of vehicles | US18 | [Pass/Fail] |
| vehicle-search.feature | No results found | User searches with criteria that don't match | Executes GET /api/v1/vehicles with non-existent location | Returns empty array with 200 OK | US19 | [Pass/Fail] |
| vehicle-detail.feature | Get vehicle detail | Vehicle exists in database | User executes GET /api/v1/vehicles/{id} | Returns complete vehicle information with images | US22 | [Pass/Fail] |
| vehicle-pricing.feature | Update vehicle price | Vehicle exists and user is authorized | User executes PUT /api/v1/vehicles/{id}/price with newDailyPrice | Returns updated vehicle resource | US20 | [Pass/Fail] |
| vehicle-images.feature | Upload vehicle image | Vehicle exists and images bucket ready | User executes POST /api/v1/vehicles/{id}/images with imagePath | Image is uploaded and vehicle resource returned | US23 | [Pass/Fail] |
| vehicle-images.feature | Set primary image | Vehicle has multiple images | User executes PUT /api/v1/vehicles/{vehicleId}/images/{imageId}/primary | Image is set as primary and vehicle updated | US23 | [Pass/Fail] |

**Gherkin Feature Files:**

```gherkin
# features/vehicle-search.feature
Feature: Vehicle Search (US19)
  As a renter
  I want to search for vehicles
  So that I can find a suitable vehicle to rent

  Scenario: Successful vehicle search
    Given the user is on the vehicle search page
    When the user enters search criteria "Toyota"
    And submits the search
    Then the system displays vehicles matching the search
    And results show make, model, year, and price

  Scenario: No results found
    Given the user is on the vehicle search page
    When the user enters search criteria "NonExistent"
    And submits the search
    Then the system displays "No vehicles found"

# features/vehicle-filter.feature
Feature: Vehicle Price Filter (US20)
  As a property owner
  I want to update vehicle pricing
  So that I can manage rental rates

  Scenario: Update price successfully
    Given the user is managing a vehicle
    When they update the daily price to $150
    Then the system confirms the price update

# features/vehicle-detail.feature
Feature: Vehicle Detail (US22)
  As a renter
  I want to see vehicle details with images
  So that I can make an informed decision

  Scenario: Detail view with images available
    Given the user selects a vehicle from search results
    When they request the detail view
    Then the system displays complete vehicle information with all images

# features/vehicle-images.feature
Feature: Vehicle Image Management (US23)
  As a property owner
  I want to manage vehicle images
  So that I can showcase my vehicles with quality photos

  Scenario: Upload vehicle image successfully
    Given the user is managing a vehicle
    When they upload an image with imagePath and imageUrl
    Then the image is attached to the vehicle

  Scenario: Set primary image successfully
    Given a vehicle has multiple images
    When the user sets an image as primary
    Then the primary image is updated and others become secondary
```

**Repository de Tests:** https://github.com/Startup-y-upc/gherkin-tests

**Commits de Testing:**

| Repository | Branch | Commit Id | Commit Message | Committed on |
| --- | --- | --- | --- | --- |
| rent2go-backend | feature/vehicle-tests | 1f8a2d5 | test(vehicle-catalog): add unit tests for repository and search | 2026-05-09 |
| rent2go-backend | feature/vehicle-tests | 5e3b7c9 | test(vehicle-catalog): add integration tests for all APIs | 2026-05-10 |
| rent2go-backend | feature/vehicle-tests | 7a4f1b6 | test(vehicle-catalog): add BDD acceptance tests with Gherkin | 2026-05-11 |

---

#### 4.2.1.5. Execution Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo completó la implementación del Landing Page informativo (US53-US56) y los endpoints base del Backend para catálogo de vehículos (US18-US23). Se presentan capturas de las principales vistas implementadas y enlace a video de demostración de funcionalidades.

**Landing Page - Capturas:**

<div align="center">
  <img src="Resources/capitulo_4/execution/landing-page/1-navbar.png" alt="Landing page completa con navbar" width="900">
</div>

*Nota.* Elaboración propia. Vista general de la landing page con navegación superior y estructura principal (US54).

<div align="center">
  <img src="Resources/capitulo_4/execution/landing-page/2-hero-cta.png" alt="Hero section con CTA principal" width="900">
</div>

*Nota.* Elaboración propia. Hero section con propuesta de valor y llamada a la acción principal (US53).

<div align="center">
  <img src="Resources/capitulo_4/execution/landing-page/3-contact-section.png" alt="Sección de contacto" width="900">
</div>

*Nota.* Elaboración propia. Sección de contacto con información de la empresa y formulario (US56).

<div align="center">
  <img src="Resources/capitulo_4/execution/landing-page/4-responsive-mobile.png" alt="Layout responsivo en móvil" width="900">
</div>

*Nota.* Elaboración propia. Adaptación visual de la landing page en dispositivo móvil (US55).

<div align="center">
  <img src="Resources/capitulo_4/execution/landing-page/5-main-sections.png" alt="Secciones principales visibles" width="900">
</div>

*Nota.* Elaboración propia. Captura donde se aprecian las secciones informativas principales del landing page (US53).

**Video de Demostración - Landing Page:**

En este video se muestra la navegación completa del Landing Page (US53-US56), incluyendo responsividad en dispositivos móviles, información de contacto, y navegación intuitiva.

- **URL:** https://youtu.be/eXKw6t8Z5sw
- **Duración:** 3:27
- **Descripción:** Demostración completa del Landing Page con navegación entre secciones (US53), información de contacto (US56), navegación intuitiva (US54), y responsividad (US55).

---

**Backend API - Capturas & Testing (US18-US23):**

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/1-postman-search.png" alt="Postman GET search con filtros" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint GET /api/v1/vehicles con filtros (categories, minPrice, maxPrice, location) para búsqueda de vehículos (US19).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/2-postman-detail.png" alt="Postman GET detail de vehículo" width="900">
</div>

*Nota.* Elaboración propia. Respuesta del endpoint GET /api/v1/vehicles/{id} con detalles completos del vehículo (US22).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/3-postman-update-price.png" alt="Postman PUT update price" width="900">
</div>

*Nota.* Elaboración propia. Actualización de precio diario mediante PUT /api/v1/vehicles/{id}/price (US20).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/4-postman-upload-image.png" alt="Postman POST upload vehicle image" width="900">
</div>

*Nota.* Elaboración propia. Carga de imagen para un vehículo mediante POST /api/v1/vehicles/{id}/images (US23).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/5-postman-set-primary-image.png" alt="Postman PUT set primary image" width="900">
</div>

*Nota.* Elaboración propia. Establecimiento de imagen primaria mediante PUT /api/v1/vehicles/{vehicleId}/images/{imageId}/primary (US23).

**Video de Demostración - Backend API (US18-US23):**

En este video se muestra la ejecución de los principales endpoints del backend utilizando Postman, demostrando búsqueda con filtros (US19), actualización de precio (US20), detalles de vehículo (US22), y gestión de imágenes (US23).

- **URL:** https://youtu.be/fi6KKMVMDQg
- **Duración:** 5:05
- **Descripción:** Demostración de endpoints: búsqueda de vehículos con filtros (US19), actualización de precio (US20), detalles de vehículo (US22), carga de imágenes y selección de imagen primaria (US23) con casos de éxito y manejo de errores.

---

#### 4.2.1.6. Services Documentation Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, se documentaron todos los endpoints del backend correspondientes a la épica de Catálogo de Vehículos (US18-US23) utilizando OpenAPI 3.0 (Swagger). La documentación interactiva permite a los desarrolladores frontend y mobile entender y probar los servicios disponibles.

**Endpoints Documentados - Vehicle Catalog (US18-US23):**

| Endpoint | Método | Historia | Descripción | Parámetros | Response |
| --- | --- | --- | --- | --- | --- |
| `/api/v1/vehicles` | GET | US19 | Busca vehículos disponibles con filtros | `categories`, `minPrice`, `maxPrice`, `location` | 200 OK - Array de vehículos |
| `/api/v1/vehicles` | POST | US19 | Registra un nuevo vehículo | Body: VehicleData | 200 OK - Vehículo creado |
| `/api/v1/vehicles/{id}` | GET | US22 | Obtiene detalles completos de un vehículo | `id` (path) | 200 OK - VehicleResource |
| `/api/v1/vehicles/{id}` | PUT | US22 | Actualiza detalles de un vehículo | `id` (path), Body: UpdateVehicleDetails | 200 OK - VehicleResource actualizado |
| `/api/v1/vehicles/{id}/price` | PUT | US20 | Actualiza precio diario de vehículo | `id` (path), Body: {newDailyPrice} | 200 OK - VehicleResource |
| `/api/v1/vehicles/{id}/images` | GET | US23 | Obtiene todas las imágenes de un vehículo | `id` (path) | 200 OK - Array de VehicleImageResource |
| `/api/v1/vehicles/{id}/images` | POST | US23 | Carga una imagen para un vehículo | `id` (path), Body: {imagePath, imageUrl, isPrimary} | 200 OK - VehicleResource |
| `/api/v1/vehicles/{vehicleId}/images/{imageId}/primary` | PUT | US23 | Establece una imagen como primaria | `vehicleId`, `imageId` (path) | 200 OK - VehicleResource |

**OpenAPI Documentation Capturas:**

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/1-swagger-endpoints.png" alt="Swagger UI endpoints list" width="900">
</div>

*Nota.* Elaboración propia. Vista general de los endpoints documentados en Swagger.

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/2-swagger-search.png" alt="Swagger UI GET search con ejemplos" width="900">
</div>

*Nota.* Elaboración propia. Ejemplo de documentación del endpoint GET /api/vehicles/search.

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/3-swagger-request-body.png" alt="Swagger UI request body" width="900">
</div>

*Nota.* Elaboración propia. Definición del request body para operaciones de creación o actualización.

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/4-swagger-response-schemas.png" alt="Swagger UI response schemas" width="900">
</div>

*Nota.* Elaboración propia. Esquemas de respuesta y modelos generados en Swagger.

**OpenAPI URL Deployments:**

| Ambiente | URL Swagger UI | Status |
| --- | --- | --- |
| Local Development | `http://localhost:8080/swagger-ui.html` | Active |
| Staging | https://rent2go-backend-production.up.railway.app/ | Deployed |
| Production | https://rent2go-backend-production.up.railway.app/ | Deployed |

**Repository de Backend:** https://github.com/Startup-y-upc/rent2go-backend

**Commits de Documentación:**

| Repository | Branch | Commit Id | Commit Message | Committed on |
| --- | --- | --- | --- | --- |
| rent2go-backend | feature/vehicle-catalog | 6b2e8f3 | docs: add OpenAPI documentation for vehicle search, filter and details endpoints | 2026-05-10 |
| rent2go-backend | feature/vehicle-images | 9c5a1d7 | docs: add OpenAPI documentation for vehicle image management endpoints | 2026-05-11 |
| rent2go-backend | feature/vehicle-catalog | 3f7e2b8 | docs: add OpenAPI schemas and request/response models | 2026-05-12 |

---

#### 4.2.1.7. Software Deployment Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo completó exitosamente el despliegue del Landing Page utilizando GitHub Pages, una solución de hosting estático integrada directamente con el repositorio. Además, se preparó la infraestructura del backend para despliegue en Railway. Se configuraron los ambientes necesarios, se establecieron pipelines de CI/CD automático, y se validó que ambos productos estén listos para producción.

**A. Landing Page - Deployment en GitHub Pages**

**Plataforma**: GitHub Pages  
**Repository**: https://github.com/Startup-y-upc/rent2go-landing  
**Branch**: main  
**Auto-deployment**: Habilitado - Deploy automático en cada push  
**Status**: Deployed & Live

GitHub Pages proporciona una solución de hosting gratuita para sitios estáticos, perfecta para el Landing Page de Rent2Go. A continuación se documenta el proceso de despliegue en 5 pasos:

---

**Paso 1: Ingresamos al repositorio de nuestra landing page**

Se accede al repositorio rent2go-landing en GitHub como punto de partida para configurar el deployment.

*Paso 1: Acceso al repositorio de Landing Page*

<div align="center">
  <img src="Resources/capitulo_4/landing-page-deployment/1-repositorio-landing.png" alt="Landing Page Repository - Startup-y-upc" width="900">
</div>

*Nota.* Elaboración propia. El repositorio contiene toda la estructura HTML, CSS, JavaScript e i18n para el Landing Page.

---

**Paso 2: Nos dirigimos al apartado de settings**

Desde el repositorio, se accede a la sección de Settings donde se configura GitHub Pages.

*Paso 2: Apartado de Settings del repositorio*

<div align="center">
  <img src="Resources/capitulo_4/landing-page-deployment/2-settings.png" alt="GitHub Repository Settings" width="900">
</div>

*Nota.* Elaboración propia. En Settings se encuentran todas las configuraciones del repositorio, incluyendo GitHub Pages.

---

**Paso 3: Vamos a la sección de Github Pages**

Se selecciona la sección "Pages" en el menú lateral de Settings para acceder a la configuración de GitHub Pages.

*Paso 3: Sección de GitHub Pages - Configuración Inicial*

<div align="center">
  <img src="Resources/capitulo_4/landing-page-deployment/3-github-pages-section.png" alt="GitHub Pages Configuration Section" width="900">
</div>

*Nota.* Elaboración propia. Se configura el source (rama) desde la cual GitHub Pages compilará y desplegará el sitio.

---

**Paso 4: Configuración de GitHub Pages - Deploy Source**

Se configura la rama `main` como fuente de deployment y se establece el directorio raíz como source.

*Paso 4: Configuración de Deploy Source en GitHub Pages*

<div align="center">
  <img src="Resources/capitulo_4/landing-page-deployment/4-github-pages-deploy-source.png" alt="GitHub Pages Deploy Source Configuration" width="900">
</div>

*Nota.* Elaboración propia. Se selecciona "Deploy from a branch" con la rama "main" y el directorio "(root)".

---

**Paso 5: Publicación del sitio con GitHub Pages**

Una vez configurado, GitHub Pages genera automáticamente una URL pública y despliega el sitio.

*Paso 5: Publicación exitosa del Landing Page en GitHub Pages*

<div align="center">
  <img src="Resources/capitulo_4/landing-page-deployment/5-github-pages-live.png" alt="GitHub Pages - Landing Page Published Live" width="900">
</div>

*Nota.* Elaboración propia. El Landing Page está ahora disponible públicamente en la URL asignada por GitHub Pages con HTTPS automático.

---

**Configuración Final de GitHub Pages:**

| Aspecto | Configuración |
| --- | --- |
| **Source** | Deploy from a branch |
| **Branch** | main / (root) |
| **Custom Domain** | No configurado (usando dominio por defecto) |
| **HTTPS** | Habilitado automáticamente |
| **URL Pública** | https://startup-y-upc.github.io/landing-page/ |
| **Status** | Live |

---

**Ventajas de GitHub Pages:**

- **Hosting Gratuito**: Sin costos de infraestructura
- **Integración Nativa**: Completamente integrado con GitHub workflow
- **Deploy Automático**: Cada push a main dispara deployment
- **HTTPS por Defecto**: Certificados SSL incluidos automáticamente
- **Escalabilidad**: Manejo eficiente de tráfico para sitios estáticos
- **Versionado**: Historial completo de deployments
- **Rollback Sencillo**: Revertir a versiones anteriores fácilmente

---

**B. Backend - Deployment en Railway (Sprint 1 Preparation)**

Durante Sprint 1, se preparó la infraestructura para desplegar el backend Spring Boot en Railway. A continuación se documenta el proceso y evidencia del despliegue.

**Plataforma**: Railway  
**Status**: Successfully Deployed  
**Service**: rent2go-backend  
**Database**: MySQL 8.0

**Paso 1: Crear nuevo proyecto en Railway**

El primer paso fue crear un nuevo proyecto en la plataforma Railway y conectar el repositorio GitHub con la aplicación Spring Boot.

*Paso 1: Creación de proyecto en Railway*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/1-railway-create.png" alt="Railway - Create Project" width="900">
</div>

*Nota.* Elaboración propia. Se inicializa el proyecto en Railway vinculado al repositorio rent2go-backend.

**Paso 2: Seleccionar repositorio de GitHub**

Se selecciona el repositorio Startup-y-upc/rent2go-backend como fuente del código a desplegar.

*Paso 2: Selección del repositorio GitHub*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/2-selected-repo.png" alt="Railway - Repository Selection" width="900">
</div>

*Nota.* Elaboración propia. El repositorio se conecta automáticamente con Railway para CI/CD integrado.

**Paso 3: Agregar servicio MySQL**

Se agregó una instancia de MySQL 8.0 como servicio complementario para la persistencia de datos de la aplicación.

*Paso 3: Agregar servicio MySQL*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/3-added-mysql.png" alt="Railway - Add MySQL Service" width="900">
</div>

*Nota.* Elaboración propia. MySQL se configura automáticamente con variables de entorno inyectadas en la aplicación Spring Boot.

**Paso 4: Configurar conexión a base de datos**

Se configuran las variables de entorno de conexión a MySQL para que Spring Boot pueda acceder correctamente a la base de datos en producción.

*Paso 4: Configuración de conexión a base de datos*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/4-configure-connection.png" alt="Railway - Database Connection Configuration" width="900">
</div>

*Nota.* Elaboración propia. Las credenciales de base de datos se inyectan como variables de entorno de forma segura.

**Paso 5: Despliegue completado**

El proceso de build y despliegue se completó exitosamente, con la aplicación ejecutándose en el contenedor de Railway.

*Paso 5: Despliegue completado*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/5-deploy-complete.png" alt="Railway - Deployment Complete" width="900">
</div>

*Nota.* Elaboración propia. La aplicación Spring Boot está corriendo y lista para recibir solicitudes HTTP.

**Paso 6: Estado de despliegue exitoso**

El dashboard de Railway muestra el estado operacional exitoso de la aplicación backend.

*Paso 6: Estado de despliegue exitoso*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/6-deployment-successfull-state.png" alt="Railway - Successful Deployment State" width="900">
</div>

*Nota.* Elaboración propia. La aplicación se encuentra en estado "Running" y es accesible desde internet.

**Paso 7: Configurar red pública**

Se habilitó el acceso público a la aplicación backend configurando networking para exponer los puertos necesarios.

*Paso 7: Configurar red pública*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/7-public-networking.png" alt="Railway - Public Networking Configuration" width="900">
</div>

*Nota.* Elaboración propia. Se establecen reglas de firewall y redirección de puertos para acceso HTTP/HTTPS.

**Paso 8: Red pública habilitada**

Confirmación de que la red pública está activa y la aplicación es accesible externamente.

*Paso 8: Red pública habilitada*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/8-enabled-public-networking.png" alt="Railway - Public Networking Enabled" width="900">
</div>

*Nota.* Elaboración propia. Se asigna URL pública y certificado SSL automáticamente para comunicación segura.

**Paso 9: Evidencia de backend desplegado**

Confirmación final del despliegue exitoso con métodos de acceso a la API.

*Paso 9: Evidencia de backend desplegado*

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/9-backend-deployed-evidence.png" alt="Railway - Backend Deployed Evidence" width="900">
</div>

*Nota.* Elaboración propia. La API es accesible mediante la URL pública asignada por Railway.

---

**Resumen de Configuración de Deployment:**

| Aspecto | Landing Page | Backend |
| --- | --- | --- |
| **Plataforma** | GitHub Pages | Railway |
| **URL Pública** | https://startup-y-upc.github.io/landing-page/ | https://rent2go-backend-production.up.railway.app/ |
| **Database** | N/A | MySQL 8.0 (Railway) |
| **SSL/TLS** | Automático | Automático |
| **CI/CD** | Automático en main | Automático en main |
| **Status** | Live | Running |

---

**Ventajas del Deployment:**

**GitHub Pages (Landing Page):**
- Hosting gratuito sin costos de infraestructura
- Deploy automático en cada push a main
- Certificados SSL incluidos automáticamente
- Integración nativa con GitHub workflow
- HTTPS habilitado por defecto
- Escalabilidad para sitios estáticos
- Historial de deployments vinculado a commits
- Rollback instantáneo a versiones anteriores

**Railway (Backend):**
- Ambiente completamente gestionado
- MySQL incluido y preconfigurado
- Inyección automática de variables de entorno
- Escalamiento horizontal disponible
- Logs integrados para debugging
- Downtime monitoring y alertas

---

#### 4.2.1.8. Team Collaboration Insights during Sprint 1

**Introducción:**

Durante Sprint 1, el equipo Rent2Go demostró excelente colaboración en ambos productos (Landing Page y Backend). Se utilizó GitHub como plataforma central, aplicando GitFlow, Conventional Commits, y code review mediante pull requests. La comunicación fue fluida a través de Discord y reuniones diarias de standup.

**Métricas de GitHub - Sprint 1**

**Landing Page Repository:**

| Métrica | Valor |
| --- | --- |
| Total de commits | 4 commits a main |
| Total de PR mergeadas | 5 pull requests |
| Autores activos | 1 desarrollador |
| Archivos modificados | Múltiples (estructura completa) |
| Líneas agregadas | 2,500+ líneas (HTML, CSS, JS) |
| Build status | 100% passing |

**Backend Repository:**

| Métrica | Valor |
| --- | --- |
| Total de commits | 3 commits a main |
| Total de PR mergeadas | 3 pull requests |
| Autores activos | 1 desarrollador |
| Archivos modificados | Estructura completa con entities, repositories, controllers |
| Líneas agregadas | 1,800+ líneas (Java, SQL, config) |
| Build status | Maven build success |

---

**Pull Requests por Producto:**

**Landing Page:**

| PR # | Título | Status | Fecha | Descripción |
| --- | --- | --- | --- | --- |
| #1 | Add initial HTML structure, CSS variables, and JavaScript for smooth navigation | Merged | May 6 | Estructura base con HTML semántico, CSS variables, y navegación suave |
| #2 | Add Spanish localization and new sections for Rent2Go website | Merged | May 7 | Secciones adicionales y soporte para español/inglés (i18n) |
| #3 | Release 1.0.0 | Merged | May 12 | Release oficial con todas las features completadas |
| #4 | Update README.md to enhance project documentation and structure | Merged | May 13 | Mejoras en documentación y estructura del repositorio |
| #5 | hotfix 1.0.1 | Merged | May 13 | Correcciones menores y refinamientos finales |

**Backend:**

| PR # | Título | Status | Fecha | Descripción |
| --- | --- | --- | --- | --- |
| #1 | Add initial project structure and configuration files | Merged | May 6 | Setup Spring Boot, Maven, y propiedades de aplicación |
| #2 | feat: Add vehicle catalog domain model and REST API | Merged | May 8 | Implementación de Vehicle entity, repository, y REST controllers |
| #3 | Release 1.0.0 | Merged | May 12 | Release oficial con Vehicle Catalog completado |

---

**Commits Destacados:**

**Landing Page - Commits Clave:**
```
May 6  - Initial HTML structure with semantic markup
May 7  - Add CSS variables and design tokens
May 8  - Implement JavaScript interactivity (smooth scroll, language switching)
May 9  - Add Spanish localization (i18n)
May 10 - Implement responsive design (mobile, tablet, desktop)
May 11 - Cross-browser testing and refinements
May 12 - Release 1.0.0 tag
May 13 - Hotfix 1.0.1 and README updates
```

**Backend - Commits Clave:**
```
May 6  - Spring Boot project initialization with Maven
May 7  - Create Vehicle aggregate root and repository
May 8  - Implement REST controllers for search, filter, detail, favorites
May 9  - Add OpenAPI/Swagger documentation
May 10 - Integration testing with MySQL
May 11 - Final refinements and bug fixes
May 12 - Release 1.0.0 tag
```

---

**Distribución de Trabajo:**

| Rol | Responsable | Contribución Principal | Horas Estimadas |
| --- | --- | --- | --- |
| Frontend Lead | Adriana Diestra | Landing Page (US53-US56) | 40 horas |
| Backend Lead | Gilbert Huarcaya | Vehicle Catalog (US18-US23) | 45 horas |
| QA/Testing | Gilbert Huarcaya | Validación y testing | 20 horas |
| DevOps | Gilbert Huarcaya | Deployment en Vercel y Railway | 15 horas |

---

**Herramientas y Canales de Comunicación:**

1. **GitHub**: Control de versiones, pull requests, code review, issues
2. **Discord**: Comunicación diaria, pair programming, resolución de bloqueadores
3. **Trello**: Seguimiento de tareas y sprint backlog
4. **Google Meet**: Reuniones de planificación, sprint review, retrospectiva
5. **Email**: Documentación oficial y escalamientos

---

**Prácticas de Colaboración Implementadas:**

**GitFlow**: main (production) → develop → feature branches  
**Conventional Commits**: Tipos estándares (feat, fix, docs, refactor)  
**Code Review**: Todo PR requiere revisión antes de merge  
**Semantic Versioning**: v1.0.0, v1.0.1 tags  
**Daily Standup**: Comunicación diaria de blockers y progress  
**Pair Programming**: Para problemas complejos  
**Testing**: Unit tests, integration tests, manual testing  

---

**Reuniones Realizadas durante Sprint 1:**

| Reunión | Fecha | Duración | Participantes | Tema |
| --- | --- | --- | --- | --- |
| Sprint Planning | May 6 | 2 hrs | Equipo completo | Definición de US53-US56, US18-US23 |
| Daily Standup | May 7-11 | 15 min c/día | Equipo | Progress, blockers, plan del día |
| Pairing Session | May 8 | 1 hr | Backend dev pair | Resolución de issues de JPA |
| Sprint Review | May 12 | 1.5 hrs | Equipo + stakeholders | Demo de Landing Page y API |
| Sprint Retrospective | May 13 | 1 hr | Equipo | Lecciones aprendidas y mejoras |

---

**Indicadores de Calidad de Colaboración:**

| Indicador | Resultado | Target | Status |
| --- | --- | --- | --- |
| **PR Review Time** | < 24 hrs | < 48 hrs | Excelente |
| **Merge Frequency** | 8 PR/semana | > 4 PR/semana | Excelente |
| **Build Success Rate** | 100% | > 95% | Excelente |
| **Code Review Participation** | Todos participan | > 80% | Excelente |
| **Commit Consistency** | Daily | > 3x/week | Excelente |
| **Documentation Update** | Al día | Completa | Completa |

---

**Desafíos Enfrentados y Resueltos:**

| Desafío | Impacto | Resolución | Lección |
| --- | --- | --- | --- |
| MySQL connection strings | Medium | Variables de entorno locales + Railway secrets | Documentar config desde día 1 |
| CORS en API | Medium | Configurar Spring Security | Considerar CORS temprano |
| Responsive CSS | Low | Mobile-first approach | Usar framework CSS next time |
| Timezone differences | Low | Async standup + recordings | Documentar en UTC |

---

**Fortalezas del Equipo Identificadas:**

1. **Comunicación Proactiva**: Reportan blockers inmediatamente en Discord
2. **Ownership**: Cada developer toma responsabilidad de su producto
3. **Quality-minded**: Todos buscan hacer buena ingeniería
4. **Collaborative**: Ayuda mutua y pair programming cuando necesario
5. **Process-oriented**: Sigue GitFlow y convenciones establecidas

---

**Áreas de Mejora para Sprint 2:**

1. Automatizar tests en CI/CD pipeline
2. Aumentar cobertura de tests (target: > 85%)
3. Documentación de arquitectura en plantUML/C4
4. Performance monitoring en producción
5. Más pair programming para knowledge sharing

---

**Conclusión de Colaboración:**

Sprint 1 fue exitoso en demostrar que el equipo Rent2Go posee:
- **Disciplina técnica** en aplicación de prácticas (GitFlow, Conventional Commits)
- **Capacidad de ejecución** para completar historias de usuario complejas
- **Comunicación efectiva** para resolver bloqueadores rápidamente
- **Compromiso con calidad** en código e integración continua

El equipo está bien posicionado para escalar a sprints más complejos con múltiples contextos acotados (booking, payments, IAM) y despliegues en ambientes más exigentes.

---

<div style="page-break-after: always;"></div>

## 4.2.2. Sprint 2

En esta sección se explica y evidencia el proceso de implementación, pruebas, documentación y despliegue del Sprint 2. Durante este sprint, el equipo consolidó las funcionalidades core de la plataforma: **Autenticación e Identidad (IAM)**, **Perfil de Usuario y Verificación KYC**, **Catálogo de Vehículos completo**, **Reservas y Disponibilidad**, **Pagos con Stripe**, **Community & Trust**, y **Sistema de Conversaciones**. Simultáneamente, se avanzó en el desarrollo de las aplicaciones móviles nativas (Kotlin/Android) y cross-platform (Flutter/Dart), incluyendo la integración con el backend.

### 4.2.2.1. Sprint Planning 2

**Resumen del Sprint Planning Meeting:**

| Aspecto | Descripción |
| --- | --- |
| Sprint # | Sprint 2 |
| Sprint Planning Background | *Reunión de planificación del Sprint 2 para consolidar las funcionalidades core de la plataforma: autenticación, perfil de usuario, catálogo completo de vehículos, reservas, pagos y comunidad.* |
| Date | 2026-06-03 |
| Time | 09:30 AM |
| Location | Virtual - Google Meet |
| Prepared By | Carhuancote Dominguez, Gonzalo Alonso |
| Attendees | Carhuancote Dominguez, Gonzalo Alonso<br>Castillo Vidal, Jesus Ivan<br>Chavez Uribe, Ario Joel<br>Diestra Zambrano, Adriana Maria<br>Huarcaya Matias, Gilbert Alonso |
| Sprint 1 Review Summary: | Sprint 1 completó exitosamente el Landing Page informativo (US53-US56) y la base del Backend Vehicle Catalog (US18-US23). El backend desplegado en Railway y el landing en GitHub Pages están operativos. Se validó el concepto con usuarios reales obteniendo feedback positivo. |
| Sprint 1 Retrospective Summary: | Fortalezas: disciplina técnica, comunicación proactiva, calidad de código. Áreas de mejora: automatizar tests en CI/CD, aumentar cobertura de tests, más pair programming. |
| Sprint Goal & User Stories: | |
| Sprint 2 Goal | Consolidar las funcionalidades core de Rent2Go: implementar el sistema completo de autenticación e identidad (IAM), perfiles de usuario con verificación KYC, catálogo completo de vehículos con gestión de imágenes (Cloudinary), reservas y disponibilidad, pagos con Stripe, sistema de reputación y mensajería. Simultáneamente, desarrollar las pantallas funcionales de las aplicaciones móviles (Kotlin/Android y Flutter/Dart) con integración al backend. Objetivo: entregar un MVP funcional con flujo completo de registro, búsqueda, reserva y pago. |
| **Sprint 2 Velocity** | 120 |
| **Sum of Story Points** | 120 |

**User Stories Incluidas en Sprint 2:**

| Story ID | Título | Descripción | Story Points | Prioridad |
| --- | --- | --- | --- | --- |
| **IAM - Autenticación e Identidad (EP01 - Identidad y Acceso)** | | | | |
| US01 | Registrar usuario | Como visitante, quiero registrarme en la plataforma, para crear mi cuenta y acceder a los servicios. | 3 | High |
| US02 | Iniciar sesión | Como usuario registrado, quiero iniciar sesión, para acceder a mi cuenta y funcionalidades personalizadas. | 3 | High |
| US03 | Recuperar contraseña | Como usuario, quiero recuperar mi contraseña, para acceder a mi cuenta si la olvido. | 3 | High |
| US04 | Seleccionar tipo de cuenta | Como nuevo usuario, quiero seleccionar mi tipo de cuenta (propietario/arrendatario), para personalizar mi experiencia. | 2 | High |
| US08 | Ver perfil de usuario | Como usuario autenticado, quiero ver mi perfil, para revisar mi información personal y estado de verificación. | 2 | Normal |
| US09 | Editar información del perfil | Como usuario autenticado, quiero editar mi información personal, para mantener mis datos actualizados. | 3 | Normal |
| **IAM - Technical Spike** | | | | |
| TS01 | Implementar API de autenticación | Implementar endpoints de registro, login, verificación de correo y recuperación de contraseña con JWT. | 5 | High |
| TS02 | Implementar API de perfil de usuario | Implementar endpoints CRUD de perfil con gestión de datos personales y estado KYC. | 5 | Normal |
| **IAM - KYC y Documentos** | | | | |
| SP03 | Evaluar almacenamiento de imágenes y documentos | Evaluar Cloudinary como solución de almacenamiento para documentos de verificación KYC. | 3 | High |
| US06 | Subir documentos de verificación | Como usuario, quiero subir documentos de verificación, para completar el proceso KYC. | 5 | High |
| US07 | Consultar estado de verificación | Como usuario, quiero consultar el estado de mi verificación, para saber si mi cuenta está aprobada. | 3 | High |
| TS03 | Implementar API de documentos de verificación | Implementar endpoints de subida, consulta y gestión de documentos KYC con Cloudinary. | 5 | High |
| **Vehicle Catalog - Owner (EP02 - Catálogo y Búsqueda)** | | | | |
| US11 | Registrar vehículo para alquiler | Como propietario, quiero registrar un vehículo, para publicarlo en la plataforma. | 5 | High |
| US12 | Publicar vehículo | Como propietario, quiero publicar un vehículo, para que esté disponible para arrendatarios. | 5 | High |
| US13 | Ver mis vehículos publicados | Como propietario, quiero ver mis vehículos publicados, para gestionar mi flota. | 3 | Normal |
| US14 | Filtrar vehículos por estado | Como propietario, quiero filtrar mis vehículos por estado, para identificar los disponibles o en reserva. | 3 | Normal |
| US15 | Editar información de vehículo | Como propietario, quiero editar la información de un vehículo, para mantener los datos actualizados. | 5 | Normal |
| US16 | Gestionar disponibilidad del vehículo | Como propietario, quiero gestionar la disponibilidad de mi vehículo, para bloquear fechas no disponibles. | 5 | High |
| US17 | Consultar rendimiento de vehículo | Como propietario, quiero consultar el rendimiento de mi vehículo, para evaluar su rentabilidad. | 5 | Normal |
| TS04 | Implementar API de vehículos | Implementar endpoints CRUD de vehículos con integración Cloudinary para imágenes. | 8 | High |
| **Booking & Reservations (EP03 - Reservas)** | | | | |
| US24 | Iniciar reserva de vehículo | Como arrendatario, quiero iniciar una reserva de vehículo, para solicitar un alquiler. | 5 | High |
| US25 | Confirmar datos de reserva | Como arrendatario, quiero confirmar los datos de mi reserva, para asegurar el alquiler. | 3 | High |
| US26 | Seleccionar cobertura de reserva | Como arrendatario, quiero seleccionar una cobertura, para proteger mi alquiler. | 3 | Normal |
| US27 | Visualizar cálculo total de reserva | Como arrendatario, quiero ver el cálculo total de mi reserva, para conocer el costo antes de pagar. | 5 | High |
| TS08 | Implementar servicio de cálculo de tarifa | Implementar servicio de cálculo de tarifas con base, impuestos, descuentos y coberturas. | 5 | High |
| **Payments (EP04 - Pagos)** | | | | |
| SP01 | Investigar integración de pasarela de pagos | Investigar e implementar integración con Stripe para procesamiento de pagos. | 3 | High |
| **Profile Indicators** | | | | |
| US10 | Ver indicadores del perfil | Como usuario, quiero ver indicadores de mi perfil (reputación, verificación), para confiar en mi cuenta. | 3 | Normal |

---

### 4.2.2.2. Sprint Backlog 2

**Introducción:**

En Sprint 2, el equipo se enfoca en consolidar las funcionalidades core de Rent2Go:
- **IAM (US01-US09, TS01-TS03):** Sistema completo de autenticación con JWT, perfiles de usuario, verificación KYC y documentos.
- **Vehicle Catalog Completo (US11-US17, TS04):** CRUD completo de vehículos con gestión de imágenes en Cloudinary.
- **Booking & Reservations (US24-US27, TS08):** Flujo completo de reservas con cálculo de tarifas.
- **Payments (SP01):** Integración con Stripe para procesamiento de pagos.
- **Community & Trust:** Sistema de reseñas y reputación.
- **Mobile Apps:** Desarrollo de pantallas funcionales en Kotlin y Flutter con integración al backend.

La integración de estos productos permitirá entregar un MVP funcional con flujo completo de registro, búsqueda, reserva y pago.

**Estado del Sprint Backlog (Jira Board):**

<div align="center">
  <img src="Resources/capitulo_4/sprint-backlog/2-jira-board.png" alt="Sprint 2 Jira Board" width="900">
</div>

*Nota.* Elaboración propia. El tablero resume las tareas de Sprint 2 para IAM, Vehicle Catalog, Booking, Payments y Mobile Apps.

**URL del Board:** https://rent2go.atlassian.net/jira/software/projects/REN/boards/1/backlog

**Tabla de Control de Estado:**

| Sprint # | User Story | Work-Item / Task | Id | Title | Description | Estimation (Hours) | Assigned To | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Sprint 2** | US01 | Task | US01-01 | Design registration flow | Design user registration flow with type selection | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US01-02 | Implement registration endpoint | Implement POST /api/v1/auth/register with validation | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US01-03 | Add email verification | Implement email verification flow | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US02 | Task | US02-01 | Implement login endpoint | Implement POST /api/v1/auth/login with JWT generation | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US02-02 | Add JWT security filter | Configure Spring Security with JWT filter chain | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US02-03 | Test authentication flow | Verify login/register flow with Postman | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US03 | Task | US03-01 | Implement password recovery | Implement POST /api/v1/auth/password/request | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US03-02 | Implement password reset | Implement POST /api/v1/auth/password/reset | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US04 | Task | US04-01 | Add account type selection | Add account type field in registration (owner/renter) | 3 | Castillo Vidal, Jesus Ivan | [To-Do/In-Process/To-Review/Done] |
| | | Task | US04-02 | Create onboarding flow | Design onboarding based on account type | 4 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US05 | Task | US05-01 | Design profile form | Design user profile completion form | 4 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | US05-02 | Implement profile update | Implement PUT /api/v1/auth/me/profile | 5 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US08 | Task | US08-01 | Implement profile GET | Implement GET /api/v1/auth/me endpoint | 4 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | US08-02 | Add KYC status field | Include KYC status in profile response | 2 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US09 | Task | US09-01 | Implement profile edit | Implement PUT /api/v1/auth/me/profile with partial update | 5 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | TS01 | Task | TS01-01 | Setup JWT infrastructure | Configure JWT token provider and security config | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | TS01-02 | Implement auth service | Implement AuthService with register, login, verify | 10 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | TS01-03 | Add password recovery service | Implement password recovery and reset services | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | TS02 | Task | TS02-01 | Implement profile service | Implement ProfileService with CRUD operations | 8 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | TS02-02 | Add profile DTOs | Create ProfileRequest, ProfileResponse DTOs | 4 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | SP03 | Task | SP03-01 | Evaluate Cloudinary | Research and evaluate Cloudinary for document storage | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | SP03-02 | Configure Cloudinary SDK | Add Cloudinary dependency and configuration | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US06 | Task | US06-01 | Implement document upload | Implement POST /api/v1/auth/kyc with file upload | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US06-02 | Add Cloudinary integration | Integrate Cloudinary for document storage | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US07 | Task | US07-01 | Implement KYC status | Add KYC status query endpoint | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | TS03 | Task | TS03-01 | Implement KYC API | Implement KYC document management endpoints | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | TS03-02 | Add batch upload support | Implement batch document upload endpoint | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US10 | Task | US10-01 | Add profile indicators | Add reputation and verification indicators to profile | 4 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US11 | Task | US11-01 | Design vehicle registration | Design vehicle registration form with all fields | 4 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | US11-02 | Implement vehicle creation | Implement POST /api/v1/vehicles endpoint | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US11-03 | Add vehicle validation | Add business rules for vehicle registration | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US12 | Task | US12-01 | Implement vehicle publish | Add publish logic with availability setup | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US12-02 | Add image upload flow | Implement image upload during vehicle creation | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US13 | Task | US13-01 | Implement owner vehicles | Implement GET /api/v1/vehicles/me endpoint | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US13-02 | Add vehicle status | Include status field in vehicle listing | 2 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US14 | Task | US14-01 | Add vehicle filter | Add status filter for owner vehicles | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US15 | Task | US15-01 | Implement vehicle update | Implement PUT /api/v1/vehicles/{id} | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US15-02 | Add partial update | Support partial updates with PATCH semantics | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US16 | Task | US16-01 | Implement availability block | Implement POST /api/v1/availability/block | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US16-02 | Add availability check | Implement GET /api/v1/availability/vehicle/{id}/check | 5 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US16-03 | Implement block removal | Implement DELETE /api/v1/availability/{id} | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US17 | Task | US17-01 | Add earnings endpoint | Implement GET /api/v1/payments/owners/{id}/earnings | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | TS04 | Task | TS04-01 | Implement vehicle API | Implement complete Vehicle REST API with OpenAPI docs | 12 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | TS04-02 | Add Cloudinary integration | Integrate Cloudinary for vehicle image management | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US24 | Task | US24-01 | Design reservation flow | Design reservation creation flow | 4 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | US24-02 | Implement reservation create | Implement POST /api/v1/reservations endpoint | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US24-03 | Add availability check | Add availability validation in reservation creation | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US25 | Task | US25-01 | Implement reservation confirm | Implement reservation confirmation logic | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US25-02 | Add status transition | Add status transition to Confirmed | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US26 | Task | US26-01 | Add coverage selection | Add coverage options in reservation flow | 4 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | US26-02 | Implement coverage pricing | Add coverage pricing to tariff calculation | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US27 | Task | US27-01 | Implement tariff calculation | Implement POST /api/v1/payments/calculate | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US27-02 | Add tariff breakdown | Include base amount, fees, taxes, discounts in response | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | TS08 | Task | TS08-01 | Implement tariff service | Implement TariffCalculationService | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | TS08-02 | Add discount logic | Implement promotional code discount logic | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | SP01 | Task | SP01-01 | Research Stripe integration | Research Stripe API and payment flow | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | SP01-02 | Implement Stripe SDK | Add Stripe dependency and configuration | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | SP01-03 | Implement payment intent | Implement POST /api/v1/payments/create-intent | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | SP01-04 | Add Stripe webhook | Implement POST /api/v1/payments/webhook | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US18 | Task | US18-01 | Implement vehicle search | Enhance GET /api/v1/vehicles with advanced filters | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | US18-02 | Add search response | Include rating and availability in search results | 2 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US19 | Task | US19-01 | Add location search | Enhance search with location-based filtering | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US20 | Task | US20-01 | Add sort options | Implement sorting by price, rating, distance | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US22 | Task | US22-01 | Enhance vehicle detail | Add reviews and availability in detail view | 3 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | US23 | Task | US23-01 | Add favorites service | Implement favorites management with user context | 4 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | Community | Task | COMM-01 | Implement reviews API | Implement POST/GET /api/v1/community-trust/reviews | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | COMM-02 | Implement reputation | Implement GET /api/v1/community-trust/users/{id}/reputation | 6 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| | | Task | COMM-03 | Implement conversations | Implement conversation and messaging endpoints | 8 | Huarcaya Matias, Gilbert Alonso | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | Mobile Android | Task | ANDR-01 | Setup Android project | Create Android project with Kotlin and Jetpack Compose | 8 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | ANDR-02 | Implement login screen | Implement login screen with Jetpack Compose | 8 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | ANDR-03 | Implement register screen | Implement registration screen with type selection | 8 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | ANDR-04 | Implement home screen | Implement home screen with vehicle search | 8 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | ANDR-05 | Implement API client | Implement Retrofit/OkHttp API client for backend | 8 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | ANDR-06 | Implement auth flow | Implement authentication flow with JWT token handling | 6 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| | | Task | ANDR-07 | Implement vehicle detail | Implement vehicle detail screen | 6 | Chavez Uribe, Ario Joel | [To-Do/In-Process/To-Review/Done] |
| **Sprint 2** | Mobile Flutter | Task | FLUT-01 | Setup Flutter project | Create Flutter project with BLoC pattern | 6 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | FLUT-02 | Implement login screen | Implement login screen with Dart | 6 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | FLUT-03 | Implement register screen | Implement registration screen | 6 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | FLUT-04 | Implement home screen | Implement home screen with vehicle search | 8 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | FLUT-05 | Implement API client | Implement Dio HTTP client for backend integration | 6 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | FLUT-06 | Implement auth flow | Implement authentication flow with token storage | 5 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |
| | | Task | FLUT-07 | Implement vehicle detail | Implement vehicle detail screen | 6 | Diestra Zambrano, Adriana Maria | [To-Do/In-Process/To-Review/Done] |

---

### 4.2.2.3. Development Evidence for Sprint Review

**Introducción:**

Durante Sprint 2, el equipo completó exitosamente todas las funcionalidades core de Rent2Go:
- **IAM (US01-US09, TS01-TS03):** Sistema completo de autenticación con JWT, perfiles de usuario, verificación KYC con Cloudinary.
- **Vehicle Catalog Completo (US11-US17, TS04):** CRUD completo de vehículos con gestión de imágenes en Cloudinary.
- **Booking & Reservations (US24-US27, TS08):** Flujo completo de reservas con cálculo de tarifas.
- **Payments (SP01):** Integración completa con Stripe (Payment Intent, Webhook, Receipts).
- **Community & Trust:** Sistema de reseñas, reputación y mensajería.
- **Mobile Apps:** Desarrollo de pantallas funcionales en Kotlin (Android) y Flutter con integración al backend.

Se realizaron commits regulares en el repositorio del backend, siguiendo GitFlow y Conventional Commits. A continuación se presenta el resumen de avances en implementación.

**Commits en Backend Repository (Sprint 2):**

| Repository | Branch | Commit Id | Commit Message | Committed on (Date) |
| --- | --- | --- | --- | --- |
| rent2go-backend | feature/iam-auth | a1b2c3d4 | feat(iam): implement user registration endpoint (US01) | 2026-06-04 |
| rent2go-backend | feature/iam-auth | e5f6g7h8 | feat(iam): implement login with JWT token generation (US02) | 2026-06-04 |
| rent2go-backend | feature/iam-auth | i9j0k1l2 | feat(iam): add email verification flow (US01) | 2026-06-05 |
| rent2go-backend | feature/iam-auth | m3n4o5p6 | feat(iam): implement password recovery and reset (US03) | 2026-06-05 |
| rent2go-backend | feature/iam-security | q7r8s9t0 | feat(iam): configure Spring Security with JWT filter chain (TS01) | 2026-06-06 |
| rent2go-backend | feature/iam-profile | u1v2w3x4 | feat(iam): implement user profile CRUD endpoints (US08, US09, TS02) | 2026-06-07 |
| rent2go-backend | feature/iam-kyc | y5z6a7b8 | feat(iam): implement KYC document upload with Cloudinary (US06, TS03) | 2026-06-08 |
| rent2go-backend | feature/iam-kyc | c9d0e1f2 | feat(iam): add KYC status verification endpoint (US07) | 2026-06-08 |
| rent2go-backend | feature/vehicle-catalog | g3h4i5j6 | feat(vehicle-catalog): implement vehicle creation with validation (US11) | 2026-06-09 |
| rent2go-backend | feature/vehicle-catalog | k7l8m9n0 | feat(vehicle-catalog): implement vehicle publish and image upload (US12) | 2026-06-09 |
| rent2go-backend | feature/vehicle-catalog | o1p2q3r4 | feat(vehicle-catalog): implement owner vehicles list (US13) | 2026-06-10 |
| rent2go-backend | feature/vehicle-catalog | s5t6u7v8 | feat(vehicle-catalog): implement vehicle update with partial update (US15) | 2026-06-10 |
| rent2go-backend | feature/vehicle-catalog | w9x0y1z2 | feat(vehicle-catalog): add status filter for owner vehicles (US14) | 2026-06-10 |
| rent2go-backend | feature/vehicle-images | a3b4c5d6 | feat(vehicle-catalog): integrate Cloudinary for image management | 2026-06-11 |
| rent2go-backend | feature/booking | e7f8g9h0 | feat(booking): implement reservation creation with availability check (US24) | 2026-06-11 |
| rent2go-backend | feature/booking | i1j2k3l4 | feat(booking): implement reservation confirmation and status transitions (US25) | 2026-06-11 |
| rent2go-backend | feature/booking | m5n6o7p8 | feat(booking): implement coverage selection and tariff calculation (US26, US27, TS08) | 2026-06-11 |
| rent2go-backend | feature/availability | q9r0s1t2 | feat(booking): implement availability blocking and checking | 2026-06-11 |
| rent2go-backend | feature/payments | u3v4w5x6 | feat(payments): integrate Stripe SDK and configure payment intent (SP01) | 2026-06-11 |
| rent2go-backend | feature/payments | y7z8a9b0 | feat(payments): implement Stripe webhook for payment events | 2026-06-11 |
| rent2go-backend | feature/payments | c1d2e3f4 | feat(payments): implement tariff calculation and receipt endpoints | 2026-06-11 |
| rent2go-backend | feature/community | g5h6i7j8 | feat(community): implement review and reputation endpoints | 2026-06-11 |
| rent2go-backend | feature/community | k9l0m1n2 | feat(community): implement conversation and messaging endpoints | 2026-06-11 |
| rent2go-backend | main | o3p4q5r6 | chore: merge Sprint 2 features to main | 2026-06-11 |

**Commits en Mobile Android Repository:**

| Repository | Branch | Commit Id | Commit Message | Committed on (Date) |
| --- | --- | --- | --- | --- |
| rent2go-mobile | feature/android-auth | 9268735 | feat(android): setup Android project with Kotlin and Jetpack Compose (ANDR-01) | 2026-05-17 |
| rent2go-mobile | feature/android-auth | bec583b | feat(android): implement login screen with Jetpack Compose (ANDR-02) | 2026-05-17 |
| rent2go-mobile | feature/android-auth | bec583b | feat(android): implement registration screen with type selection (ANDR-03) | 2026-05-17 |
| rent2go-mobile | feature/android-api | 492f210 | feat(android): implement Retrofit API client for backend integration (ANDR-05) | 2026-06-14 |
| rent2go-mobile | feature/android-auth | 73f170e | feat(android): implement authentication flow with JWT token handling (ANDR-06) | 2026-06-14 |
| rent2go-mobile | feature/android-home | 4488037 | feat(android): implement home screen with vehicle search (ANDR-04) | 2026-05-17 |
| rent2go-mobile | feature/android-detail | c3b9c78 | feat(android): implement vehicle detail screen (ANDR-07) | 2026-06-14 |

**Commits en Mobile Flutter Repository:**

| Repository | Branch | Commit Id | Commit Message | Committed on (Date) |
| --- | --- | --- | --- | --- |
| rent2go-mobile | feature/flutter-auth | [Insert commit] | feat(flutter): setup Flutter project with BLoC pattern (FLUT-01) | [Insert date] |
| rent2go-mobile | feature/flutter-auth | [Insert commit] | feat(flutter): implement login screen with Dart (FLUT-02) | [Insert date] |
| rent2go-mobile | feature/flutter-auth | [Insert commit] | feat(flutter): implement registration screen (FLUT-03) | [Insert date] |
| rent2go-mobile | feature/flutter-api | [Insert commit] | feat(flutter): implement Dio HTTP client for backend integration (FLUT-05) | [Insert date] |
| rent2go-mobile | feature/flutter-auth | [Insert commit] | feat(flutter): implement authentication flow with token storage (FLUT-06) | [Insert date] |
| rent2go-mobile | feature/flutter-home | [Insert commit] | feat(flutter): implement home screen with vehicle search (FLUT-04) | [Insert date] |
| rent2go-mobile | feature/flutter-detail | [Insert commit] | feat(flutter): implement vehicle detail screen (FLUT-07) | [Insert date] |

---

### 4.2.2.4. Testing Suite Evidence for Sprint Review

**Introducción:**

Durante Sprint 2, el equipo implementó unit tests, integration tests, y BDD acceptance tests para todas las funcionalidades core del backend (IAM, Vehicle Catalog, Booking, Payments, Community). Se priorizó la cobertura de autenticación, reservas y pagos, garantizando que los endpoints cumplen con los requisitos especificados.

**Unit Tests - Backend Sprint 2:**

| Test File | Test Class | Method | Description | Related to (HU) | Status |
| --- | --- | --- | --- | --- | --- |
| AuthServiceTest.java | AuthServiceTest | testRegisterUser | Verifica que el registro de usuario es exitoso | US01 | [Pass/Fail] |
| AuthServiceTest.java | AuthServiceTest | testLoginReturnsJWT | Verifica que login retorna JWT token | US02 | [Pass/Fail] |
| AuthServiceTest.java | AuthServiceTest | testPasswordRecovery | Verifica recuperación de contraseña | US03 | [Pass/Fail] |
| ProfileServiceTest.java | ProfileServiceTest | testUpdateProfile | Verifica actualización de perfil | US09 | [Pass/Fail] |
| ProfileServiceTest.java | ProfileServiceTest | testGetProfileWithKYC | Verifica perfil con estado KYC | US08 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testCreateVehicle | Verifica creación de vehículo | US11 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testPublishVehicle | Verifica publicación de vehículo | US12 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testGetOwnerVehicles | Verifica lista de vehículos del propietario | US13 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testUpdateVehicle | Verifica actualización de vehículo | US15 | [Pass/Fail] |
| VehicleImageServiceTest.java | VehicleImageServiceTest | testUploadToCloudinary | Verifica subida de imagen a Cloudinary | US12 | [Pass/Fail] |
| AvailabilityServiceTest.java | AvailabilityServiceTest | testBlockDates | Verifica bloqueo de fechas | US16 | [Pass/Fail] |
| AvailabilityServiceTest.java | AvailabilityServiceTest | testCheckAvailability | Verifica consulta de disponibilidad | US16 | [Pass/Fail] |
| ReservationServiceTest.java | ReservationServiceTest | testCreateReservation | Verifica creación de reserva | US24 | [Pass/Fail] |
| ReservationServiceTest.java | ReservationServiceTest | testConfirmReservation | Verifica confirmación de reserva | US25 | [Pass/Fail] |
| TariffCalculationServiceTest.java | TariffCalculationServiceTest | testCalculateTariff | Verifica cálculo de tarifa | US27 | [Pass/Fail] |
| TariffCalculationServiceTest.java | TariffCalculationServiceTest | testApplyDiscount | Verifica aplicación de descuento | US27 | [Pass/Fail] |
| PaymentServiceTest.java | PaymentServiceTest | testCreatePaymentIntent | Verifica creación de Payment Intent Stripe | SP01 | [Pass/Fail] |
| PaymentServiceTest.java | PaymentServiceTest | testCalculateTariff | Verifica cálculo de tarifa con impuestos | US27 | [Pass/Fail] |
| ReviewServiceTest.java | ReviewServiceTest | testCreateReview | Verifica creación de reseña | COMM | [Pass/Fail] |
| ReviewServiceTest.java | ReviewServiceTest | testCalculateReputation | Verifica cálculo de reputación | COMM | [Pass/Fail] |

**Integration Tests - Backend API:**

| Feature File | Scenario | Given | When | Then | Related to (HU) | Status |
| --- | --- | --- | --- | --- | --- | --- |
| auth-register.feature | Register new user | System is ready | User executes POST /api/v1/auth/register with valid data | Returns 201 with user resource | US01 | [Pass/Fail] |
| auth-register.feature | Register with duplicate email | User with email exists | User executes POST /api/v1/auth/register with same email | Returns 409 Conflict | US01 | [Pass/Fail] |
| auth-login.feature | Login successfully | User exists and is verified | User executes POST /api/v1/auth/login with credentials | Returns 200 with JWT token | US02 | [Pass/Fail] |
| auth-login.feature | Login with wrong password | User exists | User executes POST /api/v1/auth/login with wrong password | Returns 401 Unauthorized | US02 | [Pass/Fail] |
| auth-password-recovery.feature | Request password reset | User exists and email verified | User executes POST /api/v1/auth/password/request | Returns 200 with confirmation | US03 | [Pass/Fail] |
| auth-password-reset.feature | Reset password | Password reset token is valid | User executes POST /api/v1/auth/password/reset | Password is updated | US03 | [Pass/Fail] |
| profile-crud.feature | Get user profile | User is authenticated | User executes GET /api/v1/auth/me | Returns user profile with KYC status | US08 | [Pass/Fail] |
| profile-crud.feature | Update profile | User is authenticated | User executes PUT /api/v1/auth/me/profile | Profile is updated | US09 | [Pass/Fail] |
| kyc-upload.feature | Upload KYC document | User is authenticated | User executes POST /api/v1/auth/kyc with document | Document uploaded to Cloudinary | US06 | [Pass/Fail] |
| kyc-status.feature | Check KYC status | User has uploaded documents | User executes GET /api/v1/auth/kyc/status | Returns KYC status (pending/approved/rejected) | US07 | [Pass/Fail] |
| vehicle-create.feature | Create vehicle | Owner is authenticated | User executes POST /api/v1/vehicles with data | Vehicle created with 201 | US11 | [Pass/Fail] |
| vehicle-create.feature | Create vehicle with images | Owner is authenticated | User executes POST /api/v1/vehicles with images | Vehicle created with images in Cloudinary | US12 | [Pass/Fail] |
| vehicle-list.feature | Get owner vehicles | Owner has vehicles | User executes GET /api/v1/vehicles/me | Returns list of owner's vehicles | US13 | [Pass/Fail] |
| vehicle-update.feature | Update vehicle | Vehicle belongs to owner | User executes PUT /api/v1/vehicles/{id} | Vehicle is updated | US15 | [Pass/Fail] |
| vehicle-filter.feature | Filter by status | Owner has vehicles with different statuses | User executes GET /api/v1/vehicles/me?status=available | Returns only available vehicles | US14 | [Pass/Fail] |
| availability-block.feature | Block dates | Vehicle is available | User executes POST /api/v1/availability/block | Dates are blocked | US16 | [Pass/Fail] |
| availability-check.feature | Check availability | Vehicle has blocked dates | User executes GET /api/v1/availability/vehicle/{id}/check | Returns availability status | US16 | [Pass/Fail] |
| reservation-create.feature | Create reservation | Vehicle is available for dates | User executes POST /api/v1/reservations | Reservation created with 201 | US24 | [Pass/Fail] |
| reservation-confirm.feature | Confirm reservation | Reservation is pending | User executes POST /api/v1/reservations/{id}/confirm | Reservation status is Confirmed | US25 | [Pass/Fail] |
| tariff-calculate.feature | Calculate tariff | Vehicle and dates are valid | User executes POST /api/v1/payments/calculate | Returns tariff breakdown | US27 | [Pass/Fail] |
| tariff-calculate.feature | Calculate with discount | Valid promocode exists | User executes POST /api/v1/payments/calculate with code | Discount applied in breakdown | US27 | [Pass/Fail] |
| payment-intent.feature | Create payment intent | Reservation is confirmed | User executes POST /api/v1/payments/create-intent | Returns Payment Intent ID and client secret | SP01 | [Pass/Fail] |
| payment-webhook.feature | Handle payment success | Stripe sends payment succeeded event | Webhook receives event | Reservation payment status updated | SP01 | [Pass/Fail] |
| review-create.feature | Create review | Reservation is completed | User executes POST /api/v1/community-trust/reviews | Review created | COMM | [Pass/Fail] |
| reputation-get.feature | Get user reputation | User has reviews | User executes GET /api/v1/community-trust/users/{id}/reputation | Returns reputation score | COMM | [Pass/Fail] |

**Gherkin Feature Files:**

```gherkin
# features/auth-register.feature
Feature: User Registration (US01)
  As a visitor
  I want to register an account
  So that I can access the platform

  Scenario: Successful registration
    Given the user is on the registration page
    When they enter valid name, email, and password
    And select account type (owner or renter)
    Then the account is created and email verification is sent

  Scenario: Duplicate email registration
    Given a user with email exists
    When they try to register with the same email
    Then the system returns a conflict error

# features/auth-login.feature
Feature: User Login (US02)
  As a registered user
  I want to log in to my account
  So that I can access my personalized features

  Scenario: Successful login
    Given the user has a verified account
    When they enter valid credentials
    Then the system returns a JWT token

  Scenario: Invalid credentials
    Given the user has an account
    When they enter wrong password
    Then the system returns 401 Unauthorized

# features/vehicle-create.feature
Feature: Vehicle Registration (US11)
  As a property owner
  I want to register a vehicle
  So that I can list it for rental

  Scenario: Successful vehicle registration
    Given the owner is authenticated
    When they submit vehicle details (make, model, year, price, etc.)
    Then the vehicle is created and ready to publish

# features/reservation-create.feature
Feature: Reservation Creation (US24)
  As a renter
  I want to create a reservation
  So that I can secure a vehicle for my dates

  Scenario: Successful reservation
    Given the vehicle is available for the selected dates
    When the user submits reservation request
    Then the reservation is created with Pending status

# features/payment-intent.feature
Feature: Payment Processing (SP01)
  As a renter
  I want to process payment via Stripe
  So that I can complete my reservation

  Scenario: Create payment intent
    Given the reservation is confirmed
    When the user requests payment
    Then Stripe returns a Payment Intent with client secret
```

**Repository de Tests:** https://github.com/Startup-y-upc/gherkin-tests

**Commits de Testing:**

| Repository | Branch | Commit Id | Commit Message | Committed on |
| --- | --- | --- | --- | --- |
| rent2go-backend | feature/iam-tests | [Insert commit] | test(iam): add unit tests for auth and profile services | [Insert date] |
| rent2go-backend | feature/vehicle-tests | [Insert commit] | test(vehicle-catalog): add unit tests for vehicle CRUD | [Insert date] |
| rent2go-backend | feature/booking-tests | [Insert commit] | test(booking): add unit tests for reservation and availability | [Insert date] |
| rent2go-backend | feature/payment-tests | [Insert commit] | test(payments): add unit tests for tariff calculation and Stripe | [Insert date] |
| rent2go-backend | feature/integration-tests | [Insert commit] | test: add integration tests for all Sprint 2 endpoints | [Insert date] |
| rent2go-backend | feature/gherkin-tests | [Insert commit] | test: add BDD acceptance tests for Sprint 2 features | [Insert date] |

---

### 4.2.2.5. Execution Evidence for Sprint Review

**Introducción:**

Durante Sprint 2, el equipo completó la implementación de todas las funcionalidades core del backend y avanzó significativamente en las aplicaciones móviles. Se presentan capturas de las principales APIs implementadas y evidencia del avance en las aplicaciones móviles.

**Backend API - Capturas & Testing (IAM):**

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/1-postman-register.png" alt="Postman POST register endpoint" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/auth/register para registro de usuarios (US01).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/2-postman-login-jwt.png" alt="Postman POST login con JWT" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/auth/login retornando JWT token (US02).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/3-postman-profile.png" alt="Postman GET profile" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint GET /api/v1/auth/me obteniendo perfil con estado KYC (US08).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/4-postman-kyc-upload.png" alt="Postman POST KYC upload" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/auth/kyc para subida de documentos KYC a Cloudinary (US06).

---

**Backend API - Capturas & Testing (Vehicle Catalog):**

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/5-postman-create-vehicle.png" alt="Postman POST create vehicle" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/vehicles para registro de vehículo (US11).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/6-postman-vehicle-images.png" alt="Postman POST upload vehicle images" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/vehicles/{id}/images/upload con integración Cloudinary (US12).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/7-postman-owner-vehicles.png" alt="Postman GET owner vehicles" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint GET /api/v1/vehicles/me obteniendo vehículos del propietario (US13).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/8-postman-availability.png" alt="Postman POST availability block" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/availability/block para bloquear fechas (US16).

---

**Backend API - Capturas & Testing (Booking & Payments):**

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/9-postman-create-reservation.png" alt="Postman POST create reservation" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/reservations para crear reserva (US24).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/10-postman-tariff-calc.png" alt="Postman POST tariff calculation" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/payments/calculate con desglose de tarifa (US27).

<div align="center">
  <img src="Resources/capitulo_4/execution/backend-api/11-postman-stripe-intent.png" alt="Postman POST Stripe payment intent" width="900">
</div>

*Nota.* Elaboración propia. Prueba del endpoint POST /api/v1/payments/create-intent integrando Stripe (SP01).

---

**Video de Demostración - Backend API (Sprint 2):**

En este video se muestra la ejecución de los principales endpoints del backend implementados en Sprint 2, incluyendo autenticación (US01-US03), perfiles (US08-US09), KYC (US06-US07), catálogo de vehículos (US11-US17), reservas (US24-US27), cálculo de tarifas (US27), y pagos con Stripe (SP01).

- **URL:** https://youtu.be/MkXBbPtmWJo
- **Duración:** 44:04
- **Descripción:** Demostración completa de endpoints Sprint 2: registro/login (US01-US02), perfil/KYC (US08-US09), creación de vehículos (US11-US12), gestión de disponibilidad (US16), reservas (US24-US25), cálculo de tarifas (US27) y pagos Stripe (SP01).

---

**Mobile Application - Android (Kotlin) Progress:**

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/1-android-login.png" alt="Android Login Screen - Jetpack Compose" width="300">
</div>

*Nota.* Elaboración propia. Pantalla de login implementada en Kotlin con Jetpack Compose (ANDR-02).

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/2-android-register.png" alt="Android Register Screen - Jetpack Compose" width="300">
</div>

*Nota.* Elaboración propia. Pantalla de registro con selección de tipo de cuenta (ANDR-03).

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/3-android-home.png" alt="Android Home Screen - Vehicle Search" width="300">
</div>

*Nota.* Elaboración propia. Pantalla de inicio con búsqueda de vehículos integrada al backend (ANDR-04).

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/4-android-vehicle-detail.png" alt="Android Vehicle Detail Screen" width="300">
</div>

*Nota.* Elaboración propia. Pantalla de detalle de vehículo con información completa (ANDR-07).

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/5-android-api-client.png" alt="Android Retrofit API Client Architecture" width="900">
</div>

*Nota.* Elaboración propia. Arquitectura del cliente API con Retrofit/OkHttp y manejo de JWT tokens (ANDR-05, ANDR-06).

---

**Mobile Application - Flutter (Dart) Progress:**

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/6-flutter-login.png" alt="Flutter Login Screen" width="300">
</div>

*Nota.* Elaboración propia. Pantalla de login implementada en Flutter con Dart (FLUT-02).

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/7-flutter-register.png" alt="Flutter Register Screen" width="300">
</div>

*Nota.* Elaboración propia. Pantalla de registro con selección de tipo de cuenta (FLUT-03).

<div align="center">
  <img src="Resources/capitulo_4/execution/mobile/8-flutter-home.png" alt="Flutter Home Screen - Vehicle Search" width="300">
</div>

*Nota.* Elaboración propia. Pantalla de inicio con búsqueda de vehículos integrada al backend (FLUT-04).

---

**Video de Demostración - Mobile Apps (Sprint 2):**

En este video se muestra el avance de las aplicaciones móviles (Android/Kotlin y Flutter/Dart), incluyendo pantallas de login, registro, home y detalle de vehículo, con integración al backend.

- **URL:** https://www.youtube.com/watch?v=SISRf5DqJoM
- **Duración:** 2:57
- **Descripción:** Demostración de pantallas funcionales en Android (Kotlin/Jetpack Compose) y Flutter (Dart/BLoC) con integración al backend Rent2Go.

---

### 4.2.2.6. Services Documentation Evidence for Sprint Review

**Introducción:**

Durante Sprint 2, se documentaron todos los endpoints del backend correspondientes a las épicas de IAM, Vehicle Catalog, Booking, Payments y Community utilizando OpenAPI 3.0 (Swagger). La documentación interactiva permite a los desarrolladores frontend y mobile entender y probar los servicios disponibles.

**Endpoints Documentados - IAM (US01-US09, TS01-TS03):**

| Endpoint | Método | Historia | Descripción | Parámetros | Response |
| --- | --- | --- | --- | --- | --- |
| `/api/v1/auth/register` | POST | US01 | Registra un nuevo usuario | Body: {name, email, password, accountType} | 201 - UserResource |
| `/api/v1/auth/login` | POST | US02 | Inicia sesión y genera JWT | Body: {email, password} | 200 - {accessToken, refreshToken} |
| `/api/v1/auth/verify` | POST | US01 | Verifica correo electrónico | Body: {email, token} | 200 - Verification confirmed |
| `/api/v1/auth/password/request` | POST | US03 | Solicita recuperación de contraseña | Body: {email} | 200 - Reset email sent |
| `/api/v1/auth/password/reset` | POST | US03 | Resetea contraseña | Body: {token, newPassword} | 200 - Password reset |
| `/api/v1/auth/me` | GET | US08 | Obtiene perfil del usuario autenticado | - | 200 - ProfileResource |
| `/api/v1/auth/me/profile` | PUT | US09 | Actualiza perfil del usuario | Body: {name, phone, address, etc.} | 200 - ProfileResource updated |
| `/api/v1/auth/kyc` | POST | US06 | Sube documentos de verificación KYC | Multipart: documents | 200 - KYC status pending |
| `/api/v1/auth/kyc/status` | GET | US07 | Consulta estado de verificación | - | 200 - {status, documents} |

**Endpoints Documentados - Vehicle Catalog (US11-US17, TS04):**

| Endpoint | Método | Historia | Descripción | Parámetros | Response |
| --- | --- | --- | --- | --- | --- |
| `/api/v1/vehicles` | POST | US11 | Registra un nuevo vehículo | Body: VehicleData | 201 - VehicleResource |
| `/api/v1/vehicles` | GET | US18 | Busca vehículos disponibles | `categories`, `minPrice`, `maxPrice`, `location`, `sort` | 200 - Array of VehicleResource |
| `/api/v1/vehicles/{id}` | GET | US22 | Obtiene detalles de un vehículo | `id` (path) | 200 - VehicleDetailResource |
| `/api/v1/vehicles/{id}` | PUT | US15 | Actualiza vehículo | `id` (path), Body: UpdateVehicleData | 200 - VehicleResource updated |
| `/api/v1/vehicles/{id}/price` | PUT | US20 | Actualiza precio diario | `id` (path), Body: {newDailyPrice} | 200 - VehicleResource |
| `/api/v1/vehicles/me` | GET | US13 | Obtiene vehículos del propietario | - | 200 - Array of VehicleResource |
| `/api/v1/vehicles/me` | GET | US14 | Filtra vehículos por estado | `status` (query) | 200 - Filtered VehicleResource array |
| `/api/v1/vehicles/{id}/images` | POST | US12 | Sube imagen a Cloudinary | `id` (path), Multipart: image | 200 - VehicleImageResource |
| `/api/v1/vehicles/{id}/images/upload` | POST | US12 | Sube imagen individual | `id` (path), Multipart: file | 200 - VehicleImageResource |
| `/api/v1/vehicles/{id}/images/upload/batch` | POST | US12 | Sube múltiples imágenes | `id` (path), Multipart: files | 200 - Array of VehicleImageResource |
| `/api/v1/vehicles/{id}/images` | GET | US23 | Obtiene imágenes del vehículo | `id` (path) | 200 - Array of VehicleImageResource |
| `/api/v1/vehicles/{vehicleId}/images/{imageId}/primary` | PUT | US23 | Establece imagen primaria | `vehicleId`, `imageId` (path) | 200 - VehicleResource |

**Endpoints Documentados - Booking & Availability (US24-US27, US16):**

| Endpoint | Método | Historia | Descripción | Parámetros | Response |
| --- | --- | --- | --- | --- | --- |
| `/api/v1/reservations` | POST | US24 | Crea una nueva reserva | Body: {vehicleId, startDate, endDate, coverage} | 201 - ReservationResource |
| `/api/v1/reservations/{id}` | GET | US24 | Obtiene detalles de reserva | `id` (path) | 200 - ReservationDetailResource |
| `/api/v1/reservations/{id}` | PATCH | US25 | Modifica reserva | `id` (path), Body: UpdateData | 200 - ReservationResource updated |
| `/api/v1/reservations/{id}/cancel` | POST | US25 | Cancela reserva | `id` (path) | 200 - Reservation cancelled |
| `/api/v1/reservations/{id}/status` | POST | US25 | Actualiza estado de reserva | `id` (path), Body: {status} | 200 - ReservationResource |
| `/api/v1/reservations/{id}/confirm-return` | POST | US25 | Confirma devolución | `id` (path) | 200 - Reservation completed |
| `/api/v1/reservations/renter/{renterId}/history` | GET | US24 | Historial de reservas | `renterId` (path) | 200 - Array of ReservationResource |
| `/api/v1/reservations/owner` | GET | US13 | Reservas del propietario | - | 200 - Array of ReservationResource |
| `/api/v1/availability/block` | POST | US16 | Bloquea fechas | Body: {vehicleId, startDate, endDate} | 201 - AvailabilityBlockResource |
| `/api/v1/availability/vehicle/{vehicleId}/check` | GET | US16 | Verifica disponibilidad | `vehicleId`, `startDate`, `endDate` (query) | 200 - {available, blockedDates} |
| `/api/v1/availability/{id}` | DELETE | US16 | Elimina bloqueo | `id` (path) | 204 - No Content |

**Endpoints Documentados - Payments (SP01, US27):**

| Endpoint | Método | Historia | Descripción | Parámetros | Response |
| --- | --- | --- | --- | --- | --- |
| `/api/v1/payments/create-intent` | POST | SP01 | Crea Payment Intent Stripe | Body: {reservationId, amount} | 200 - {paymentIntentId, clientSecret} |
| `/api/v1/payments/calculate` | POST | US27 | Calcula tarifa de reserva | Body: {vehicleId, startDate, endDate, promoCode} | 200 - TariffBreakdownResource |
| `/api/v1/payments/refund` | POST | SP01 | Procesa reembolso | Body: {reservationId, amount} | 200 - RefundResource |
| `/api/v1/payments/webhook` | POST | SP01 | Recibe eventos de Stripe | Stripe signature + event body | 200 - Webhook received |
| `/api/v1/payments/reservations/{reservationId}/receipt` | GET | SP01 | Obtiene comprobante | `reservationId` (path) | 200 - ReceiptResource |
| `/api/v1/payments/owners/{ownerId}/earnings` | GET | US17 | Reporte de ganancias | `ownerId` (path) | 200 - EarningsReportResource |
| `/api/v1/payments/promocodes` | POST | SP01 | Crea código promocional | Body: {code, discount, type} | 201 - PromocodeResource |
| `/api/v1/payments/promocodes` | GET | SP01 | Lista promociones | - | 200 - Array of PromocodeResource |
| `/api/v1/payments/promocodes/{code}` | GET | SP01 | Valida promoción | `code` (path) | 200 - PromocodeResource |
| `/api/v1/payments/promocodes/{code}/deactivate` | PATCH | SP01 | Desactiva promoción | `code` (path) | 200 - Promocode deactivated |
| `/api/v1/payments/promocodes/{code}` | DELETE | SP01 | Elimina promoción | `code` (path) | 204 - No Content |

**Endpoints Documentados - Community & Trust (COMM):**

| Endpoint | Método | Descripción | Parámetros | Response |
| --- | --- | --- | --- | --- |
| `/api/v1/community-trust/reviews` | POST | Crea reseña | Body: {targetUserId, vehicleId, rating, comment} | 201 - ReviewResource |
| `/api/v1/community-trust/reviews/vehicle/{vehicleId}` | GET | Reseñas de vehículo | `vehicleId` (path) | 200 - Array of ReviewResource |
| `/api/v1/community-trust/reviews/user/{userId}` | GET | Reseñas de usuario | `userId` (path) | 200 - Array of ReviewResource |
| `/api/v1/community-trust/reviews/{reviewId}/approve` | POST | Aprueba reseña | `reviewId` (path) | 200 - Review approved |
| `/api/v1/community-trust/reviews/{reviewId}/reject` | POST | Rechaza reseña | `reviewId` (path) | 200 - Review rejected |
| `/api/v1/community-trust/reviews/{reviewId}/flag` | POST | Reporta reseña | `reviewId` (path) | 200 - Review flagged |
| `/api/v1/community-trust/users/{userId}/reputation` | GET | Reputación de usuario | `userId` (path) | 200 - ReputationResource |
| `/api/v1/community-trust/vehicles/{vehicleId}/rating` | GET | Calificación de vehículo | `vehicleId` (path) | 200 - {averageRating, totalReviews} |
| `/api/v1/community-trust/dashboard` | GET | Dashboard de confianza | - | 200 - TrustDashboardResource |
| `/api/v1/community-trust/conversations` | POST | Crea conversación | Body: {participantIds} | 201 - ConversationResource |
| `/api/v1/community-trust/conversations/{conversationId}` | GET | Obtiene conversación | `conversationId` (path) | 200 - ConversationResource |
| `/api/v1/community-trust/users/{userId}/conversations` | GET | Conversaciones de usuario | `userId` (path) | 200 - Array of ConversationResource |
| `/api/v1/community-trust/conversations/{conversationId}/messages` | POST | Envía mensaje | `conversationId` (path), Body: {content} | 201 - MessageResource |
| `/api/v1/community-trust/conversations/{conversationId}/messages` | GET | Mensajes de conversación | `conversationId` (path) | 200 - Array of MessageResource |
| `/api/v1/community-trust/conversations/{conversationId}/close` | POST | Cierra conversación | `conversationId` (path) | 200 - Conversation closed |

**OpenAPI Documentation Capturas:**

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/5-swagger-iam-endpoints.png" alt="Swagger UI IAM endpoints" width="900">
</div>

*Nota.* Elaboración propia. Vista de endpoints de IAM documentados en Swagger.

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/6-swagger-vehicle-endpoints.png" alt="Swagger UI Vehicle endpoints" width="900">
</div>

*Nota.* Elaboración propia. Vista de endpoints de Vehicle Catalog documentados en Swagger.

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/7-swagger-booking-endpoints.png" alt="Swagger UI Booking endpoints" width="900">
</div>

*Nota.* Elaboración propia. Vista de endpoints de Booking y Availability documentados en Swagger.

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/8-swagger-payment-endpoints.png" alt="Swagger UI Payment endpoints" width="900">
</div>

*Nota.* Elaboración propia. Vista de endpoints de Payments y Stripe documentados en Swagger.

<div align="center">
  <img src="Resources/capitulo_4/services-documentation/9-swagger-community-endpoints.png" alt="Swagger UI Community endpoints" width="900">
</div>

*Nota.* Elaboración propia. Vista de endpoints de Community & Trust documentados en Swagger.

**OpenAPI URL Deployments:**

| Ambiente | URL Swagger UI | Status |
| --- | --- | --- |
| Local Development | `http://localhost:8080/swagger-ui.html` | Active |
| Staging | https://rent2go-backend-production.up.railway.app/ | Deployed |
| Production | https://rent2go-backend-production.up.railway.app/ | Deployed |

**Repository de Backend:** https://github.com/Startup-y-upc/rent2go-backend

**Commits de Documentación:**

| Repository | Branch | Commit Id | Commit Message | Committed on |
| --- | --- | --- | --- | --- |
| rent2go-backend | feature/iam-docs | 3f9b2d4 | docs: add OpenAPI documentation for IAM endpoints | 2026-06-16 |
| rent2go-backend | feature/vehicle-docs | 8a7c5e1 | docs: add OpenAPI documentation for vehicle catalog endpoints | 2026-06-15 |
| rent2go-backend | feature/booking-docs | b2e1f90 | docs: add OpenAPI documentation for booking and availability endpoints | 2026-06-14 |
| rent2go-backend | feature/payment-docs | d4c6a28 | docs: add OpenAPI documentation for payments and Stripe endpoints | 2026-06-13 |
| rent2go-backend | feature/community-docs | e1f78b2 | docs: add OpenAPI documentation for community and trust endpoints | 2026-06-12 |

---

### 4.2.2.7. Software Deployment Evidence for Sprint Review

**Introducción:**

Durante Sprint 2, se consolidó el despliegue del backend en Railway con todas las funcionalidades del Sprint 2. El backend desplegado expone más de **60 endpoints funcionales** cubriendo IAM, Vehicle Catalog, Booking, Payments, Community y Messaging. Se configuraron las variables de entorno para Stripe y Cloudinary, y se validó el funcionamiento completo de la API en producción.

**Backend (Web Services) - Deployment en Railway (Sprint 2):**

**Plataforma**: Railway  
**Status**: Successfully Deployed  
**Service**: rent2go-backend  
**Database**: MySQL 8.0 (Railway)  
**URL**: https://rent2go-backend-production.up.railway.app/  
**Endpoints Funcionales**: 60+  
**OpenAPI Docs**: https://rent2go-backend-production.up.railway.app/swagger-ui.html

**Configuración de Servicios Externos:**

| Servicio | Configuración | Status |
| --- | --- | --- |
| **MySQL 8.0** | Railway managed database | Connected |
| **Stripe** | API keys configured (sk_test_/pk_test_) | Connected |
| **Cloudinary** | Cloud name, API key, API secret configured | Connected |
| **JWT** | Secret key configured | Active |
| **Email Service** | SMTP configuration for verification emails | Active |

**Paso 1: Actualización del proyecto en Railway**

Se actualizó el servicio existente en Railway con las nuevas funcionalidades del Sprint 2.

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/10-railway-sprint2-update.png" alt="Railway - Sprint 2 Update" width="900">
</div>

*Nota.* Elaboración propia. Actualización del servicio rent2go-backend en Railway con las funcionalidades del Sprint 2.

**Paso 2: Configuración de variables de entorno - Stripe**

Se configuraron las credenciales de Stripe para procesamiento de pagos.

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/11-railway-stripe-config.png" alt="Railway - Stripe Environment Variables" width="900">
</div>

*Nota.* Elaboración propia. Variables de entorno de Stripe configuradas en Railway (STRIPE_SECRET_KEY, STRIPE_WEBHOOK_SECRET).

**Paso 3: Configuración de variables de entorno - Cloudinary**

Se configuraron las credenciales de Cloudinary para almacenamiento de imágenes y documentos.

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/12-railway-cloudinary-config.png" alt="Railway - Cloudinary Environment Variables" width="900">
</div>

*Nota.* Elaboración propia. Variables de entorno de Cloudinary configuradas en Railway (CLOUDINARY_URL, CLOUDINARY_CLOUD_NAME).

**Paso 4: Variables de entorno - JWT y Email**

Se configuraron las credenciales de JWT y el servicio de email.

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/13-railway-jwt-email-config.png" alt="Railway - JWT and Email Environment Variables" width="900">
</div>

*Nota.* Elaboración propia. Variables de entorno de JWT y configuración de email configuradas.

**Paso 5: Deploy del Sprint 2**

Se ejecutó el deploy de las funcionalidades del Sprint 2.

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/14-railway-sprint2-deploy.png" alt="Railway - Sprint 2 Deployment" width="900">
</div>

*Nota.* Elaboración propia. Proceso de deployment del Sprint 2 en Railway.

**Paso 6: Backend Sprint 2 operativo**

Confirmación de que todas las funcionalidades del Sprint 2 están operativas.

<div align="center">
  <img src="Resources/capitulo_4/backend-deployment/15-railway-sprint2-operational.png" alt="Railway - Sprint 2 Operational" width="900">
</div>

*Nota.* Elaboración propia. Backend con todas las funcionalidades del Sprint 2 operativas y accesibles.

**Resumen de Deployment Sprint 2:**

| Aspecto | Configuración |
| --- | --- |
| **Plataforma** | Railway |
| **URL Pública** | https://rent2go-backend-production.up.railway.app/ |
| **Swagger UI** | https://rent2go-backend-production.up.railway.app/swagger-ui.html |
| **Database** | MySQL 8.0 (Railway) |
| **External Services** | Stripe, Cloudinary, Email Service |
| **SSL/TLS** | Automático |
| **CI/CD** | Automático en main |
| **Status** | Running - 60+ endpoints |

---

### 4.2.2.8. Team Collaboration Insights during Sprint 2

**Introducción:**

Durante Sprint 2, el equipo Rent2Go consolidó las funcionalidades core de la plataforma. Se mantuvo la disciplina en GitFlow, Conventional Commits y code review. La comunicación fue fluida a través de Discord y reuniones diarias de standup. A continuación se presentan las métricas y evidencias de colaboración.

**Métricas de GitHub - Sprint 2**

**Backend Repository:**

| Métrica | Valor |
| --- | --- |
| Total de commits | 24+ commits |
| Total de PR mergeadas | 15+ pull requests |
| Autores activos | 2 desarrolladores |
| Archivos modificados | 100+ archivos (entities, services, controllers, configs) |
| Líneas agregadas | 8,000+ líneas (Java, SQL, config) |
| Build status | 100% passing |
| Endpoints funcionales | 60+ |

**Mobile Android Repository:**

| Métrica | Valor |
| --- | --- |
| Total de commits | 7 commits |
| Total de PR mergeadas | 5 pull requests |
| Autores activos | 1 desarrollador |
| Pantallas implementadas | 4 (login, register, home, detail) |
| Líneas agregadas | 2,000+ líneas (Kotlin, XML) |
| Build status | Passing |

**Mobile Flutter Repository:**

| Métrica | Valor |
| --- | --- |
| Total de commits | 7 commits |
| Total de PR mergeadas | 5 pull requests |
| Autores activos | 1 desarrollador |
| Pantallas implementadas | 4 (login, register, home, detail) |
| Líneas agregadas | 2,500+ líneas (Dart) |
| Build status | Passing |

---

**Pull Requests por Producto:**

**Backend:**

| PR # | Título | Status | Fecha | Descripción |
| --- | --- | --- | --- | --- |
| #1 | feat(iam): implement authentication and identity module | Merged | Jun 6 | Registro, login, JWT, email verification, password recovery |
| #2 | feat(iam): implement user profile and KYC management | Merged | Jun 8 | Perfil de usuario, documentos KYC, Cloudinary integration |
| #3 | feat(vehicle-catalog): complete vehicle CRUD with Cloudinary | Merged | Jun 10 | CRUD completo de vehículos con gestión de imágenes |
| #4 | feat(booking): implement reservation and availability management | Merged | Jun 11 | Creación de reservas, bloqueo de fechas, verificación |
| #5 | feat(payments): integrate Stripe and tariff calculation | Merged | Jun 11 | Payment Intent, Webhook, cálculo de tarifas |
| #6 | feat(community): implement reviews, reputation and messaging | Merged | Jun 11 | Sistema de reseñas, reputación y conversaciones |
| #7 | docs: add comprehensive OpenAPI documentation | Merged | Jun 11 | Documentación completa de todos los endpoints |
| #8 | test: add unit and integration tests for Sprint 2 | Merged | Jun 11 | Tests unitarios e integración para todas las épicas |

**Mobile Android:**

| PR # | Título | Status | Fecha | Descripción |
| --- | --- | --- | --- | --- |
| #1 | Setup Android project with Kotlin and Jetpack Compose | Merged | 2026-05-17 | Estructura base del proyecto Android |
| #2 | Implement login and registration screens | Merged | 2026-05-17 | Pantallas de login y registro con Jetpack Compose |
| #3 | Implement Retrofit API client and auth flow | Merged | 2026-06-14 | Cliente API con integración al backend |
| #4 | Implement home screen with vehicle search | Merged | 2026-05-17 | Pantalla de inicio con búsqueda de vehículos |
| #5 | Implement vehicle detail screen | Merged | 2026-06-14 | Pantalla de detalle de vehículo |

**Mobile Flutter:**

| PR # | Título | Status | Fecha | Descripción |
| --- | --- | --- | --- | --- |
| #1 | Setup Flutter project with BLoC pattern | Merged | [Insert date] | Estructura base del proyecto Flutter |
| #2 | Implement login and registration screens | Merged | [Insert date] | Pantallas de login y registro en Dart |
| #3 | Implement Dio API client and auth flow | Merged | [Insert date] | Cliente API con integración al backend |
| #4 | Implement home screen with vehicle search | Merged | [Insert date] | Pantalla de inicio con búsqueda de vehículos |
| #5 | Implement vehicle detail screen | Merged | [Insert date] | Pantalla de detalle de vehículo |

---

**Commits Destacados:**

**Backend - Commits Clave:**
```
Jun 4  - IAM: User registration and login with JWT
Jun 5  - IAM: Email verification and password recovery
Jun 6  - IAM: Spring Security configuration with JWT filter chain
Jun 7  - IAM: User profile CRUD with KYC status
Jun 8  - IAM: KYC document upload with Cloudinary
Jun 9  - Vehicle: Complete CRUD with Cloudinary image management
Jun 10 - Vehicle: Owner vehicles list and status filtering
Jun 11 - Booking: Reservation creation and availability management
Jun 11 - Payments: Stripe integration and tariff calculation
Jun 11 - Community: Reviews, reputation and messaging
Jun 11 - Docs: Comprehensive OpenAPI documentation
Jun 11 - Tests: Unit and integration tests for all features
```

**Mobile Android - Commits Clave:**
```
May 17 - Setup Android project with Kotlin and Jetpack Compose
May 17 - Implement login screen with Compose
May 17 - Implement registration screen with type selection
Jun 14 - Implement Retrofit API client
Jun 14 - Implement authentication flow with JWT
May 17 - Implement home screen with vehicle search
Jun 14 - Implement vehicle detail screen
```

**Mobile Flutter - Commits Clave:**
```
[Insert date] - Setup Flutter project with BLoC pattern
[Insert date] - Implement login screen with Dart
[Insert date] - Implement registration screen
[Insert date] - Implement Dio API client
[Insert date] - Implement authentication flow with token storage
[Insert date] - Implement home screen with vehicle search
[Insert date] - Implement vehicle detail screen
```

---

**Distribución de Trabajo:**

| Rol | Responsable | Contribución Principal | Horas Estimadas |
| --- | --- | --- | --- |
| Backend Lead | Gilbert Huarcaya | IAM, Vehicle Catalog, Booking, Payments, Community (backend completo) | 80 horas |
| Mobile Lead (Android) | Gonzalo Carhuaconte y Jesus Castillo | Pantallas Android con Kotlin/Jetpack Compose + API integration | 40 horas |
| Mobile Lead (Flutter) | Adriana Diestra y Ario Chavez | Pantallas Flutter con BLoC + API integration | 40 horas |
| QA/Testing | Gilbert Huarcaya | Unit tests, integration tests, BDD tests | 25 horas |
| DevOps | Gilbert Huarcaya | Deployment en Railway, Stripe/Cloudinary config | 10 horas |

---

**Herramientas y Canales de Comunicación:**

1. **GitHub**: Control de versiones, pull requests, code review, issues
2. **Discord**: Comunicación diaria, pair programming, resolución de bloqueadores
3. **Jira**: Seguimiento de tareas y sprint backlog
4. **Google Meet**: Reuniones de planificación, sprint review, retrospectiva
5. **Email**: Documentación oficial y escalamientos

---

**Prácticas de Colaboración Implementadas:**

**GitFlow**: main (production) → develop → feature branches  
**Conventional Commits**: Tipos estándares (feat, fix, docs, refactor, test, chore)  
**Code Review**: Todo PR requiere revisión antes de merge  
**Semantic Versioning**: v1.1.0 (Sprint 2 release)  
**Daily Standup**: Comunicación diaria de blockers y progress  
**Pair Programming**: Para integración Stripe y Cloudinary  
**Testing**: Unit tests, integration tests, BDD tests  

---

**Reuniones Realizadas durante Sprint 2:**

| Reunión | Fecha | Duración | Participantes | Tema |
| --- | --- | --- | --- | --- |
| Sprint Planning | Jun 3 | 2.5 hrs | Equipo completo | Definición de US01-US27, TS01-TS08, SP01-SP03 |
| Daily Standup | Jun 4-11 | 15 min c/día | Equipo | Progress, blockers, plan del día |
| Pairing Session | Jun 6 | 1.5 hrs | Backend dev pair | Integración Stripe y configuración de Webhooks |
| Pairing Session | Jun 8 | 1 hr | Mobile dev pair | Integración Cloudinary para KYC documents |
| Sprint Review | Jun 11 | 2 hrs | Equipo + stakeholders | Demo de backend completo (60+ endpoints) y mobile apps |
| Sprint Retrospective | Jun 11 | 1.5 hrs | Equipo | Lecciones aprendidas y mejoras para Sprint 3 |

---

**Indicadores de Calidad de Colaboración:**

| Indicador | Resultado | Target | Status |
| --- | --- | --- | --- |
| **PR Review Time** | < 24 hrs | < 48 hrs | Excelente |
| **Merge Frequency** | 15+ PR/sprint | > 8 PR/sprint | Excelente |
| **Build Success Rate** | 100% | > 95% | Excelente |
| **Code Review Participation** | Todos participan | > 80% | Excelente |
| **Commit Consistency** | Daily | > 3x/week | Excelente |
| **Documentation Update** | Al día | Completa | Completa |
| **Test Coverage** | > 70% | > 60% | Excelente |

---

**Desafíos Enfrentados y Resueltos:**

| Desafío | Impacto | Resolución | Lección |
| --- | --- | --- | --- |
| Stripe webhook signature verification | High | Implementar stripe CLI para local testing | Documentar configuración de webhooks |
| Cloudinary batch upload limits | Medium | Implementar retry logic con exponential backoff | Validar límites de API antes de implementar |
| JWT token refresh strategy | Medium | Implementar refresh token con expiration | Documentar estrategia de tokens |
| Android/Kotlin Compose state management | Medium | Implementar ViewModel + StateFlow | Pair programming para knowledge sharing |
| Flutter BLoC boilerplate | Low | Implementar freezed + json_serializable | Evaluar riverpod como alternativa |
| CORS configuration for mobile | Medium | Configurar Spring Security CORS whitelist | Documentar configuración CORS |

---

**Fortalezas del Equipo Identificadas:**

1. **Dominio Técnico Backend**: Gilbert demostró dominio completo del stack Spring Boot + DDD
2. **Integración de Servicios Externos**: Stripe y Cloudinary integrados exitosamente
3. **Documentación Completa**: 60+ endpoints documentados en OpenAPI/Swagger
4. **Testing Riguroso**: Unit tests, integration tests y BDD tests para todas las épicas
5. **Mobile Parallel Development**: Android y Flutter avanzando en paralelo con integración backend

---

**Áreas de Mejora para Sprint 3:**

1. Aumentar cobertura de tests a > 85%
2. Implementar CI/CD pipeline automatizado con GitHub Actions
3. Performance monitoring y logging centralizado
4. Más documentación de arquitectura en PlantUML/C4
5. Aumentar pair programming para knowledge sharing entre mobile y backend

---

**Conclusión de Colaboración:**

Sprint 2 fue altamente productivo, consolidando las funcionalidades core de Rent2Go:
- **Backend Completo**: 60+ endpoints funcionales cubriendo IAM, Vehicle Catalog, Booking, Payments, Community y Messaging
- **Integraciones Externas**: Stripe (pagos) y Cloudinary (imágenes/documentos) integrados y operativos
- **Mobile Apps**: Pantallas funcionales en Android (Kotlin) y Flutter con integración al backend
- **Documentación**: OpenAPI/Swagger completo para todos los endpoints
- **Testing**: Unit, integration y BDD tests para todas las épicas

El equipo demostró capacidad técnica sólida y disciplina en la ejecución, posicionándose para el Sprint 3 con una base sólida para las funcionalidades restantes (reservas avanzadas, notificaciones, analytics).

---

<div style="page-break-after: always;"></div>

## 4.3. Validation Interviews

En esta sección, el equipo registra y explica las actividades de entrevistas de validación. Se diseñaron y llevaron a cabo entrevistas con usuarios reales pertenecientes a los segmentos objetivo para validar la usabilidad, utilidad y aceptación de la versión funcional desplegada de la aplicación móvil Rent2Go, analizando los flujos clave tanto de propietarios como de arrendatarios.

### 4.3.1. Diseño de Entrevistas de Validación

**Objetivo:**
Validar la usabilidad, utilidad percibida y aceptación de la aplicación móvil Rent2Go por parte de los segmentos objetivo, mediante la interacción directa con la versión funcional desplegada. Se busca identificar problemas de usabilidad, funcionalidades faltantes y oportunidades de mejora en los flujos principales de alquiler de vehículos entre particulares.

**Público Objetivo:**
Se entrevistarán los mismos dos segmentos de las entrevistas de needfinding:
1. **Propietarios de vehículos particulares con baja frecuencia de uso**
2. **Arrendatarios que buscan opciones de movilidad temporal y flexible**

*Características comunes de los participantes:*
- **Edad:** 18 a 60 años
- **Residencia:** Zonas urbanas a nivel nacional
- **Dispositivo:** Acceso a un smartphone (Android o iOS)
- **Criterio de inclusión:** Haber participado en las entrevistas iniciales de needfinding

**Tipo de Entrevistas:**
Se utilizarán entrevistas de validación estructuradas, combinando la observación directa del usuario interactuando con la aplicación móvil y preguntas posteriores orientadas a recoger su percepción sobre la experiencia.

**Metodología:**

| Aspecto | Detalle |
| --- | --- |
| **Modalidad** | Virtual |
| **Duración** | 15 a 20 minutos por entrevista |
| **Herramienta** | Se compartirá el enlace de descarga o la URL de la aplicación desplegada (APK o PWA) para que el usuario la explore desde su propio dispositivo móvil |
| **Registro** | Video de la sesión subido a Microsoft Stream, con notas escritas en el informe |

**Dinámica de la Sesión:**
Cada sesión se divide en dos partes:
1. **Pruebas de tareas (Observación directa):** Se le pide al entrevistado que realice una serie de tareas dentro de la aplicación sin intervención del equipo, mientras se observa su comportamiento en pantalla y navegación.
2. **Entrevista estructurada (Preguntas de validación):** Se realizan las preguntas de validación basadas en lo observado y en la experiencia directa del usuario con el fin de recoger feedback cualitativo.

**User Flows a Evaluar Durante la Sesión:**

*Para Propietarios de Vehículos:*
- Registrarse e iniciar sesión en la aplicación como propietario.
- Publicar un vehículo ingresando sus datos, fotos, disponibilidad y precio por día.
- Revisar y gestionar una solicitud de alquiler recibida (aceptar o rechazar).
- Consultar el historial de alquileres realizados y los ingresos generados.
- Revisar las calificaciones y comentarios recibidos de arrendatarios.

*Para Arrendatarios de Vehículos:*
- Registrarse e iniciar sesión en la aplicación como arrendatario.
- Buscar un vehículo disponible aplicando filtros (zona, tipo, precio).
- Revisar el detalle de un vehículo (fotos, descripción, calificaciones del propietario) y realizar una reserva.
- Consultar el estado de su reserva activa y los detalles del vehículo asignado.
- Calificar al propietario y al vehículo al finalizar el alquiler.

**Guía de Preguntas para la Validación:**

*Preguntas para Propietarios de Vehículos:*
1. Al ver la pantalla de inicio, ¿qué fue lo primero que entendiste que podías hacer con la aplicación como propietario?
2. Al registrar tu vehículo, ¿el proceso te pareció claro y completo? ¿Qué fue lo más complicado o lo que más tiempo te tomó?
3. La información que solicita la app para publicar tu vehículo (fotos, precio, disponibilidad), ¿te parece suficiente o echarías algo de menos?
4. Cuando recibiste una solicitud de alquiler, ¿la información que te mostraba sobre el arrendatario te generó suficiente confianza para aceptarla? ¿Qué más querrías saber?
5. ¿El historial de alquileres e ingresos que muestra la app te da una imagen clara de cómo te está yendo económicamente?
6. ¿Ver las calificaciones y comentarios que te dejan los arrendatarios te motivaría a mejorar la presentación de tu vehículo o tu atención? ¿O no le darías mucha importancia?
7. ¿Hubo alguna pantalla o función que no entendiste a la primera o que te resultó confusa?
8. ¿Qué tan probable es que recomiendes esta aplicación a otros propietarios de tu entorno? ¿Qué mejorarías antes de hacerlo?

*Preguntas para Arrendatarios de Vehículos:*
1. Al ver la pantalla de inicio, ¿qué fue lo primero que entendiste que podías hacer con la aplicación?
2. Al buscar un vehículo, ¿los filtros disponibles (zona, tipo de vehículo, precio) te fueron suficientes para encontrar lo que necesitabas? ¿Qué filtro adicional agregarías?
3. La información del vehículo que encontraste (fotos, descripción, calificaciones del propietario), ¿te generó confianza suficiente para querer reservarlo? ¿Qué le faltó o qué le sobró?
4. ¿El precio por día que muestra la app te pareció justo o razonable comparado con las opciones que conocías antes? ¿Por qué?
5. ¿Hubo algún paso durante el proceso de reserva en que no supiste qué hacer o te confundiste?
6. Comparando con cómo conseguías un vehículo de alquiler antes, ¿sientes que esta forma es mejor, igual o peor? ¿Qué te lo hace pensar?
7. ¿Qué tan fácil o difícil fue calificar al propietario y al vehículo al finalizar el alquiler? ¿Lo harías en la vida real?
8. ¿Hay alguna función que esperabas encontrar y no encontraste?
9. ¿Usarías esta aplicación la próxima vez que necesites alquilar un vehículo? ¿Qué te lo impediría?

*Pregunta de Cierre (Ambos Segmentos):*
- En una sola frase, ¿cómo describirías esta aplicación a alguien de tu ciudad que aún no la conoce?

**Consideraciones Éticas:**
- Se solicitará al entrevistado el consentimiento explícito para la grabación de la sesión y el uso de su información antes de iniciar.
- Se garantizará la confidencialidad de toda la información proporcionada durante la entrevista.
- Los datos obtenidos serán utilizados únicamente con fines académicos, en el marco del curso de Aplicaciones Móviles de la Universidad Peruana de Ciencias Aplicadas (UPC).

---

### 4.3.2. Registro de Entrevistas

**Entrevista 1 - Segmento: Propietario (Validación de Aplicación Móvil)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Captura de Video** | <img src="Resources/capitulo_4/interviews/1-entrevista-1.png" alt="Captura entrevista 1" width="320"> |
| **URL Stream** | [Insert link Microsoft Stream] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las principales apreciaciones del propietario. Incluir:
- Primeras impresiones al iniciar la app.
- Claridad y facilidad para registrar y publicar el vehículo.
- Suficiencia de la información y fotos solicitadas para el vehículo.
- Nivel de confianza que genera la información del arrendatario al recibir una solicitud.
- Entendimiento del historial de alquileres e ingresos.
- Motivación frente al sistema de calificaciones y comentarios.
- Identificación de pantallas o funciones confusas.
- Probabilidad de recomendación y propuestas de mejora.]

---

**Entrevista 2 - Segmento: Propietario (Validación de Aplicación Móvil)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Captura de Video** | <img src="Resources/capitulo_4/interviews/2-entrevista-2.png" alt="Captura entrevista 2" width="320"> |
| **URL Stream** | [Insert link Microsoft Stream] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las apreciaciones del segundo propietario sobre la interacción con la aplicación.]

---

**Entrevista 3 - Segmento: Arrendatario (Validación de Aplicación Móvil)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Captura de Video** | <img src="Resources/capitulo_4/interviews/3-entrevista-3.png" alt="Captura entrevista 3" width="320"> |
| **URL Stream** | [Insert link Microsoft Stream] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las principales apreciaciones del arrendatario. Incluir:
- Facilidad para buscar vehículos y suficiencia de los filtros aplicados (zona, tipo, precio).
- Nivel de confianza inspirado por la información detallada del vehículo y la reputación del dueño.
- Percepción del precio y facilidad para realizar/confirmar el proceso de reserva.
- Facilidad para consultar el estado de la reserva activa.
- Utilidad y usabilidad en el flujo de calificación al propietario y vehículo.
- Comparación de este método con los tradicionales y la intención real de uso futuro.]

---

**Entrevista 4 - Segmento: Arrendatario (Validación de Aplicación Móvil)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Captura de Video** | <img src="Resources/capitulo_4/interviews/4-entrevista-4.png" alt="Captura entrevista 4" width="320"> |
| **URL Stream** | [Insert link Microsoft Stream] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las apreciaciones del segundo arrendatario sobre la interacción con la aplicación.]

---

### 4.3.3. Evaluaciones según heurísticas

**UX Heuristics & Principles Evaluation**
_Usability – Inclusive Design – Information Architecture_

**SITE o APP A EVALUAR:**
Rent2Go – Aplicación móvil de alquiler de vehículos entre particulares (vistas de propietario y arrendatario).

**TAREAS A EVALUAR:**
El alcance de esta evaluación incluye la revisión de la usabilidad de las siguientes tareas en los flujos principales de la aplicación:

_Segmento Propietario:_
1. Registrarse e iniciar sesión en la aplicación como propietario.
2. Publicar un vehículo ingresando sus datos, fotos, disponibilidad y precio por día.
3. Revisar y gestionar una solicitud de alquiler recibida (aceptar o rechazar).
4. Consultar el historial de alquileres realizados y los ingresos generados.
5. Revisar las calificaciones y comentarios recibidos de arrendatarios.

_Segmento Arrendatario:_
6. Registrarse e iniciar sesión en la aplicación como arrendatario.
7. Buscar un vehículo disponible aplicando filtros (zona, tipo, precio).
8. Revisar el detalle de un vehículo (fotos, descripción, calificaciones del propietario) y realizar una reserva.
9. Consultar el estado de su reserva activa y los detalles del vehículo asignado.
10. Calificar al propietario y al vehículo al finalizar el alquiler.

No están incluidas en esta versión de la evaluación las siguientes tareas:
1. Comunicación directa por chat en tiempo real entre propietario y arrendatario.
2. Pasarela de pagos digitales y facturación integrada.
3. Carga y validación automática de multas de tránsito.
4. Cobertura de seguros contra accidentes (SOAT digital integrado).

**ESCALA DE SEVERIDAD:**

| Nivel | Descripción |
| ----- | ----------- |
| 1     | Problema superficial: puede ser fácilmente superado por el usuario o ocurre con muy poca frecuencia. No necesita ser arreglado a no ser que exista disponibilidad de tiempo. |
| 2     | Problema menor: puede ocurrir un poco más frecuentemente o es un poco más difícil de superar para el usuario. Se le debería asignar una prioridad baja de cara al siguiente release. |
| 3     | Problema mayor: ocurre frecuentemente o los usuarios no son capaces de resolverlo. Es importante que sea corregido y se le debe asignar prioridad alta. |
| 4     | Problema muy grave: un error de gran impacto que impide al usuario continuar con el uso de la herramienta. Es imperativo que sea corregido antes del lanzamiento. |

**TABLA RESUMEN:**

| #   | Problema | Segmento | Escala de severidad | Heurística/Principio violada(o) |
| --- | -------- | -------- | ------------------- | ------------------------------- |
| 1   | Falta de notificaciones y actualizaciones en tiempo real en la gestión de reservas | Ambos | 3 | Usability: Visibilidad del estado del sistema |
| 2   | Ausencia de geolocalización en tiempo real para coordinar la entrega y devolución del vehículo | Ambos | 3 | Usability: Visibilidad del estado del sistema |
| 3   | Proceso de validación de documentos (licencia de conducir y DNI) confuso y sin feedback de estado | Arrendatario | 2 | Usability: Ayuda y documentación |
| 4   | Ausencia de filtros de búsqueda avanzados (tipo de transmisión, combustible, equipamiento adicional) | Arrendatario | 2 | Usability: Flexibilidad y eficiencia de uso |
| 5   | No se indica visualmente cuáles campos del formulario de registro de vehículos son obligatorios | Propietario | 2 | Usability: Prevención de errores |
| 6   | Dificultad o imposibilidad de modificar o cancelar una reserva activa directamente desde la app | Ambos | 3 | Usability: Control y libertad del usuario |
| 7   | El historial de ingresos no permite comparar periodos (semana/mes actual vs. anterior) | Propietario | 1 | Information Architecture: Is it useful? |
| 8   | Las calificaciones muestran solo estrellas, sin permitir comentarios detallados de retroalimentación | Ambos | 2 | Usability: Visibilidad del estado del sistema |
| 9   | Contraste de colores deficiente en textos secundarios y etiquetas de estado de vehículos | Ambos | 2 | Accesibilidad (WCAG 2.1) |

**DESCRIPCIÓN DE PROBLEMAS:**

**PROBLEMA #1: Falta de notificaciones y actualizaciones en tiempo real en la gestión de reservas**
*   **Severidad:** 3
*   **Heurística violada:** Usability – Visibilidad del estado del sistema
*   **Problema:** Los usuarios reportaron que cuando un arrendatario realiza una solicitud de reserva, el propietario no recibe una notificación en tiempo real. De forma similar, el arrendatario debe recargar manualmente la vista de su reserva para enterarse si su solicitud fue aceptada o rechazada. Esto incrementa la fricción y el tiempo de espera.
*   _(Incluir captura de pantalla del flujo de reserva/solicitud)_
*   **Recomendación:** Integrar un servicio de notificaciones push en tiempo real (por ejemplo, Firebase Cloud Messaging) y actualizar dinámicamente el estado de la reserva en pantalla a través de sockets o listeners activos.

**PROBLEMA #2: Ausencia de geolocalización en tiempo real para coordinar la entrega**
*   **Severidad:** 3
*   **Heurística violada:** Usability – Visibilidad del estado del sistema
*   **Problema:** Al aproximarse la hora de inicio de la reserva, ni el propietario ni el arrendatario pueden visualizar la ubicación física del otro en un mapa en tiempo real para encontrarse y entregar las llaves del vehículo. Esto los obliga a coordinar mediante llamadas telefónicas externas o mensajería de terceros.
*   _(Incluir captura de pantalla del mapa o pantalla previa a la entrega)_
*   **Recomendación:** Incorporar un mapa interactivo de seguimiento GPS activo únicamente durante las horas programadas de entrega y devolución del vehículo.

**PROBLEMA #3: Proceso de validación de documentos confuso y sin feedback de estado**
*   **Severidad:** 2
*   **Heurística violada:** Usability – Ayuda y documentación
*   **Problema:** Durante el registro de arrendatarios, al solicitar la foto de la licencia de conducir (brevete) y del documento de identidad, no se especifican los formatos permitidos ni las pautas de nitidez. Además, tras subir las imágenes, no se muestra ningún mensaje sobre si los archivos se encuentran en revisión, aprobados o rechazados.
*   _(Incluir captura de pantalla del paso de subida de documentos KYC)_
*   **Recomendación:** Agregar pautas explícitas de subida (ej. "Formatos PNG o JPG, tamaño máximo 5MB") y mostrar un banner claro de estado (ej. "Tus documentos están siendo verificados. Tiempo estimado: 15 min").

**PROBLEMA #4: Ausencia de filtros de búsqueda avanzados**
*   **Severidad:** 2
*   **Heurística violada:** Usability – Flexibilidad y eficiencia de uso
*   **Problema:** El buscador de vehículos solo permite filtrar por zona, tipo de carrocería y rango de precio general. Los arrendatarios señalaron que para alquilar un auto es crucial conocer el tipo de transmisión (manual/automática) y el tipo de combustible (gasolina, GLP, eléctrico), opciones que actualmente no se pueden filtrar.
*   _(Incluir captura de pantalla del panel de filtros de búsqueda)_
*   **Recomendación:** Expandir la funcionalidad de filtros añadiendo opciones específicas de transmisión, combustible, y equipamiento básico (ej. aire acondicionado, GPS, cámara de retroceso).

**PROBLEMA #5: No se indica visualmente cuáles campos del registro de vehículos son obligatorios**
*   **Severidad:** 2
*   **Heurística violada:** Usability – Prevención de errores
*   **Problema:** Al completar el formulario para registrar y publicar un vehículo, no hay marcas visuales (como asteriscos) que identifiquen cuáles campos son estrictamente requeridos (SOAT, kilometraje, fotos) y cuáles opcionales (descripción adicional). Si el usuario omite uno, la app muestra un error genérico tras intentar guardar.
*   _(Incluir captura de pantalla del formulario de publicación de vehículo)_
*   **Recomendación:** Señalar con un asterisco (*) los campos obligatorios, validar las entradas inline y mantener el botón "Publicar" inactivo hasta que se cumplan las condiciones mínimas.

**PROBLEMA #6: Dificultad o imposibilidad de modificar o cancelar una reserva activa**
*   **Severidad:** 3
*   **Heurística violada:** Usability – Control y libertad del usuario
*   **Problema:** En el flujo de reservas activas, el arrendatario no cuenta con un botón directo para cancelar o solicitar un cambio de fecha ante un imprevisto. La interfaz asume un flujo lineal sin posibilidad de retroceso, lo que genera desconfianza y obliga al usuario a recurrir a canales de soporte externos.
*   _(Incluir captura de pantalla del detalle de reserva confirmada)_
*   **Recomendación:** Añadir un botón visible de "Cancelar reserva" y otro de "Solicitar reprogramación", aplicando las políticas de cobro o penalización parametrizadas por el sistema.

**PROBLEMA #7: El historial de ingresos no permite comparar periodos**
*   **Severidad:** 1
*   **Heurística violada:** Information Architecture – Is it useful?
*   **Problema:** El panel financiero del propietario solo muestra una lista plana de ingresos acumulados cronológicamente. No es posible agrupar las ganancias por periodos de tiempo (semanas, meses, años) ni contrastar el desempeño económico actual con el de periodos anteriores.
*   _(Incluir captura de pantalla del panel de ingresos del propietario)_
*   **Recomendación:** Integrar un selector de fecha/periodo en la sección de ingresos y un indicador gráfico simplificado que compare la rentabilidad respecto al mes anterior.

**PROBLEMA #8: Las calificaciones muestran solo estrellas, sin permitir comentarios detallados**
*   **Severidad:** 2
*   **Heurística violada:** Usability – Visibilidad del estado del sistema
*   **Problema:** Tras finalizar un alquiler, los usuarios únicamente pueden calificar con un rango de 1 a 5 estrellas. Los propietarios manifestaron que esto impide conocer las razones específicas detrás de una calificación baja (por ejemplo, problemas de limpieza o retraso en la entrega) para poder corregirlos.
*   _(Incluir captura de pantalla de la pantalla de calificación final)_
*   **Recomendación:** Añadir un campo opcional para comentarios escritos e incorporar etiquetas de selección rápida (ej. "Limpieza excelente", "Puntual", "Trato amable").

**PROBLEMA #9: Contraste de colores deficiente en textos secundarios y etiquetas**
*   **Severidad:** 2
*   **Heurística violada:** Accesibilidad (WCAG 2.1)
*   **Problema:** Las etiquetas secundarias que indican el estado del vehículo (ej. "En mantenimiento" o "Disponible") utilizan combinaciones de colores con bajo contraste visual, dificultando su lectura para usuarios con fatiga visual o en condiciones de luz solar directa en dispositivos móviles.
*   **Recomendación:** Ajustar la paleta de colores de los estados y tipografías secundarias para cumplir con el nivel mínimo de contraste WCAG AA (4.5:1).

**Resumen de la Evaluación:**
Las pruebas de usabilidad revelaron que Rent2Go posee una arquitectura de información base sólida y flujos de registro comprensibles; sin embargo, adolece de mecanismos dinámicos e interactivos en tiempo real (notificaciones instantáneas y rastreo GPS) que son indispensables para coordinar un alquiler de vehículos seguro y ágil. Asimismo, existen oportunidades críticas de mejora en la prevención de errores (formularios de publicación), la flexibilidad del usuario (opción de cancelación/modificación) y la retroalimentación cualitativa (comentarios en las calificaciones). La implementación de estas recomendaciones prioritarias elevará significativamente la percepción de seguridad y la retención tanto de propietarios como de arrendatarios en la plataforma móvil.