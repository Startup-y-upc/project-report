# Guía de Capturas Swagger UI — Rent2Go

**URL local:** `http://localhost:8080/swagger-ui/index.html`  
**Alternativa:** `http://localhost:8080/swagger-ui.html`  
**URL producción:** `https://rent2go-backend-production.up.railway.app/swagger-ui.html`

---

## Pasos previos — Autenticar en Swagger UI

1. Ejecutar primero `POST /auth/login` en Postman y copiar el JWT del response.
2. En Swagger UI, hacer clic en el botón **Authorize 🔒** (esquina superior derecha).
3. En el campo `bearerAuth`, pegar el token **sin** el prefijo `Bearer `:
   ```
   eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
   ```
4. Hacer clic en **Authorize** y luego **Close**.
5. A partir de aquí todos los endpoints marcados con 🔒 usarán el token automáticamente.

---

## SPRINT 1 — Capturas del Capítulo 4, sección 4.2.1.6

> Carpeta destino: `Resources/capitulo_4/services-documentation/`

---

### Captura 1 — `1-swagger-endpoints.png`

**Descripción en reporte:** Vista general de los endpoints documentados en Swagger.

**Qué hacer:**
1. Abrir Swagger UI.
2. Sin expandir ningún grupo, hacer scroll para mostrar todos los controladores disponibles (auth-controller, vehicle-controller, feature-controller, reservation-controller, payment-controller, community-trust-controller, etc.).
3. Deben verse los grupos colapsados con sus tags y el conteo de endpoints.
4. **Capturar** la pantalla mostrando al menos 5–6 grupos visibles.

**Lo que debe verse:** La lista completa de grupos/tags con los métodos y paths a la derecha de cada grupo colapsado.

---

### Captura 2 — `2-swagger-search.png`

**Descripción en reporte:** Ejemplo de documentación del endpoint GET /api/vehicles/search.

**Qué hacer:**
1. Expandir el grupo **vehicle-controller**.
2. Buscar el endpoint `GET /api/v1/vehicles` (búsqueda con filtros).
3. Hacer clic en ese endpoint para expandirlo.
4. En la sección **Parameters** deben verse todos los query params: `categories`, `minPrice`, `maxPrice`, `minYear`, `maxYear`, `seats`, `transmission`, `fuelType`, `location`, `centerLatitude`, `centerLongitude`, `radiusKm`, `page`, `size`.
5. **Capturar** con los parámetros expandidos y visibles. Si no caben en pantalla, hacer zoom out al 80% en el navegador.

**Opcional — ejecutar desde Swagger:**
1. Hacer clic en **Try it out**.
2. Llenar: `location = Lima`, `minPrice = 50`, `maxPrice = 200`.
3. Hacer clic en **Execute**.
4. Capturar el resultado con la URL generada y el Response body con la lista de vehículos.

---

### Captura 3 — `3-swagger-request-body.png`

**Descripción en reporte:** Definición del request body para operaciones de creación o actualización.

**Qué hacer:**
1. Expandir el grupo **vehicle-controller**.
2. Hacer clic en `POST /api/v1/vehicles` para expandirlo.
3. Hacer clic en **Try it out**.
4. En la sección **Request body**, el editor JSON mostrará el schema completo con todos los campos.
5. Llenar el body con datos de ejemplo:
   ```json
   {
     "licensePlate": "ABC-123",
     "make": "Toyota",
     "model": "Corolla",
     "year": 2021,
     "dailyPrice": 85.00,
     "categoryId": 1,
     "location": "Miraflores, Lima",
     "seats": 5,
     "transmission": "AUTOMATIC",
     "fuelType": "GASOLINE"
   }
   ```
6. **Capturar** mostrando el editor JSON con el schema y los campos rellenados. El botón **Execute** debe ser visible.

---

### Captura 4 — `4-swagger-response-schemas.png`

**Descripción en reporte:** Esquemas de respuesta y modelos generados en Swagger.

