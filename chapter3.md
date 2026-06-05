# Capítulo III: Solution UI/UX Design

## 3.1 Product design

Este capítulo se alinea con lo implementado en la carpeta landing-page. Se documenta el diseño visual, los componentes y la arquitectura de información existentes, manteniendo el enfoque mobile-first solicitado por la guía del curso.

### 3.1.1 Style Guidelines

La Landing Page implementada se apoya en la estructura Vue de landing-page-samples/landing-page-main, con estilos efectivos en src/style.css e index.html. Esta sección registra la implementación visual real para trazabilidad.

#### 3.1.1.1 General Style Guidelines

- Branding y tono: comunicación directa, confiable y orientada a acción con CTAs como Reservar ahora y Explorar vehículos.
- Tipografía aplicada en la implementación real: Poppins como familia base con fallback system-ui, Segoe UI, Roboto y Arial.
- Escala tipográfica efectiva: títulos grandes, encabezados medios y texto base definidos con clases heading-xl, heading-lg, heading-md, heading-sm y body.
- Colores base confirmados: paleta primary con variantes primary-50, primary-100, primary-500 y primary-600, neutros grises y superficies dark.
- Variables y utilidades adicionales implementadas para estados y superficies: fondos claros, fondos dark, bordes, sombras y footer.
- Espaciado y layout aplicado: base de 8px, contenedores max-w-7xl y padding horizontal 16px en mobile y 24px en desktop.
- Breakpoints configurados en Tailwind y usados en la UI: 640px, 768px y 1024px.
- Breakpoints implementados en CSS: 1024px, 768px y 640px, con ajustes de grid, tipografía y layout.
- Soporte visual adicional implementado: modo oscuro por clase dark en html, activado desde el toggle de tema y aplicado al conjunto de la interfaz.

Componentes UI implementados en Landing:

- Botón primario: fondo #0D6EFD, texto blanco, radio 8px, hover en #0854d4.
- Botón outline: borde de 1px, fondo transparente, hover con fondo gris claro.
- Botón ícono: usado para cambio de tema y menú móvil.
- Tarjetas: fondo de tarjeta, borde suave, radio 16px y elevación en hover.
- Formularios: campos con borde gris y foco con anillo visual primary-50.
- Chips de categoría y tags de atributos para flota.

### 3.1.2 Information Architecture

La arquitectura de información se documenta desde la estructura real de la página implementada en index.html, sections y app.js.

#### 3.1.2.1 Organization Systems

Sistema jerárquico y secuencial implementado por bloques anclados:

1. Header
2. Hero
3. Features
4. Fleet
5. How it works
6. Requirements
7. Testimonials
8. FAQ
9. CTA / Contacto
10. Footer

Organización funcional observada:

- Sección Hero para propuesta de valor y CTAs.
- Secciones intermedias para confianza y evaluación (features, flota, requisitos, testimonios, FAQ).
- Sección CTA/Contacto para conversión mediante información de soporte y formulario de solicitud.

#### 3.1.2.2 Labelling Systems

Etiquetas reales de navegación principal:

- Inicio
- Vehículos
- ¿Cómo funciona?
- Requisitos
- Preguntas
- Contacto

Etiquetas de acción reales:

- Iniciar sesión
- Reservar ahora
- Explorar vehículos
- ¿Cómo funciona?
- Solicitar reserva

Se mantiene consistencia bilingüe usando claves data-i18n y catálogos en es_419.json y en_US.json.

#### 3.1.2.3 SEO Tags and Meta Tags

Implementado en index.html:

- Title: Rent2Go – Alquila y monetiza vehículos
- Meta description: Rent2Go — Alquila y monetiza vehículos fácilmente

Pendiente para completar guía de curso:

- [PENDIENTE: agregar meta keywords si la guía lo exige].
- [PENDIENTE: agregar meta author si la guía lo exige].
- [PENDIENTE: agregar Open Graph y Twitter Cards para evidencia SEO social].
- [PENDIENTE: evidencia de validación SEO en capturas o reporte de auditoría].

ASO para aplicaciones móviles:

- [PENDIENTE: no existe material ASO en el repositorio actual].

#### 3.1.2.4 Searching Systems

Estado real implementado:

- No hay barra de búsqueda por texto en la Landing.
- Sí existe filtrado por categorías de flota: Todos, Económicos, SUVs, Lujo y Vans.
- El grid de vehículos se actualiza dinámicamente al seleccionar categoría.

Pendiente para alineación futura si la guía exige búsqueda completa:

- [PENDIENTE: definir búsqueda por texto, ubicación y ordenamientos].
- [PENDIENTE: evidencia de estados sin resultados].

#### 3.1.2.5 Navigation Systems

Navegación implementada:

- Desktop: menú horizontal con enlaces ancla internos a secciones.
- Mobile: botón de menú hamburguesa y menú colapsable con aria-hidden.
- CTA persistente en header con botones Iniciar sesión y Reservar ahora.
- Selector de idioma con preferencia visual declarada en la navegación.
- Toggle de tema claro/oscuro que alterna la clase dark en html.

No implementado actualmente:

- Breadcrumbs.
- Bottom navigation tipo aplicación móvil.

### 3.1.3 Landing Page UI Design

La UI implementada corresponde a una landing de una sola página con secciones modulares, renderizado dinámico de contenido y soporte bilingüe.

