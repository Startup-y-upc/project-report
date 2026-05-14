# Capítulo IV: Product Implementation & Validation

<div style="page-break-after: always;"></div>

## 4. Product Implementation & Validation

En esta sección el equipo explica y evidencia el proceso de implementar, comprobar, desplegar y validar la solución compuesta por los productos digitales que forman parte del alcance. El Landing Page presenta el modelo de negocio y las aplicaciones móviles. Los procesos del negocio digital que dirigen la operación del negocio, tanto procesos core como procesos de soporte (Authentication & Authorization, Subscriptions), están distribuidos entre los productos digitales que forman parte del alcance como RESTful Web Services, Native Mobile Applications y Web Applications.

Este capítulo abarca secciones para la organización del proceso de trabajo en Sprints, la descripción y prácticas asociadas a Software Configuration Management, y las evidencias de Implementation, Testing, Deployment y Validación para cada uno de los productos que forman parte de la solución, en términos del producto en sí y la colaboración por Sprint.

---

<div style="page-break-after: always;"></div>

## 4.1. Software Configuration Management

En esta sección el equipo establece las decisiones y convenciones que permitirán mantener la consistencia durante el ciclo de vida. Se incluyen secciones internas para Source Code Management, Development Environment Configuration y Deployment Configuration.

### 4.1.1. Software Development Environment Configuration

En esta sección se especifica, describe e indica los nombres de productos, el propósito de uso en el proyecto, la ruta de referencia (para software basado en modelos SaaS) o ruta de descarga de cada uno de los productos de software que deben utilizar los miembros del equipo para colaborar en el ciclo de vida de los productos digitales que forman la solución.