**Qué hacer:**
1. En cualquier endpoint expandido (ej: `GET /api/v1/vehicles/{id}`), hacer scroll hacia abajo hasta la sección **Responses**.
2. Hacer clic en el código de respuesta `200` para expandir el schema completo del modelo (VehicleResource con todos sus campos: id, make, model, year, dailyPrice, images, features, etc.).
3. Hacer clic también en el schema de error `404` para que sea visible.
4. Alternativamente, ir a la sección **Schemas** al final de la página de Swagger, que muestra todos los modelos definidos (VehicleResource, UserResource, ReservationResource, etc.).
5. **Capturar** la sección Responses o Schemas mostrando los modelos con sus tipos de dato.

---

## SPRINT 2 — Capturas del Capítulo 4, sección 4.2.2.6

> Carpeta destino: `Resources/capitulo_4/services-documentation/`

---

### Captura 5 — `5-swagger-iam-endpoints.png`

**Descripción en reporte:** Vista de endpoints de IAM documentados en Swagger.

**Qué hacer:**
1. Expandir el grupo **auth-controller** (o el tag que agrupe los endpoints de `/auth`).
2. Deben verse los siguientes endpoints colapsados en la lista:
   - `POST /api/v1/auth/register`
   - `POST /api/v1/auth/login`
   - `POST /api/v1/auth/verify`
   - `POST /api/v1/auth/kyc`
   - `GET  /api/v1/auth/me`
   - `POST /api/v1/auth/password/request`
   - `POST /api/v1/auth/password/reset`
3. **Capturar** con el grupo expandido mostrando todos los endpoints del dominio IAM. Los endpoints con 🔒 deben ser visibles.

**Opcional — mostrar detalle de uno:**  
Expandir `POST /api/v1/auth/register` y capturar el schema del request body con todos los campos (email, password, username, fullName, phone, accountType).

---

### Captura 6 — `6-swagger-vehicle-endpoints.png`

**Descripción en reporte:** Vista de endpoints de Vehicle Catalog documentados en Swagger.

**Qué hacer:**
1. Expandir el grupo **vehicle-controller** y el grupo **vehicle-feature-controller**.
2. Deben verse los endpoints:
   - `POST   /api/v1/vehicles`
   - `GET    /api/v1/vehicles`
   - `GET    /api/v1/vehicles/me`
   - `GET    /api/v1/vehicles/{id}`
   - `PUT    /api/v1/vehicles/{id}`
   - `PUT    /api/v1/vehicles/{id}/price`
   - `POST   /api/v1/vehicles/{id}/images`
   - `POST   /api/v1/vehicles/{id}/images/upload`
   - `POST   /api/v1/vehicles/{id}/images/upload/batch`
   - `PUT    /api/v1/vehicles/{vehicleId}/images/{imageId}/primary`
   - `DELETE /api/v1/vehicles/{id}/images/{imageId}`
   - `GET    /api/v1/features`
   - `POST   /api/v1/features`
3. Si no caben todos en pantalla, hacer zoom out al 75% en el navegador.
4. **Capturar** con los dos grupos visibles y todos los endpoints listados.

---

### Captura 7 — `7-swagger-booking-endpoints.png`

**Descripción en reporte:** Vista de endpoints de Booking y Availability documentados en Swagger.

**Qué hacer:**
1. Expandir los grupos **reservation-controller**, **availability-controller** y **favorite-controller**.
2. Deben verse los endpoints:
   - `POST   /api/v1/reservations`
   - `GET    /api/v1/reservations`
   - `GET    /api/v1/reservations/{id}`
   - `POST   /api/v1/reservations/{id}/cancel`
   - `POST   /api/v1/reservations/{id}/status`
   - `POST   /api/v1/reservations/{id}/confirm-return`
   - `GET    /api/v1/reservations/owner`
   - `GET    /api/v1/reservations/renter/{renterId}/history`
   - `POST   /api/v1/availability/block`
   - `DELETE /api/v1/availability/{id}`
   - `GET    /api/v1/availability/vehicle/{vehicleId}/check`
   - `POST   /api/v1/favorites`
   - `DELETE /api/v1/favorites`
   - `GET    /api/v1/favorites`
3. **Capturar** los tres grupos visibles.