#### 3.1.3.1 Landing Page Wireframe

Referencia estructural derivada de implementación actual:

- Header con branding, menú principal, selector de idioma, toggle de tema y CTAs.
- Hero con imagen de fondo, título, subtítulo, doble CTA y métricas.
- Bloques de contenido tipo card para features, pasos, requisitos, testimonios y FAQ.
- Catálogo de flota con filtros por categoría.
- Sección CTA/Contacto con información de contacto, imagen de fondo y formulario de reserva.
- Footer en cuatro columnas con enlaces de navegación secundaria.

Evidencia pendiente:

- [PENDIENTE: wireframe desktop en project-report/Resources/capitulo_3/landing_wireframes/desktop.png].
- [PENDIENTE: wireframe mobile en project-report/Resources/capitulo_3/landing_wireframes/mobile.png].

#### 3.1.3.2 Landing Page Mock-up

Estado actual:

- Existe implementación visual funcional en HTML/CSS/JS.
- No se encontró archivo de mock-up editable (Figma, Sketch u otro) dentro del repositorio.

Evidencia pendiente:

- [PENDIENTE: mock-up desktop en project-report/Resources/capitulo_3/landing_mockups/].
- [PENDIENTE: mock-up mobile en project-report/Resources/capitulo_3/landing_mockups/].
- [PENDIENTE: registro de decisiones visuales comparando mock-up vs implementación].

### 3.1.4 Mobile Applications UX/UI Design

Se mantiene el alcance mobile-first en el reporte, pero esta sección queda como evidencia pendiente porque no hay entregables UX/UI móviles dentro de la carpeta mobile en el estado actual del repositorio.

#### 3.1.4.1 Mobile Applications Wireframes

- [PENDIENTE: wireframes de onboarding, home, detalle de vehículo, checkout y perfil].
- [PENDIENTE: guardar evidencia en project-report/Resources/capitulo_3/mobile_wireframes/].

#### 3.1.4.2 Mobile Applications Wireflow Diagrams

- [PENDIENTE: wireflow principal Reservar vehículo rápido].
- [PENDIENTE: guardar evidencia en project-report/Resources/capitulo_3/mobile_wireflows/].

#### 3.1.4.3 Mobile Applications Mock-ups

- [PENDIENTE: mock-ups de alta fidelidad de pantallas móviles].
- [PENDIENTE: guardar evidencia en project-report/Resources/capitulo_3/mobile_mockups/].

#### 3.1.4.4 Mobile Applications User Flow Diagrams

- [PENDIENTE: user flows happy path y unhappy paths].
- [PENDIENTE: incluir flujos de error y mensajes de validación].

#### 3.1.4.5 Mobile Applications Prototyping

- [PENDIENTE: prototipo navegable y evidencia en video].
- [PENDIENTE: capturas en project-report/Resources/capitulo_3/prototypes/].

---

## 3.2 Design System - Configuración base (alineado al Landing implementado)

Fuentes reales verificadas:

- landing-page-samples/landing-page-main/index.html
- landing-page-samples/landing-page-main/src/style.css
- landing-page-samples/landing-page-main/src/App.vue
- landing-page-samples/landing-page-main/src/components/*.vue

Definiciones clave registradas:

- Tipografía base Poppins declarada en index.html y aplicada desde src/style.css.
- Variables visuales extendidas y tema oscuro en src/style.css.
- Componentes de UI organizados por Vue en src/components y ensamblados desde App.vue.
- Navegación, CTA y toggle de tema definidos en componentes reutilizables.

Nota de consistencia:

- La guía de diseño debe considerar como fuente de verdad visual el CSS efectivo (src/style.css).
- La implementación actual no depende de un archivo separado de design tokens en esta muestra.

## 3.3 Assets y Evidencias

Evidencia existente verificable en repositorio:

- Implementación de estructura y contenido en landing-page-samples/landing-page-main/index.html.
- Estilos efectivos en landing-page-samples/landing-page-main/src/style.css.
- Ensamblado de secciones y toggle de tema en landing-page-samples/landing-page-main/src/App.vue.
- Componentes de navegación, hero, features, flota, how-it-works, requirements, testimonials, FAQ, CTA y footer en landing-page-samples/landing-page-main/src/components/.

Evidencia pendiente para completar capítulo según guía:

- [PENDIENTE: capturas de pantalla desktop/mobile del landing en ejecución].
- [PENDIENTE: wireframes y mock-ups documentados en Resources/capitulo_3].
- [PENDIENTE: evidencia de evaluación de accesibilidad y contraste].
- [PENDIENTE: evidencia de pruebas responsive por breakpoint].
- [PENDIENTE: evidencia de licencias/fuentes de imágenes externas usadas en hero y contacto].

## 3.4 Siguientes pasos y tareas

1. Adjuntar evidencia visual del estado actual del Landing (desktop y mobile) en project-report/Resources/capitulo_3.
2. Registrar wireframes y mock-ups faltantes como evidencia de diseño, manteniendo la estructura de carpetas ya definida.
3. Completar metadatos SEO/OG solo si la guía del curso los exige explícitamente y anexar evidencia.
4. Incorporar en este capítulo las evidencias de UX/UI móvil cuando el equipo las genere en la carpeta mobile.

---

Este documento queda alineado con lo realmente implementado en la Landing Page y mantiene placeholders explícitos para toda evidencia aún no disponible.
