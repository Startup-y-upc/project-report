# Capítulo III: Solution UI/UX Design

## 3.1 Product design

En esta sección se presenta el diseño del producto como una parte integral de la arquitectura del sistema, enfocándose en los aspectos clave que determinan su estructura y funcionalidad. El diseño del producto abarca tanto los componentes físicos como el software, asegurando que cada parte esté alineada con los requisitos y objetivos definidos en las etapas previas del proyecto. Se detallan las decisiones clave que influencian la interacción entre los usuarios y el sistema, las funcionalidades principales del producto y las tecnologías utilizadas para su implementación.

### 3.1.1 Style Guidelines

El equipo utiliza un repositorio centralizado de assets y tokens de diseño para mantener coherencia visual entre Landing Page, Web App y Mobile App. Este Design System de referencia contiene: paleta de colores, tipografías, escalas de espaciado, iconografía, estilos de botones, formularios y componentes reutilizables.

#### 3.1.1.1 General Style Guidelines

- Branding: lenguaje visual cercano y confiable que inspire seguridad y accesibilidad. Tono: semi-formal, cercano y claro.
- Typography: sistema escalado con variables CSS: --font-base (inter/roboto), --font-headline, --font-body. Escalas typográficas: H1 (32px), H2 (24px), H3 (20px), body (16px), small (14px).
- Colors: tokens primarios, secundarios y neutrales. Ejemplo:
  - --color-primary: #0D6EFD
  - --color-accent: #FF7A59
  - --color-success: #28A745
  - neutrals: --gray-100 ... --gray-900
- Spacing: base 8px modular (8, 16, 24, 32). Contenedores responsivos con breakpoints: 360px, 768px, 1024px, 1440px.
- Tone & Voice: comunicación clara, breve y orientada a la acción. Preferir frases cortas y verbos en imperativo suave para CTAs.

> Principios: accesibilidad (AA), lectura rápida, consistencia y economía visual.

### 3.1.2 Information Architecture

Se documentan las decisiones que rigen la organización del contenido en experiencias web y móvil, con el objetivo de que usuarios encuentren lo que necesitan sin esfuerzo.

#### 3.1.2.1 Organization Systems

Decisiones:
- Jerárquica (visual hierarchy): para pantallas de producto y ficha de vehículo; uso de tamaño, contraste y agrupación para priorizar información.
- Secuencial (step-by-step): para procesos como registro, verificación de usuario y reserva.
- Matricial: para listados y filtros (por tipo de vehículo, precio, ubicación).

Esquemas de categorización:
- Alfabetico: listas de marcas cuando aplique.
- Cronológico: historial de reservas y transacciones.
- Por tópicos: filtros por características (transmisión, asientos, combustible).
- Según audiencia: vistas diferenciadas para Propietario y Arrendatario.

#### 3.1.2.2 Labelling Systems

Reglas:
- Etiquetas cortas (1–3 palabras) y consistentes: "Buscar", "Reservar", "Mi perfil", "Mis vehículos".
- Botones de acción: verbo principal + complemento opcional (ej. "Reservar ahora").
- Evitar tecnicismos en UI, priorizar claridad y correspondencia semántica entre etiqueta y destino.

Ejemplos de etiquetas clave:
- Header: Inicio | Buscar vehículos | Mis reservas | Soporte
- Ficha vehículo: Marca | Modelo | Precio/Día | Disponibilidad

#### 3.1.2.3 SEO Tags and Meta Tags

Recomendaciones para Landing Page y páginas públicas:
- Title: Rent2Go – Alquila y monetiza vehículos fácilmente
- Meta Description: Plataforma P2P para alquilar vehículos en minutos. Propietarios monetizan; arrendatarios encuentran autos accesibles y seguros.
- Meta Keywords: alquiler vehículos, carsharing, rent2go, alquiler por horas, P2P vehículos
- Author: R2G Technologies

ASO (App Store Optimization) para aplicaciones móviles:
- App Title: Rent2Go – Alquiler de vehículos
- App Subtitle: Reserva autos cerca de ti
- App Keywords: alquiler, auto, coche, rent, carshare, vehículo
- App Description (breve): Reserva vehículos de particulares y gana dinero como propietario. Seguro integrado y proceso rápido.

#### 3.1.2.4 Searching Systems

Opciones de búsqueda:
- Barra principal con búsqueda por ubicación y palabras clave.
- Filtros: rango de precio, tipo de vehículo, transmisión, capacidad, distancia, calificación.
- Ordenamiento: relevancia, precio asc/desc, cercanía, más reservados.

Resultados:
- Tarjetas estándar con imagen, título, etiqueta de precio, rating y CTA.
- Paginación o scroll infinito con indicador de carga y estado "sin resultados" con sugerencias (expandir radio, quitar filtros).