**Opcional — mostrar detalle:**  
Expandir `POST /api/v1/reservations` y capturar el schema del body (vehicleId, renterId, ownerId, startDate, endDate, totalAmount, coveragePlan).

---

### Captura 8 — `8-swagger-payment-endpoints.png`

**Descripción en reporte:** Vista de endpoints de Payments y Stripe documentados en Swagger.

**Qué hacer:**
1. Expandir el grupo **payment-controller** (o **stripe-controller**).
2. Deben verse los endpoints:
   - `POST  /api/v1/payments/calculate`
   - `POST  /api/v1/payments/create-intent`
   - `POST  /api/v1/payments/webhook`
   - `POST  /api/v1/payments/refund`
   - `GET   /api/v1/payments/reservations/{reservationId}/receipt`
   - `GET   /api/v1/payments/owners/{ownerId}/earnings`
   - `POST  /api/v1/payments/promocodes`
   - `GET   /api/v1/payments/promocodes`
   - `GET   /api/v1/payments/promocodes/{code}`
   - `PATCH /api/v1/payments/promocodes/{code}/deactivate`
   - `DELETE /api/v1/payments/promocodes/{code}`
3. **Capturar** el grupo expandido. Los endpoints con 🔒 (AUTH requerida) deben ser visibles.

**Opcional — mostrar detalle de Stripe:**  
Expandir `POST /api/v1/payments/create-intent` y capturar el schema del body (reservationId, amountCents, currency) junto con la respuesta esperada (clientSecret, id).

---

### Captura 9 — `9-swagger-community-endpoints.png`

**Descripción en reporte:** Vista de endpoints de Community & Trust documentados en Swagger.

**Qué hacer:**
1. Expandir el grupo **community-trust-controller**.
2. Deben verse los endpoints:
   - `POST  /api/v1/community-trust/reviews`
   - `POST  /api/v1/community-trust/reviews/{reviewId}/flag`
   - `POST  /api/v1/community-trust/reviews/{reviewId}/approve`
   - `POST  /api/v1/community-trust/reviews/{reviewId}/reject`
   - `GET   /api/v1/community-trust/reviews/vehicle/{vehicleId}`
   - `GET   /api/v1/community-trust/reviews/user/{userId}`
   - `GET   /api/v1/community-trust/users/{userId}/reputation`
   - `GET   /api/v1/community-trust/vehicles/{vehicleId}/rating`
   - `POST  /api/v1/community-trust/users/{userId}/block`
   - `GET   /api/v1/community-trust/dashboard`
   - `POST  /api/v1/community-trust/reservations/{reservationId}/disputes`
   - `POST  /api/v1/community-trust/conversations`
   - `GET   /api/v1/community-trust/conversations/{conversationId}`
   - `GET   /api/v1/community-trust/users/{userId}/conversations`
   - `POST  /api/v1/community-trust/conversations/{conversationId}/messages`
   - `GET   /api/v1/community-trust/conversations/{conversationId}/messages`
3. Si hay demasiados para una sola pantalla, hacer zoom out al 75%.
4. **Capturar** el grupo completo.

**Opcional — mostrar enum ReviewCategory:**  
Expandir `POST /api/v1/community-trust/reviews` y hacer clic en el schema del campo `category` para que muestre el enum: `VEHICLE | USER | EXPERIENCE`.

---

## Tips generales para capturas

- **Zoom del navegador:** Si el contenido no cabe, usar Ctrl+- para reducir al 75% o 80%.
- **Ancho de ventana:** Usar 1440px de ancho mínimo para que se vean bien las columnas de Swagger.
- **Modo oscuro/claro:** Swagger UI es fondo blanco por defecto; dejar así para que las capturas sean consistentes.
- **Ocultar otros grupos:** Hacer clic en los grupos que no son del dominio actual para colapsarlos y que solo se vea el grupo relevante.
- **Resolución:** Capturar en pantalla completa (F11 o botón de pantalla completa del navegador) para mayor resolución.
- **Formato:** PNG, ancho 900px mínimo (el `width="900"` que indica el reporte).
