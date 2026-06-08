# Diagnóstico General del Informe de Trabajo Final

Este documento presenta un análisis automático de calidad del informe, identificando secciones vacías, placeholders de contenido o imágenes, duplicaciones de cabeceras, enlaces rotos en la Tabla de Contenidos y cumplimiento de las normas de formato (saltos de página).

## 1. Resumen de Calidad por Archivo
| Archivo | Cabeceras | Placeholders/Vacíos | Cabeceras Duplicadas | Errores de Formato (Salto Pág.) |
| :--- | :---: | :---: | :---: | :---: |
| README.md | 15 | 0 | 0 | 0 |
| Capitulo_1.md | 16 | 0 | 0 | 0 |
| Capitulo_2.md | 100 | 8 | 7 | 0 |
| Capitulo_3.md | 42 | 9 | 0 | 0 |
| Capitulo_4.md | 25 | 0 | 0 | 4 |
| Conclusiones.md | 8 | 3 | 0 | 0 |

---

## 2. Enlaces Rotos o Desalineados en la Tabla de Contenidos (README.md)
¡Perfecto! No se encontraron enlaces rotos en la Tabla de Contenidos.

---

## 3. Diagnóstico Detallado de Contenidos Vacíos y Placeholders
### [ README.md ]
#### Placeholders o Textos Pendientes:
*No se encontraron placeholders de texto o imágenes.*
#### Cabeceras Vacías o sin Contenido:
- **Línea 78** (Nivel 2): `### Project Report Collaboration Insights`
- **Línea 98** (Nivel 1): `### Tabla de contenidos`
- **Línea 100** (Nivel 2): `### [Student Outcome (ver anexo A)](#student-outcome)`
- **Línea 102** (Nivel 2): `### [Objetivos SMART](#objetivos-smart)`
- **Línea 246** (Nivel 2): `### [Bibliografía](Conclusiones.md#bibliografía)`
- **Línea 248** (Nivel 2): `### [Anexos](Conclusiones.md#anexos)`
#### Cabeceras Duplicadas:
*No se detectaron cabeceras duplicadas.*
#### Errores de Formato (Saltos de Página faltantes en cabeceras `#`):
*Todas las cabeceras `#` de este archivo tienen salto de página correcto.*


### [ Capitulo_1.md ]
#### Placeholders o Textos Pendientes:
*No se encontraron placeholders de texto o imágenes.*
#### Cabeceras Vacías o sin Contenido:
- **Línea 3** (Nivel 1): `### Capítulo I: Introducción`
- **Línea 5** (Nivel 2): `### 1.1. StartUp Profile`
- **Línea 29** (Nivel 2): `### 1.2. Solution Profile`
- **Línea 53** (Nivel 3): `### 1.2.2. Lean UX Process`
- **Línea 223** (Nivel 2): `### 1.3. Segmentos Objetivo`
#### Cabeceras Duplicadas:
*No se detectaron cabeceras duplicadas.*
#### Errores de Formato (Saltos de Página faltantes en cabeceras `#`):
*Todas las cabeceras `#` de este archivo tienen salto de página correcto.*


### [ Capitulo_2.md ]
#### Placeholders o Textos Pendientes:
- **Línea 1152**: `<td colspan="4">**AC1:** Given que el usuario ha enviado información de verificación, When consulta su perfil, Then el sistema muestra el estado actual de la verificación. <br> **AC2:** Given que falta información de verificación, When el usuario consulta su estado, Then el sistema indica qué requisitos están pendientes.</td>`
- **Línea 1710**: `<td colspan="4">**AC1:** Given que el arrendatario tiene una reserva en proceso, When revisa los datos, Then el sistema muestra vehículo, fechas, lugar y condiciones de la reserva. <br> **AC2:** Given que la reserva tiene datos incompletos, When el arrendatario intenta continuar, Then el sistema solicita completar la información pendiente.</td>`
- **Línea 1977**: `<td colspan="3">Ver solicitudes de reserva pendientes</td>`
- **Línea 1983**: `<td colspan="4">Como propietario, quiero ver solicitudes de reserva pendientes para decidir si acepto o rechazo el alquiler.</td>`
- **Línea 1989**: `<td colspan="4">**AC1:** Given que existen solicitudes pendientes para sus vehículos, When el propietario las consulta, Then el sistema muestra las solicitudes disponibles. <br> **AC2:** Given que no existen solicitudes pendientes, When el propietario realiza la consulta, Then el sistema informa que no hay solicitudes por revisar.</td>`
- **Línea 2020**: `<td colspan="4">**AC1:** Given que existe una solicitud pendiente, When el propietario la acepta, Then el sistema actualiza la reserva como aceptada. <br> **AC2:** Given que existe una solicitud pendiente, When el propietario la rechaza, Then el sistema actualiza la reserva como rechazada.</td>`
- **Línea 2764**: `<td colspan="4">**AC1:** Given que el cliente envía un archivo permitido, When el API procesa la carga, Then registra el documento como recibido. <br> **AC2:** Given que el cliente envía un archivo no permitido, When el API procesa la carga, Then responde con un error de formato. <br> **AC3:** Given que un usuario consulta su estado de verificación, When el API procesa la solicitud, Then responde con los documentos registrados y pendientes.</td>`
- **Línea 3361**: `|      49 | US34          | Ver solicitudes de reserva pendientes                   |            5 |`
#### Cabeceras Vacías o sin Contenido:
- **Línea 3** (Nivel 1): `### Capítulo II: Requirements Development and Software Solution Design`
- **Línea 274** (Nivel 2): `### 2.2. Entrevistas`
- **Línea 497** (Nivel 5): `### Análisis estadístico`
- **Línea 570** (Nivel 5): `### Análisis estadístico`
- **Línea 631** (Nivel 2): `### 2.3. Needfinding`
- **Línea 703** (Nivel 3): `### 2.3.5. Big Picture EventStorming`
- **Línea 716** (Nivel 2): `### 2.4. Requirements specification`
- **Línea 3295** (Nivel 3): `### 2.4.2. Impact Mapping`
- **Línea 3391** (Nivel 2): `### 2.5. Strategic-Level Domain-Driven Design`
- **Línea 3393** (Nivel 3): `### 2.5.1. EventStorming`
#### Cabeceras Duplicadas:
- `Características objetivas del segmento` aparece en las líneas: 483, 557
- `Análisis estadístico` aparece en las líneas: 497, 570
- `Experiencia previa alquilando vehículos` aparece en las líneas: 507, 580
- `Principales preocupaciones al alquilar` aparece en las líneas: 516, 598
- `Interés por la propuesta Rent2Go` aparece en las líneas: 526, 607
- `Características subjetivas identificadas` aparece en las líneas: 536, 616
- `Conclusión del segmento` aparece en las líneas: 547, 627
#### Errores de Formato (Saltos de Página faltantes en cabeceras `#`):
*Todas las cabeceras `#` de este archivo tienen salto de página correcto.*