#### 3.1.2.5 Navigation Systems

Estrategia:
- Desktop: header con navegación primaria, CTA de alto contraste, footer con enlaces secundarios.
- Mobile: bottom navigation (4 tabs) para acciones principales: Inicio, Buscar, Reservas, Perfil. Menu hamburguesa para enlaces secundarios.
- Breadcrumbs en rutas profundas (detalle vehículo > pasos de reserva).

### 3.1.3 Landing Page UI Design

Introducción: la Landing Page comunica propuesta de valor, genera confianza e impulsa registros y descargas. Traduce las decisiones de diseño y arquitectura de información en una experiencia pública clara.

#### 3.1.3.1 Landing Page Wireframe

Wireframes incluidos (placeholder):
- Desktop: Hero con CTA principal, secciones Features, How it Works, Testimonios, FAQ, Footer.
- Mobile: versión adaptada con hero condensado, CTA fijo y secciones apiladas verticalmente.

Evidencia: añadir imágenes en `project-report/Resources/capitulo_3/landing_wireframes/` con archivos `desktop.png` y `mobile.png`.

#### 3.1.3.2 Landing Page Mock-up

Mock-ups (placeholder): usar assets en `project-report/Resources/capitulo_3/landing_mockups/` y describir la aplicación del Design System: colores, tipografías, espaciado y accesibilidad.

### 3.1.4 Mobile Applications UX/UI Design

Propuesta visual e interacción para las aplicaciones móviles. La UI móvil sigue el mismo Design System del landing para mantener sincronía en la experiencia.

#### 3.1.4.1 Mobile Applications Wireframes

Wireframes por pantallas clave:
- Onboarding/Registro
- Home / Búsqueda con filtros
- Ficha vehículo
- Reserva (checkout)
- Perfil de usuario y panel de propietario

Guardar wireframes en `project-report/Resources/capitulo_3/mobile_wireframes/`.

#### 3.1.4.2 Mobile Applications Wireflow Diagrams

Wireflows por User Goal (placeholders):
- Goal: Reservar vehículo rápido
  - Task Flow: Buscar > Filtrar > Ver ficha > Reservar > Confirmación
  - Crear wireflow diagram y guardar en `project-report/Resources/capitulo_3/mobile_wireflows/`.

Cada wireflow debe incluir: User goal, persona objetivo, pasos y estados de pantalla.

#### 3.1.4.3 Mobile Applications Mock-ups

Mock-ups en alta fidelidad usando los tokens del Design System. Guardar en `project-report/Resources/capitulo_3/mobile_mockups/`.

#### 3.1.4.4 Mobile Applications User Flow Diagrams

User Flows que incluyan happy path y unhappy paths (errores, verificación fallida). Documentar condiciones y mensajes de error.

#### 3.1.4.5 Mobile Applications Prototyping

Prototipos interactivos (link / screenshot): incluir al menos 1 captura y un enlace a video demostrativo en Microsoft Stream por prototipo. Guardar capturas en `project-report/Resources/capitulo_3/prototypes/`.

---

## 3.2 Design System — Configuración base (referencia del Landing Page)

Esta sección incluye el archivo de referencia para tokens y componentes que deben usarse en Web App y Mobile App para mantener sincronía.

- Fonts: `Inter` para UI, `Roboto` fallback.
- Color tokens: primario, secundario, neutrales, estados (success, error, warning).
- Spacing: base 8px.
- Component primitives: Button, Input, Card, Tag, Avatar, Badge.

Nota técnica: el Landing Page purista (HTML/CSS/JS) ubicado en `/landing-page` incluirá un `style.css` con las variables CSS del Design System. Las aplicaciones web y móviles deben mapear estos tokens a sus sistemas (CSS vars / theme tokens / design tokens JSON).

Design tokens de referencia: [landing-page/design-tokens.json](landing-page/design-tokens.json)

## 3.3 Assets y Evidencias

Estructura recomendada dentro de `project-report/Resources/capitulo_3/`:
- landing_wireframes/
- landing_mockups/
- mobile_wireframes/
- mobile_mockups/
- mobile_wireflows/
- prototypes/

En cada carpeta incluir un README con la lista de archivos y descripciones.

## 3.4 Siguientes pasos y tareas

1. Generar wireframes en baja fidelidad y exportar PNG (ponerlos en `landing_wireframes` y `mobile_wireframes`).
2. Crear mock-ups en Figma/Sketch o como archivos estáticos y guardar en `landing_mockups` y `mobile_mockups`.
3. Implementar el Landing Page en HTML/CSS/JS en la carpeta `/landing-page` (tarea scaffoldeada en este repositorio).

---

_Este documento es la base para el Capítulo III. Contiene plantillas, placeholders y la configuración inicial del Design System que servirán como referencia para el desarrollo front-end y mobile._