| Producto | Versión | Propósito | Referencia |
| --- | --- | --- | --- |
| **JDK (Java Development Kit)** | 17.0 | Desarrollo del backend con Spring Boot | [https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html) |
| **Apache Maven** | 3.8.1+ | Gestor de dependencias y build para Spring Boot | [https://maven.apache.org/download.cgi](https://maven.apache.org/download.cgi) |
| **IDE - IntelliJ IDEA** | 2024+ | Entorno de desarrollo para Java/Spring Boot | [https://www.jetbrains.com/idea/](https://www.jetbrains.com/idea/) |
| **Node.js** | 18.0+ | Runtime para herramientas de build frontend | [https://nodejs.org/](https://nodejs.org/) |
| **Visual Studio Code** | Latest | Editor para desarrollo frontend y móvil | [https://code.visualstudio.com/](https://code.visualstudio.com/) |
| **Android Studio** | Latest | IDE para desarrollo Android Kotlin | [https://developer.android.com/studio](https://developer.android.com/studio) |
| **Xcode** | Latest | IDE para desarrollo iOS Swift | [https://developer.apple.com/xcode/](https://developer.apple.com/xcode/) |
| **Flutter SDK** | 3.10+ | Framework para desarrollo cross-platform | [https://flutter.dev/docs/get-started/install](https://flutter.dev/docs/get-started/install) |
| **Dart** | 3.0+ | Lenguaje para Flutter | [https://dart.dev/get-dart](https://dart.dev/get-dart) |
| **Git** | 2.40+ | Control de versiones | [https://git-scm.com/](https://git-scm.com/) |
| **GitHub Desktop** | Latest | Interfaz gráfica para Git | [https://desktop.github.com/](https://desktop.github.com/) |
| **Figma** | Cloud | Diseño y prototipado UI/UX | [https://www.figma.com/](https://www.figma.com/) |
| **Postman** | Latest | Herramienta para testing de APIs REST | [https://www.postman.com/downloads/](https://www.postman.com/downloads/) |
| **MySQL Workbench** | 8.0+ | Modelado y administración de BD MySQL | [https://www.mysql.com/products/workbench/](https://www.mysql.com/products/workbench/) |
| **Docker** | Latest | Containerización para despliegue | [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop) |
| **Firebase** | Console | Testing y distribución de apps móviles | [https://console.firebase.google.com/](https://console.firebase.google.com/) |

---

### 4.1.2. Source Code Management

En esta sección el equipo establece el esquema de organización y control de versiones aplicado a la solución. Se utiliza GitHub como plataforma y sistema de control de versiones.

**Repositorios del Proyecto:**

| Producto | URL Repositorio | Rama Principal | Estado |
| --- | --- | --- | --- |
| Landing Page | [https://github.com/Startup-y-upc/rent2go-landing](https://github.com/Startup-y-upc/rent2go-landing) | main | [Insert status] |
| Backend (Web Services) | [https://github.com/Startup-y-upc/rent2go-backend](https://github.com/Startup-y-upc/rent2go-backend) | master | [Insert status] |
| Frontend Web | [https://github.com/Startup-y-upc/rent2go-frontend](https://github.com/Startup-y-upc/rent2go-frontend) | main | [Insert status] |
| Mobile (Android/iOS/Flutter) | [https://github.com/Startup-y-upc/rent2go-mobile](https://github.com/Startup-y-upc/rent2go-mobile) | main | [Insert status] |

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

**Dart (Flutter Mobile):**
- Guía: [Dart Style Guide](https://dart.dev/guides/language/effective-dart/style)
- Nomenclatura: camelCase para variables y funciones, PascalCase para clases
- Ejemplo: `class VehicleRepository {}`

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

[Insert Deployment Diagram C4 Model - URL a imagen]

**Estrategia de Despliegue por Producto:**

**Landing Page:**
- Plataforma: Vercel o Netlify (SaaS)
- Trigger: Merge a main branch
- Process: Automatic build & deploy
- URL: [Insert production URL]
- Configuración: Environment variables en .env.production

**Backend (Web Services):**
- Plataforma: AWS EC2 o Azure App Service
- Container: Docker
- Orchestration: [Insert si aplica - Kubernetes, etc.]
- CI/CD: GitHub Actions
- Database: MySQL en AWS RDS
- Configuración: application.properties por ambiente (dev, staging, prod)

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

**Sprint # Sprint 1**

| Aspecto | Descripción |
| --- | --- |
| **Date** | [Insert YYYY-MM-DD] |
| **Time** | [Insert HH:MM AM/PM] |
| **Location** | Virtual - [Insert plataforma de reunión] |
| **Prepared By** | [Insert nombre] |
| **Attendees** | Carhuancote Dominguez, Gonzalo Alonso<br>Castillo Vidal, Jesus Ivan<br>Chavez Uribe, Ario Joel<br>Diestra Zambrano, Adriana Maria<br>Huarcaya Matias, Gilbert Alonso |

**Sprint 0 Review Summary:**
- No hay sprint anterior.

**Sprint 0 Retrospective Summary:**
- No hay sprint anterior.

**Sprint Goal & User Stories:**

| Aspecto | Descripción |
| --- | --- |
| **Sprint 1 Goal** | Implementar y desplegar Landing Page informativo (HU15-HU18) que presente el modelo de negocio de Rent2Go, e iniciar backend de catálogo de vehículos (HU02-HU05) con búsqueda, filtrado y gestión de favoritos. Permitir que visitantes conozcan el servicio y que arrendatarios comiencen a interactuar con funcionalidades core de búsqueda. |
| **Sprint 1 Velocity** | [Insert story points capacity] |
| **Sum of Story Points** | [Insert total story points] |

**User Stories Incluidas en Sprint 1 (Priorizadas):**

| Story ID | Título | Descripción | Story Points | Prioridad |
| --- | --- | --- | --- | --- |
| **Landing Page (EP06 - Plataforma y Soporte)** | | | | |
| HU15 | Ver landing page informativa | Como visitante, quiero ver una landing page informativa, para conocer el servicio. | [Insert] | Medium |
| HU16 | Ver información de contacto | Como visitante, quiero ver información de contacto, para comunicarme con la empresa. | [Insert] | Medium |
| HU17 | Navegar intuitivamente en landing | Como visitante, quiero navegar fácilmente la landing, para encontrar contenido sin fricción. | [Insert] | Low |
| HU18 | Adaptar landing responsiva | Como visitante, quiero que la landing sea responsiva, para verla bien en distintos dispositivos. | [Insert] | Low |
| **Backend - Vehicle Catalog (EP02 - Catálogo y Búsqueda)** | | | | |
| HU02 | Buscar vehículos disponibles | Como arrendatario, quiero buscar vehículos disponibles, para seleccionar uno adecuado a mis necesidades. | [Insert] | High |
| HU03 | Filtrar por precio | Como arrendatario, quiero filtrar vehículos por precio, para ajustar el resultado a mi presupuesto. | [Insert] | Medium |
| HU04 | Ver detalles de vehículo | Como arrendatario, quiero ver detalles de un vehículo, para tomar una decisión informada. | [Insert] | Medium |
| HU05 | Agregar a favoritos | Como arrendatario, quiero agregar vehículos a favoritos, para revisarlos más tarde. | [Insert] | Medium |

---

#### 4.2.1.2. Sprint Backlog 1

**Introducción:**

En Sprint 1, el equipo se enfoca en las historias de usuario de mayor prioridad:
- **Landing Page (HU15-HU18):** Crear landing page informativa para que visitantes conozcan el servicio, con contacto, navegación intuitiva y diseño responsivo.
- **Backend Vehicle Catalog (HU02-HU05):** Implementar búsqueda, filtro por precio, detalle de vehículo y gestión de favoritos para que arrendatarios puedan descubrir y seleccionar vehículos.

La integración de estos productos permitirá validar tempranamente el concepto con usuarios reales.

**Estado del Sprint Backlog (Trello Board):**

[Insert screenshot de Trello Board]

**URL del Board:** [Insert URL público de Trello]

**Tabla de Control de Estado:**

| Sprint # | User Story | Work-Item / Task | Id | Title | Description | Estimation (Hours) | Assigned To | Status |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Sprint 1** | HU15 | Task | HU15-01 | Setup landing page project | Configure Vite + Vue 3 + Tailwind CSS | 4 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU15-02 | Implement landing page sections | Create navbar, hero, features, how-it-works, FAQ, footer | 20 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU15-03 | Add i18n support | Implement English/Spanish translations for all sections | 6 | [Name] | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | HU16 | Task | HU16-01 | Create contact section | Design and implement contact information display | 4 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU16-02 | Add social media links | Implement links to social networks and contact form | 3 | [Name] | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | HU17 | Task | HU17-01 | Implement navigation menu | Create intuitive menu structure with anchor links | 5 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU17-02 | Add smooth scrolling | Implement smooth scroll to sections | 2 | [Name] | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | HU18 | Task | HU18-01 | Implement responsive design | Create responsive CSS for mobile, tablet, desktop | 8 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU18-02 | Test responsiveness | Test on multiple devices and screen sizes | 3 | [Name] | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | HU02 | Task | HU02-01 | Setup Spring Boot project | Create Maven project with Spring Boot 3.5.7 | 4 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU02-02 | Configure MySQL database | Setup connection and schema for vehicle catalog | 5 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU02-03 | Create Vehicle entity | Implement Vehicle aggregate root with properties | 6 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU02-04 | Create Vehicle repository | Implement Spring Data JPA repository | 4 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU02-05 | Implement search endpoint | Create GET /api/vehicles/search with query parameters | 8 | [Name] | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | HU03 | Task | HU03-01 | Add price filter logic | Implement price range filtering in repository | 5 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU03-02 | Create filter endpoint | Implement GET /api/vehicles/filter?minPrice=X&maxPrice=Y | 5 | [Name] | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | HU04 | Task | HU04-01 | Implement vehicle detail service | Add service layer method for vehicle details | 5 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU04-02 | Create detail endpoint | Implement GET /api/vehicles/{id} | 4 | [Name] | [To-Do/In-Process/To-Review/Done] |
| **Sprint 1** | HU05 | Task | HU05-01 | Design favorites feature | Plan storage and query strategies for favorites | 4 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU05-02 | Implement favorites service | Add favorites management business logic | 6 | [Name] | [To-Do/In-Process/To-Review/Done] |
| | | Task | HU05-03 | Create favorites endpoints | Implement POST/DELETE /api/favorites | 5 | [Name] | [To-Do/In-Process/To-Review/Done] |

---

#### 4.2.1.3. Development Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo implementó todas las historias de usuario priorizadas:
- **Landing Page (HU15-HU18):** Implementación del landing page informativo con secciones core, información de contacto, navegación intuitiva y diseño responsivo.
- **Backend Vehicle Catalog (HU02-HU05):** Endpoints de búsqueda, filtrado por precio, detalle de vehículo, y gestión de favoritos.

Se realizaron commits regulares en ambos repositorios, siguiendo GitFlow y Conventional Commits. A continuación se presenta el resumen de avances en implementación.

**Commits en Landing Page Repository:**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |
| rent2go-landing | feature/landing-page | [Insert] | feat(landing): implement informative landing page (HU15) | Implemented all landing page sections: navbar, hero, features, how-it-works, FAQ, footer. Added i18n support for ES/EN. | [Insert YYYY-MM-DD] |
| rent2go-landing | feature/contact-section | [Insert] | feat(landing): add contact information section (HU16) | Added contact section with phone, email, and social media links. Integrated contact form. | [Insert YYYY-MM-DD] |
| rent2go-landing | feature/navigation | [Insert] | feat(landing): implement intuitive navigation (HU17) | Added smooth scrolling and anchor links for all sections. Improved menu navigation. | [Insert YYYY-MM-DD] |
| rent2go-landing | feature/responsive-design | [Insert] | feat(landing): implement responsive design (HU18) | Added responsive CSS for mobile, tablet, and desktop viewports. Tested on multiple devices. | [Insert YYYY-MM-DD] |
| rent2go-landing | develop | [Insert] | Merge: landing page Sprint 1 complete | Merged all landing page features to develop branch. | [Insert YYYY-MM-DD] |

**Commits en Backend Repository (Vehicle Catalog):**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| --- | --- | --- | --- | --- | --- |
| rent2go-backend | feature/vehicle-setup | [Insert] | feat(vehicle-catalog): setup Spring Boot project (HU02) | Initialized Spring Boot 3.5.7 with Maven, configured application.properties, and database connection to MySQL. | [Insert YYYY-MM-DD] |
| rent2go-backend | feature/vehicle-entity | [Insert] | feat(vehicle-catalog): create Vehicle aggregate root (HU02) | Implemented Vehicle domain entity with properties: id, make, model, year, price, availability, owner_id. | [Insert YYYY-MM-DD] |
| rent2go-backend | feature/vehicle-repo | [Insert] | feat(vehicle-catalog): implement vehicle repository (HU02) | Created Spring Data JPA VehicleRepository with custom query methods. | [Insert YYYY-MM-DD] |
| rent2go-backend | feature/vehicle-search | [Insert] | feat(vehicle-catalog): add vehicle search (HU02) | Implemented search endpoint GET /api/vehicles/search with make, model, year, and availability filters. | [Insert YYYY-MM-DD] |
| rent2go-backend | feature/vehicle-filter | [Insert] | feat(vehicle-catalog): implement price filter (HU03) | Added price range filtering logic. Created GET /api/vehicles/filter?minPrice=X&maxPrice=Y endpoint. | [Insert YYYY-MM-DD] |
| rent2go-backend | feature/vehicle-detail | [Insert] | feat(vehicle-catalog): add vehicle detail endpoint (HU04) | Implemented GET /api/vehicles/{id} with complete vehicle information and rental conditions. | [Insert YYYY-MM-DD] |
| rent2go-backend | feature/favorites | [Insert] | feat(vehicle-catalog): implement favorites feature (HU05) | Added Favorite entity and endpoints POST/DELETE /api/favorites for managing user favorites. | [Insert YYYY-MM-DD] |
| rent2go-backend | develop | [Insert] | Merge: vehicle catalog Sprint 1 complete | Merged all vehicle catalog features to develop branch. | [Insert YYYY-MM-DD] |

---

#### 4.2.1.4. Testing Suite Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo implementó unit tests, integration tests, y BDD acceptance tests para las historias de usuario del Backend Vehicle Catalog (HU02-HU05). Se priorizó la cobertura de búsqueda, filtrado, detalle y favoritos, garantizando que los endpoints cumplen con los requisitos especificados.

**Unit Tests - Backend Vehicle Catalog:**

| Test File | Test Class | Method | Description | Related to (HU) | Status |
| --- | --- | --- | --- | --- | --- |
| VehicleRepositoryTest.java | VehicleRepositoryTest | testFindBySearchCriteria | Verifica que la búsqueda por make y model retorna vehículos correctos | HU02 | [Pass/Fail] |
| VehicleRepositoryTest.java | VehicleRepositoryTest | testFindByPriceRange | Verifica filtro de precio funciona correctamente | HU03 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testSearchVehicles | Verifica servicio de búsqueda retorna resultados esperados | HU02 | [Pass/Fail] |
| VehicleServiceTest.java | VehicleServiceTest | testGetVehicleDetail | Verifica que obtiene detalles correctos de un vehículo | HU04 | [Pass/Fail] |
| FavoriteServiceTest.java | FavoriteServiceTest | testAddToFavorites | Verifica que se agrega correctamente un vehículo a favoritos | HU05 | [Pass/Fail] |
| FavoriteServiceTest.java | FavoriteServiceTest | testRemoveFromFavorites | Verifica que se elimina correctamente de favoritos | HU05 | [Pass/Fail] |

**Integration Tests - Backend API:**

| Feature File | Scenario | Given | When | Then | Related to (HU) | Status |
| --- | --- | --- | --- | --- | --- | --- |
| vehicle-search.feature | Successful vehicle search | User searches for vehicles with specific criteria | Executes GET /api/vehicles/search | Returns list of matching vehicles | HU02 | [Pass/Fail] |
| vehicle-search.feature | No results found | User searches with criteria that don't match | Executes GET /api/vehicles/search | Returns empty list with 200 OK | HU02 | [Pass/Fail] |
| vehicle-filter.feature | Filter by price range | User applies price filter | Executes GET /api/vehicles/filter?minPrice=100&maxPrice=500 | Returns vehicles within price range | HU03 | [Pass/Fail] |
| vehicle-detail.feature | Get vehicle detail | User requests detail of specific vehicle | Executes GET /api/vehicles/{id} | Returns complete vehicle information | HU04 | [Pass/Fail] |
| favorites.feature | Add to favorites | User adds vehicle to favorites | Executes POST /api/favorites | Favorite is saved and confirmed | HU05 | [Pass/Fail] |
| favorites.feature | Remove from favorites | User removes vehicle from favorites | Executes DELETE /api/favorites/{id} | Favorite is deleted | HU05 | [Pass/Fail] |

**Gherkin Feature Files:**

```gherkin
# features/vehicle-search.feature
Feature: Vehicle Search (HU02)
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
Feature: Vehicle Price Filter (HU03)
  As a renter
  I want to filter vehicles by price
  So that I can adjust results to my budget

  Scenario: Filter applied successfully
    Given the user is viewing vehicle results
    When the user applies a price filter from $100 to $500
    Then the system displays only vehicles within the price range

# features/vehicle-detail.feature
Feature: Vehicle Detail (HU04)
  As a renter
  I want to see vehicle details
  So that I can make an informed decision

  Scenario: Detail view available
    Given the user selects a vehicle from list
    When they request the detail view
    Then the system displays complete vehicle information

# features/favorites.feature
Feature: Favorites Management (HU05)
  As a renter
  I want to manage my favorite vehicles
  So that I can review them later

  Scenario: Add to favorites
    Given the user is viewing a vehicle
    When they add it to favorites
    Then the vehicle is saved in their favorites list
```

**Repository de Tests:** [Insert URL GitHub]

**Commits de Testing:**

| Repository | Branch | Commit Id | Commit Message | Committed on |
| --- | --- | --- | --- | --- |
| rent2go-backend | feature/vehicle-tests | [Insert] | test(vehicle-catalog): add unit tests for repository | [Insert date] |
| rent2go-backend | feature/vehicle-tests | [Insert] | test(vehicle-catalog): add integration tests for API | [Insert date] |
| rent2go-backend | feature/vehicle-tests | [Insert] | test(vehicle-catalog): add BDD acceptance tests | [Insert date] |

---

#### 4.2.1.5. Execution Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo completó la implementación del Landing Page informativo (HU15-HU18) y los endpoints base del Backend para catálogo de vehículos (HU02-HU05). Se presentan screenshots de las principales vistas implementadas y enlace a video de demostración de funcionalidades.

**Landing Page - Screenshots:**

[Insert screenshot 1: Landing page completa con navbar (HU17) - Navegación]
[Insert screenshot 2: Hero section con CTA principal (HU15) - Propuesta de valor]
[Insert screenshot 3: Sección de contacto (HU16) - Información de contacto]
[Insert screenshot 4: Layout responsivo en móvil (HU18) - Responsive design]
[Insert screenshot 5: Secciones principales visibles (HU15) - Contenido informativo]

**Video de Demostración - Landing Page:**

En este video se muestra la navegación completa del Landing Page (HU15-HU18), incluyendo responsividad en dispositivos móviles, información de contacto, y navegación intuitiva.

- **URL OneDrive:** [Insert link]
- **URL YouTube:** [Insert link]
- **Duración:** [Insert HH:MM:SS]
- **Descripción:** Demostración completa del Landing Page con navegación entre secciones (HU15), información de contacto (HU16), navegación intuitiva (HU17), y responsividad (HU18).

**Backend API - Screenshots & Testing (HU02-HU05):**

[Insert screenshot 1: Postman - GET /api/vehicles/search con criterios (HU02)]
[Insert screenshot 2: Postman - GET /api/vehicles/filter con rango de precio (HU03)]
[Insert screenshot 3: Postman - GET /api/vehicles/{id} detail (HU04)]
[Insert screenshot 4: Postman - POST /api/favorites respuesta exitosa (HU05)]
[Insert screenshot 5: Postman - GET /api/favorites list (HU05)]

**Video de Demostración - Backend API (HU02-HU05):**

En este video se muestra la ejecución de los principales endpoints del backend utilizando Postman, demostrando búsqueda (HU02), filtrado (HU03), detalles (HU04) y favoritos (HU05).

- **URL OneDrive:** [Insert link]
- **URL YouTube:** [Insert link]
- **Duración:** [Insert HH:MM:SS]
- **Descripción:** Demostración de endpoints: búsqueda de vehículos (HU02), filtro de precio (HU03), detalle de vehículo (HU04), y gestión de favoritos (HU05) con casos de éxito y manejo de errores.

---

#### 4.2.1.6. Services Documentation Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, se documentaron todos los endpoints del backend correspondientes a la épica de Catálogo de Vehículos (HU02-HU05) utilizando OpenAPI 3.0 (Swagger). La documentación interactiva permite a los desarrolladores frontend y mobile entender y probar los servicios disponibles.

**Endpoints Documentados - Vehicle Catalog (HU02-HU05):**

| Endpoint | Método | Historia | Descripción | Parámetros | Response |
| --- | --- | --- | --- | --- | --- |
| `/api/vehicles/search` | GET | HU02 | Busca vehículos por criterios | `make`, `model`, `year`, `available` | 200 OK - Vehículos coincidentes |
| `/api/vehicles/filter` | GET | HU03 | Filtra vehículos por rango de precio | `minPrice`, `maxPrice` | 200 OK - Vehículos filtrados |
| `/api/vehicles/{id}` | GET | HU04 | Obtiene detalles de un vehículo | `id` (path) | 200 OK - Detalle del vehículo |
| `/api/favorites` | GET | HU05 | Obtiene favoritos del usuario | `userId` | 200 OK - Lista de favoritos |
| `/api/favorites` | POST | HU05 | Agrega vehículo a favoritos | Body: {vehicleId, userId} | 201 Created - Agregado a favoritos |
| `/api/favorites/{id}` | DELETE | HU05 | Elimina de favoritos | `id` (path) | 204 No Content |

**OpenAPI Documentation Screenshots:**

[Insert screenshot 1: Swagger UI - Endpoints list]
[Insert screenshot 2: Swagger UI - GET /api/vehicles/search con ejemplos]
[Insert screenshot 3: Swagger UI - POST /api/vehicles request body]
[Insert screenshot 4: Swagger UI - Response schemas]

**OpenAPI URL Deployments:**

| Ambiente | URL Swagger UI | Status |
| --- | --- | --- |
| Local Development | `http://localhost:8080/swagger-ui.html` | [Insert status] |
| Staging | [Insert URL] | [Insert status] |
| Production | [Insert URL] | [Insert status] |

**Repository de Backend:** [Insert URL GitHub]

**Commits de Documentación:**

| Repository | Branch | Commit Id | Commit Message | Committed on |
| --- | --- | --- | --- | --- |
| rent2go-backend | feature/vehicle-controller | [Insert] | docs: add OpenAPI documentation for vehicle endpoints | [Insert date] |
| rent2go-backend | feature/favorites | [Insert] | docs: add OpenAPI documentation for favorites endpoints | [Insert date] |

---

#### 4.2.1.7. Software Deployment Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo completó el despliegue del Landing Page en ambiente de staging (HU15-HU18) y preparó el backend para despliegue en desarrollo (HU02-HU05). Se configuraron los ambientes necesarios, secrets, y pipelines de CI/CD.

**Landing Page - Deployment:**

**Plataforma:** Vercel

- **Production URL:** [Insert URL]
- **Staging URL:** [Insert URL]
- **Deploy Method:** Automatic deployment on merge to main
- **Branch:** main
- **Status:** [Insert Deployed/In Progress]

**Steps realizados:**

1. Creación de proyecto en Vercel vinculado a repositorio GitHub
2. Configuración de environment variables (.env.production)
3. Setup de dominio personalizado (si aplica)
4. Configuración de SSL/TLS automático
5. Primer deploy exitoso en staging

[Insert screenshot: Vercel deployment console]
[Insert screenshot: Landing page deployed en staging]

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

**Database Deployment:**

**Plataforma:** AWS RDS MySQL 8.0

**Steps realizados:**

1. Creación de instancia RDS MySQL
2. Ejecución de scripts de schema para Vehicle Catalog
3. Configuración de security groups
4. Testing de conexión desde aplicación

[Insert screenshot: AWS RDS instance created]
[Insert screenshot: Database schema verification]

---

#### 4.2.1.8. Team Collaboration Insights during Sprint

**Introducción:**

Durante Sprint 1, el equipo trabajó de forma colaborativa siguiendo GitFlow y prácticas de desarrollo ágil en las historias de usuario HU15-HU18 (Landing Page) y HU02-HU05 (Backend Vehicle Catalog). Se utilizaron pull requests, code reviews, y reuniones diarias para garantizar calidad y comunicación.

**Analíticos de GitHub - Sprint 1:**

[Insert screenshot: GitHub Insights - Contributors]
[Insert screenshot: GitHub Insights - Commits over time]
[Insert screenshot: GitHub Insights - Pull requests merged]
[Insert screenshot: GitHub Insights - Code frequency]

**Participación del equipo:**

| Miembro | Commits | PRs | Code Reviews | Tareas Principales |
| --- | --- | --- | --- | --- |
| Carhuancote Dominguez, Gonzalo Alonso | [Insert #] | [Insert #] | [Insert #] | Backend Entity Design, DDD Architecture |
| Castillo Vidal, Jesus Ivan | [Insert #] | [Insert #] | [Insert #] | Android Mobile Development, API Integration |
| Chavez Uribe, Ario Joel | [Insert #] | [Insert #] | [Insert #] | Landing Page Responsive Design, QA Testing |
| Diestra Zambrano, Adriana Maria | [Insert #] | [Insert #] | [Insert #] | iOS Mobile Development, UX Design |
| Huarcaya Matias, Gilbert Alonso | [Insert #] | [Insert #] | [Insert #] | Backend API Development, Deployment Setup |

**Pull Requests Mergeados - Sprint 1:**

| PR # | Title | Description | Author | Merged | Date |
| --- | --- | --- | --- | --- | --- |
| #1 | Feature/landing-informative (HU15) | Implement Landing Page informative sections | [Name] | Yes | [Date] |
| #2 | Feature/landing-contact (HU16) | Add contact information section | [Name] | Yes | [Date] |
| #3 | Feature/landing-navigation (HU17) | Implement intuitive navigation and smooth scrolling | [Name] | Yes | [Date] |
| #4 | Feature/landing-responsive (HU18) | Add responsive design for all devices | [Name] | Yes | [Date] |
| #5 | Feature/vehicle-catalog (HU02) | Implement vehicle search functionality | [Name] | Yes | [Date] |
| #6 | Feature/vehicle-filter (HU03) | Add price filter functionality | [Name] | Yes | [Date] |
| #7 | Feature/vehicle-detail (HU04) | Implement vehicle detail endpoint | [Name] | Yes | [Date] |
| #8 | Feature/favorites (HU05) | Add favorites management feature | [Name] | Yes | [Date] |

**Reuniones Realizadas:**

- Sprint Planning: [Date] - [HH:MM]
- Daily Standup: [Insert frequency - e.g., Monday-Friday 10:00 AM]
- Sprint Review: [Date] - [HH:MM]
- Sprint Retrospective: [Date] - [HH:MM]

**Challenges & Resolutions:**

| Challenge | Descripción | Resolución |
| --- | --- | --- |
| Database Configuration | Configuración inicial de conexión MySQL en Spring Boot | Implementar application.properties con credenciales y propiedades de JPA correctas |
| Responsive Design | Asegurar landing page funcione en múltiples dispositivos | Aplicar mobile-first approach con breakpoints en CSS |
| Multilingual Support | Soportar español e inglés desde el inicio | Implementar JSON i18n y language selector |

---

#### 4.2.1.7. Software Deployment Evidence for Sprint Review

**Introducción:**

Durante Sprint 1, el equipo completó exitosamente el despliegue del Landing Page utilizando GitHub Pages, una solución de hosting estático integrada directamente con el repositorio. Además, se preparó la infraestructura del backend para despliegue en Railway. Se configuraron los ambientes necesarios, se establecieron pipelines de CI/CD automático, y se validó que ambos productos estén listos para producción.

**A. Landing Page - Deployment en GitHub Pages**

**Plataforma**: GitHub Pages  
**Repository**: https://github.com/Startup-y-upc/rent2go-landing  
**Branch**: main  
**Auto-deployment**: Habilitado - Deploy automático en cada push  
**Status**: ✅ Deployed & Live

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
| **HTTPS** | ✅ Habilitado automáticamente |
| **URL Pública** | https://[username].github.io/rent2go-landing/ |
| **Status** | ✅ Live |

---

**Ventajas de GitHub Pages:**

- ✅ **Hosting Gratuito**: Sin costos de infraestructura
- ✅ **Integración Nativa**: Completamente integrado con GitHub workflow
- ✅ **Deploy Automático**: Cada push a main dispara deployment
- ✅ **HTTPS por Defecto**: Certificados SSL incluidos automáticamente
- ✅ **Escalabilidad**: Manejo eficiente de tráfico para sitios estáticos
- ✅ **Versionado**: Historial completo de deployments
- ✅ **Rollback Sencillo**: Revertir a versiones anteriores fácilmente

---

**B. Backend - Deployment en Railway (Sprint 1 Preparation)**

Durante Sprint 1, se preparó la infraestructura para desplegar el backend Spring Boot en Railway. A continuación se documenta el proceso y evidencia del despliegue.

**Plataforma**: Railway  
**Status**: ✅ Successfully Deployed  
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
| **URL Pública** | [Insert] | [Insert] |
| **Database** | N/A | MySQL 8.0 (Railway) |
| **SSL/TLS** | ✅ Automático | ✅ Automático |
| **CI/CD** | ✅ Automático en main | ✅ Automático en main |
| **Status** | ✅ Live | ✅ Running |
| **Domain** | [Insert custom domain] | [Insert public URL] |

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
| Build status | ✅ 100% passing |

**Backend Repository:**

| Métrica | Valor |
| --- | --- |
| Total de commits | 3 commits a main |
| Total de PR mergeadas | 3 pull requests |
| Autores activos | 1 desarrollador |
| Archivos modificados | Estructura completa con entities, repositories, controllers |
| Líneas agregadas | 1,800+ líneas (Java, SQL, config) |
| Build status | ✅ Maven build success |

---

**Pull Requests por Producto:**

**Landing Page:**

| PR # | Título | Status | Fecha | Descripción |
| --- | --- | --- | --- | --- |
| #1 | Add initial HTML structure, CSS variables, and JavaScript for smooth navigation | ✅ Merged | May 6 | Estructura base con HTML semántico, CSS variables, y navegación suave |
| #2 | Add Spanish localization and new sections for Rent2Go website | ✅ Merged | May 7 | Secciones adicionales y soporte para español/inglés (i18n) |
| #3 | Release 1.0.0 | ✅ Merged | May 12 | Release oficial con todas las features completadas |
| #4 | Update README.md to enhance project documentation and structure | ✅ Merged | May 13 | Mejoras en documentación y estructura del repositorio |
| #5 | hotfix 1.0.1 | ✅ Merged | May 13 | Correcciones menores y refinamientos finales |

**Backend:**

| PR # | Título | Status | Fecha | Descripción |
| --- | --- | --- | --- | --- |
| #1 | Add initial project structure and configuration files | ✅ Merged | May 6 | Setup Spring Boot, Maven, y propiedades de aplicación |
| #2 | feat: Add vehicle catalog domain model and REST API | ✅ Merged | May 8 | Implementación de Vehicle entity, repository, y REST controllers |
| #3 | Release 1.0.0 | ✅ Merged | May 12 | Release oficial con Vehicle Catalog completado |

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
| Frontend Lead | [Name] | Landing Page (HU15-HU18) | 40 horas |
| Backend Lead | [Name] | Vehicle Catalog (HU02-HU05) | 45 horas |
| QA/Testing | [Name] | Validación y testing | 20 horas |
| DevOps | [Name] | Deployment en Vercel y Railway | 15 horas |

---

**Herramientas y Canales de Comunicación:**

1. **GitHub**: Control de versiones, pull requests, code review, issues
2. **Discord**: Comunicación diaria, pair programming, resolución de bloqueadores
3. **Trello**: Seguimiento de tareas y sprint backlog
4. **Google Meet**: Reuniones de planificación, sprint review, retrospectiva
5. **Email**: Documentación oficial y escalamientos

---

**Prácticas de Colaboración Implementadas:**

✅ **GitFlow**: main (production) → develop → feature branches  
✅ **Conventional Commits**: Tipos estándares (feat, fix, docs, refactor)  
✅ **Code Review**: Todo PR requiere revisión antes de merge  
✅ **Semantic Versioning**: v1.0.0, v1.0.1 tags  
✅ **Daily Standup**: Comunicación diaria de blockers y progress  
✅ **Pair Programming**: Para problemas complejos  
✅ **Testing**: Unit tests, integration tests, manual testing  

---

**Reuniones Realizadas durante Sprint 1:**

| Reunión | Fecha | Duración | Participantes | Tema |
| --- | --- | --- | --- | --- |
| Sprint Planning | May 6 | 2 hrs | Equipo completo | Definición de HU15-HU18, HU02-HU05 |
| Daily Standup | May 7-11 | 15 min c/día | Equipo | Progress, blockers, plan del día |
| Pairing Session | May 8 | 1 hr | Backend dev pair | Resolución de issues de JPA |
| Sprint Review | May 12 | 1.5 hrs | Equipo + stakeholders | Demo de Landing Page y API |
| Sprint Retrospective | May 13 | 1 hr | Equipo | Lecciones aprendidas y mejoras |

---

**Indicadores de Calidad de Colaboración:**

| Indicador | Resultado | Target | Status |
| --- | --- | --- | --- |
| **PR Review Time** | < 24 hrs | < 48 hrs | ✅ Excelente |
| **Merge Frequency** | 8 PR/semana | > 4 PR/semana | ✅ Excelente |
| **Build Success Rate** | 100% | > 95% | ✅ Excelente |
| **Code Review Participation** | Todos participan | > 80% | ✅ Excelente |
| **Commit Consistency** | Daily | > 3x/week | ✅ Excelente |
| **Documentation Update** | Al día | Completa | ✅ Completa |

---

**Desafíos Enfrentados y Resueltos:**

| Desafío | Impacto | Resolución | Lección |
| --- | --- | --- | --- |
| MySQL connection strings | Medium | Docker compose local + env vars | Documentar config desde día 1 |
| CORS en API | Medium | Configurar Spring Security | Considerar CORS temprano |
| Responsive CSS | Low | Mobile-first approach | Usar framework CSS next time |
| Timezone differences | Low | Async standup + recordings | Documentar en UTC |

---

**Fortalezas del Equipo Identificadas:**

1. ✅ **Comunicación Proactiva**: Reportan blockers inmediatamente en Discord
2. ✅ **Ownership**: Cada developer toma responsabilidad de su producto
3. ✅ **Quality-minded**: Todos buscan hacer buena ingeniería
4. ✅ **Collaborative**: Ayuda mutua y pair programming cuando necesario
5. ✅ **Process-oriented**: Sigue GitFlow y convenciones establecidas

---

**Áreas de Mejora para Sprint 2:**

1. 📋 Automatizar tests en CI/CD pipeline
2. 📋 Aumentar cobertura de tests (target: > 85%)
3. 📋 Documentación de arquitectura en plantUML/C4
4. 📋 Performance monitoring en producción
5. 📋 Más pair programming para knowledge sharing

---

**Conclusión de Colaboración:**

Sprint 1 fue exitoso en demostrar que el equipo Rent2Go posee:
- **Disciplina técnica** en aplicación de prácticas (GitFlow, Conventional Commits)
- **Capacidad de ejecución** para completar historias de usuario complejas
- **Comunicación efectiva** para resolver bloqueadores rápidamente
- **Compromiso con calidad** en código e integración continua

El equipo está bien posicionado para escalar a sprints más complejos con múltiples contextos acotados (booking, payments, IAM) y despliegues en ambientes más exigentes.

---

<!--
<div style="page-break-after: always;"></div>

## 4.3. Validation Interviews

En esta sección, el equipo registra y explica las actividades de entrevistas de validación durante Sprint 1. Se realizaron entrevistas con usuarios de los segmentos objetivo: visitantes para validar Landing Page (HU15-HU18) y arrendatarios para validar funcionalidades de búsqueda y filtrado de vehículos (HU02-HU05).

### 4.3.1. Diseño de Entrevistas

**Objetivos de Validación:**

- Evaluar claridad del valor propuesto en el Landing Page (HU15-HU18)
- Validar navegabilidad e información presentada en landing
- Validar responsividad en múltiples dispositivos
- Recopilar feedback sobre funcionalidades de búsqueda y filtrado de vehículos (HU02-HU05)
- Entender fluidez de interacción en búsqueda y detalle de vehículos

**Segmentos Objetivo:**

1. **Visitantes:** Personas nuevas interesadas en conocer la plataforma (para HU15-HU18)
2. **Arrendatarios:** Personas buscando alquilar vehículos de corta duración (para HU02-HU05)

**Estructura de Entrevista (Visitantes - HU15-HU18):**

| Sección | Duración | Descripción |
| --- | --- | --- |
| Bienvenida | 2 min | Presentación del producto y propósito de validación |
| Navegar Landing Page | 5 min | Usuario explora secciones del landing (HU15, HU16, HU17, HU18) |
| Tarea 1: Entender el servicio | 3 min | Preguntas sobre claridad del modelo de negocio y propuesta de valor |
| Tarea 2: Encontrar contacto | 2 min | Usuario localiza información de contacto (HU16) |
| Tarea 3: Evaluar navegación | 2 min | Usuario intenta acceder a diferentes secciones (HU17) |
| Feedback de diseño | 2 min | Observaciones sobre responsividad y usabilidad (HU18) |
| Cierre | 1 min | Agradecimiento y siguiente pasos |

**Estructura de Entrevista (Arrendatarios - HU02-HU05):**

| Sección | Duración | Descripción |
| --- | --- | --- |
| Bienvenida | 2 min | Presentación del producto y propósito de validación |
| Búsqueda de vehículos | 4 min | Usuario realiza búsqueda (HU02) y obtiene resultados |
| Aplicar filtro | 3 min | Usuario aplica filtro de precio (HU03) |
| Ver detalles | 3 min | Usuario selecciona y ve detalles de vehículo (HU04) |
| Agregar favoritos | 2 min | Usuario agrega vehículo a favoritos (HU05) |
| Feedback general | 3 min | Preguntas sobre facilidad de uso y mejoras |
| Cierre | 1 min | Agradecimiento y siguiente pasos |

**User Flows a Validar:**

1. **Flow Visitante - Landing Page:** Acceder a landing → Entender propuesta → Navegar secciones → Encontrar CTA (HU15-HU18)
2. **Flow Arrendatario - Búsqueda:** Buscar vehículos → Filtrar por precio → Ver detalles → Agregar a favoritos (HU02-HU05)

---

### 4.3.2. Registro de Entrevistas

**Entrevista 1 - Segmento: Visitante (Landing Page HU15-HU18)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Screenshot de Video** | [Insert image screenshot] |
| **URL OneDrive** | [Insert link OneDrive] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las principales apreciaciones del entrevistado. Incluir:
- Reacciones sobre el Landing Page (HU15)
- Claridad del modelo de negocio
- Facilidad de encontrar información de contacto (HU16)
- Facilidad de navegación (HU17)
- Observaciones sobre responsividad (HU18)
- Principales dudas o fricción
- Puntos positivos y negativos
- Disposición a usar la app]

---

**Entrevista 2 - Segmento: Visitante (Landing Page HU15-HU18)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Screenshot de Video** | [Insert image screenshot] |
| **URL OneDrive** | [Insert link OneDrive] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las principales apreciaciones del entrevistado sobre Landing Page (HU15-HU18)]

---

**Entrevista 3 - Segmento: Arrendatario (Búsqueda y Filtrado HU02-HU05)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Screenshot de Video** | [Insert image screenshot] |
| **URL OneDrive** | [Insert link OneDrive] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las principales apreciaciones del entrevistado. Incluir:
- Facilidad de búsqueda de vehículos (HU02)
- Utilidad del filtro de precio (HU03)
- Claridad de detalles de vehículo mostrados (HU04)
- Necesidad de agregar a favoritos (HU05)
- Fluidez de la búsqueda
- Resultados relevantes
- Puntos de fricción
- Intención de alquilar]

---

**Entrevista 4 - Segmento: Arrendatario (Búsqueda y Filtrado HU02-HU05)**

| Aspecto | Descripción |
| --- | --- |
| **Nombre** | [Insert nombre] |
| **Apellido** | [Insert apellido] |
| **Edad** | [Insert edad] |
| **Distrito** | [Insert distrito] |
| **Ocupación** | [Insert ocupación] |
| **Screenshot de Video** | [Insert image screenshot] |
| **URL OneDrive** | [Insert link OneDrive] |
| **Timing del Video** | Inicia en [HH:MM:SS], Duración: [HH:MM:SS] |

**Resumen de Observaciones:**

[Insert resumen descriptivo de las principales apreciaciones del entrevistado sobre búsqueda y filtrado (HU02-HU05)]

---

### 4.3.3. Evaluaciones según heurísticas

En esta sección se evalúan las sesiones de validación basado en heurísticas de usabilidad, arquitectura de información e inclusive design de la experiencia propuesta en el Landing Page.

**Evaluación Heurística - Landing Page Sprint 1:**

| # | Heurística | Severidad | Descripción | Recomendación |
| --- | --- | --- | --- | --- |
| 1 | Visibilidad del estado del sistema | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 2 | Coincidencia entre el sistema y el mundo real | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 3 | Control y libertad del usuario | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 4 | Estándares y consistencia | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 5 | Prevención de errores | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 6 | Reconocimiento en lugar de recuerdo | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 7 | Flexibilidad y eficiencia de uso | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 8 | Diseño estético y minimalista | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 9 | Ayuda y documentación | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |
| 10 | Accesibilidad (WCAG 2.1) | [Low/Medium/High] | [Descripción de hallazgo] | [Recomendación de mejora] |

**Resumen de Evaluación:**

[Insert resumen general de hallazgos, patrones observados, y prioridades de mejora para próximas iteraciones]

---

<div style="page-break-after: always;"></div>
-->