### [ Capitulo_3.md ]
#### Placeholders o Textos Pendientes:
- **Línea 121**: `- *Pendiente:* Incorporación de metadatos Open Graph y Twitter Cards para optimización en redes sociales.`
- **Línea 122**: `- *Pendiente:* Planificación y optimización ASO (App Store Optimization) para cuando se publiquen las aplicaciones móviles en las tiendas correspondientes.`
- **Línea 296**: `Se mantiene el alcance mobile-first en el reporte, pero esta sección de prototipo interactivo queda marcada como un entregable pendiente para futuras iteraciones debido a que los esfuerzos actuales están concentrados en el desarrollo de la aplicación de producción y de los flujos estáticos del informe.`
- **Línea 298**: `- [PENDIENTE: Configurar un prototipo interactivo con transiciones de flujos completos en Figma].`
- **Línea 299**: `- [PENDIENTE: Grabar video demostrativo de la navegación del prototipo móvil].`
- **Línea 318**: `### Evidencias Pendientes`
- **Línea 319**: `- [PENDIENTE: Capturas de pantalla de la Landing Page en modo claro y modo oscuro].`
- **Línea 320**: `- [PENDIENTE: Reporte de contraste de color y cumplimiento de pautas de accesibilidad WCAG].`
- **Línea 321**: `- [PENDIENTE: Capturas adicionales de pruebas responsive bajo distintos tamaños de pantalla (breakpoints)].`
#### Cabeceras Vacías o sin Contenido:
- **Línea 3** (Nivel 1): `### Capítulo III: Solution UI/UX Design`
- **Línea 157** (Nivel 3): `### 3.1.3. Landing Page UI Design`
- **Línea 187** (Nivel 3): `### 3.1.4. Mobile Applications UX/UI Design`
- **Línea 205** (Nivel 3): `### 3.1.4.2. Mobile Applications Wireflow Diagrams`
- **Línea 310** (Nivel 2): `### 3.3. Assets y Evidencias`
#### Cabeceras Duplicadas:
*No se detectaron cabeceras duplicadas.*
#### Errores de Formato (Saltos de Página faltantes en cabeceras `#`):
*Todas las cabeceras `#` de este archivo tienen salto de página correcto.*


### [ Capitulo_4.md ]
#### Placeholders o Textos Pendientes:
*No se encontraron placeholders de texto o imágenes.*
#### Cabeceras Vacías o sin Contenido:
- **Línea 3** (Nivel 1): `### Capítulo IV: Product Implementation & Validation`
- **Línea 7** (Nivel 2): `### 4. Product Implementation & Validation`
- **Línea 206** (Nivel 3): `### 4.2.1. Sprint 1`
#### Cabeceras Duplicadas:
*No se detectaron cabeceras duplicadas.*
#### Errores de Formato (Saltos de Página faltantes en cabeceras `#`):
- **Línea 360**: `# features/vehicle-search.feature` (Falta `<div style="page-break-after: always;"></div>` antes)
- **Línea 379**: `# features/vehicle-filter.feature` (Falta `<div style="page-break-after: always;"></div>` antes)
- **Línea 390**: `# features/vehicle-detail.feature` (Falta `<div style="page-break-after: always;"></div>` antes)
- **Línea 401**: `# features/vehicle-images.feature` (Falta `<div style="page-break-after: always;"></div>` antes)


### [ Conclusiones.md ]
#### Placeholders o Textos Pendientes:
- **Línea 15**: `[Espacio reservado para el video de validación de la aplicación]`
- **Línea 19**: `[Espacio reservado para el video sobre el producto]`
- **Línea 27**: `[Espacio reservado para el glosario de términos]`
#### Cabeceras Vacías o sin Contenido:
- **Línea 3** (Nivel 1): `### Conclusiones`
#### Cabeceras Duplicadas:
*No se detectaron cabeceras duplicadas.*
#### Errores de Formato (Saltos de Página faltantes en cabeceras `#`):
*Todas las cabeceras `#` de este archivo tienen salto de página correcto.*

