# Guía de Capturas Postman — Rent2Go

**Base URL:** `http://localhost:8080/api/v1`  
**Colección:** importar `postman/rent2go-backend.postman_collection.json`

---

## Variables de entorno (configurar antes de empezar)

| Variable | Valor inicial | Se llena automáticamente en |
|---|---|---|
| `baseUrl` | `http://localhost:8080/api/v1` | Manual |
| `token` | *(vacío)* | POST /auth/login → Test script |
| `userId` | *(vacío)* | POST /auth/register → Test script |
| `vehicleId` | *(vacío)* | POST /vehicles → Test script |
| `reservationId` | *(vacío)* | POST /reservations → Test script |
| `ownerId` | `1` | mismo que `userId` del owner |
| `renterId` | `2` | `userId` del segundo usuario registrado |

**Test script para auto-guardar el token** (tab Tests de POST /auth/login):
```javascript
pm.environment.set("token", pm.response.json().token);
pm.environment.set("userId", pm.response.json().id);
```

---

## SPRINT 1 — Capturas del Capítulo 4, sección 4.2.1.5

> Carpeta destino: `Resources/capitulo_4/execution/backend-api/`

---

### Captura 1 — `1-postman-search.png`

**Descripción en reporte:** Prueba del endpoint GET /api/v1/vehicles con filtros para búsqueda de vehículos (US19).

| Campo | Valor |
|---|---|
| Método | `GET` |
| URL | `{{baseUrl}}/vehicles` |
| Auth | No requerida |

**Query Params a agregar en Postman:**

| Key | Value |
|---|---|
| `categories` | `1` |
| `minPrice` | `50` |
| `maxPrice` | `200` |
| `location` | `Lima` |
| `page` | `0` |
| `size` | `10` |

**Qué mostrar en la captura:** La pestaña Params con los filtros visibles, la URL completa generada, y la respuesta JSON con la lista de vehículos.

---

### Captura 2 — `2-postman-detail.png`

**Descripción en reporte:** Respuesta del endpoint GET /api/v1/vehicles/{id} con detalles completos del vehículo (US22).

| Campo | Valor |
|---|---|
| Método | `GET` |
| URL | `{{baseUrl}}/vehicles/{{vehicleId}}` |
| Auth | No requerida |

**Qué mostrar en la captura:** La URL con el `vehicleId` resuelto, y la respuesta JSON completa del vehículo (make, model, year, dailyPrice, images, features, etc.).

---

### Captura 3 — `3-postman-update-price.png`

**Descripción en reporte:** Actualización de precio diario mediante PUT /api/v1/vehicles/{id}/price (US20).

| Campo | Valor |
|---|---|
| Método | `PUT` |
| URL | `{{baseUrl}}/vehicles/{{vehicleId}}/price` |
| Auth | Bearer `{{token}}` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "vehicleId": 1,
  "newDailyPrice": 95.00
}
```

**Qué mostrar en la captura:** La pestaña Authorization con Bearer token visible, el body con el nuevo precio, y la respuesta 200 con el vehículo actualizado.

---

### Captura 4 — `4-postman-upload-image.png`

**Descripción en reporte:** Carga de imagen para un vehículo mediante POST /api/v1/vehicles/{id}/images (US23).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/vehicles/{{vehicleId}}/images` |
| Auth | Bearer `{{token}}` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "imageUrl": "https://res.cloudinary.com/rent2go/img/toyota_front.jpg",
  "imagePath": "rent2go/vehicles/toyota_front",
  "isPrimary": false,
  "imageOrder": 2
}
```

**Qué mostrar en la captura:** El body JSON con la imageUrl de Cloudinary, y la respuesta 201 con el vehículo actualizado incluyendo la nueva imagen.

---

### Captura 5 — `5-postman-set-primary-image.png`

**Descripción en reporte:** Establecimiento de imagen primaria mediante PUT /api/v1/vehicles/{vehicleId}/images/{imageId}/primary (US23).

| Campo | Valor |
|---|---|
| Método | `PUT` |
| URL | `{{baseUrl}}/vehicles/{{vehicleId}}/images/1/primary` |
| Auth | Bearer `{{token}}` |

> Reemplaza `1` por el `id` de la imagen devuelto en la captura anterior.

**Qué mostrar en la captura:** La URL con los dos path params (`vehicleId` e `imageId`), la respuesta 200 y el campo `isPrimary: true` en el JSON de respuesta.

---

## SPRINT 2 — Capturas del Capítulo 4, sección 4.2.2.5

> Carpeta destino: `Resources/capitulo_4/execution/backend-api/`

---

### Captura 1 — `1-postman-register.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/auth/register para registro de usuarios (US01).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/auth/register` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "email": "owner@rent2go.com",
  "password": "Password123",
  "username": "owner_carlos",
  "fullName": "Carlos Mendoza",
  "phone": "+51999888777",
  "accountType": "OWNER"
}
```

**Qué mostrar en la captura:** El body con todos los campos, y la respuesta 201 con el objeto de usuario creado (id, email, username, accountType).

---

### Captura 2 — `2-postman-login-jwt.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/auth/login retornando JWT token (US02).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/auth/login` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "email": "owner@rent2go.com",
  "password": "Password123",
  "rememberMe": false
}
```

**Qué mostrar en la captura:** La respuesta 200 con el JWT token visible en el body (`"token": "eyJ..."`). El token debe verse completo o al menos los primeros caracteres que confirman que es un JWT.

**Después de capturar:** Agrega este test script para que las siguientes requests usen el token automáticamente:
```javascript
pm.environment.set("token", pm.response.json().token);
```

---

### Captura 3 — `3-postman-profile.png`

**Descripción en reporte:** Prueba del endpoint GET /api/v1/auth/me obteniendo perfil con estado KYC (US08).

| Campo | Valor |
|---|---|
| Método | `GET` |
| URL | `{{baseUrl}}/auth/me` |
| Auth | Bearer `{{token}}` |

**Qué mostrar en la captura:** La pestaña Authorization con el tipo Bearer Token y el token en el campo, y la respuesta 200 con el perfil incluyendo el campo `kycStatus` (ej: `"PENDING"` o `"APPROVED"`).

---

### Captura 4 — `4-postman-kyc-upload.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/auth/kyc para subida de documentos KYC a Cloudinary (US06).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/auth/kyc` |
| Auth | Bearer `{{token}}` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "userId": 1,
  "fullName": "Carlos Mendoza",
  "idNumber": "12345678",
  "dniFrontUrl": "https://res.cloudinary.com/rent2go/img/dni_front.jpg",
  "dniBackUrl": "https://res.cloudinary.com/rent2go/img/dni_back.jpg",
  "driverLicenseUrl": "https://res.cloudinary.com/rent2go/img/license.jpg"
}
```

**Qué mostrar en la captura:** El body completo con las URLs de Cloudinary visibles, y la respuesta 201.

---

### Captura 5 — `5-postman-create-vehicle.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/vehicles para registro de vehículo (US11).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/vehicles` |
| Auth | Bearer `{{token}}` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "licensePlate": "ABC-123",
  "make": "Toyota",
  "model": "Corolla",
  "year": 2021,
  "vin": "1HGBH41JXMN109186",
  "dailyPrice": 85.00,
  "categoryId": 1,
  "location": "Miraflores, Lima",
  "description": "Auto en excelente estado, AC, GPS incluido",
  "seats": 5,
  "transmission": "AUTOMATIC",
  "fuelType": "GASOLINE",
  "latitude": -12.1191,
  "longitude": -77.0282,
  "features": ["GPS", "Bluetooth", "Aire acondicionado"]
}
```

**Qué mostrar en la captura:** El body con todos los campos, y la respuesta 201 con el `id` del vehículo creado.

**Después de capturar:**
```javascript
pm.environment.set("vehicleId", pm.response.json().id);
```

---

### Captura 6 — `6-postman-vehicle-images.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/vehicles/{id}/images/upload con integración Cloudinary (US12).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/vehicles/{{vehicleId}}/images/upload` |
| Auth | Bearer `{{token}}` |
| Content-Type | `multipart/form-data` *(Postman lo pone automático)* |

**Body — seleccionar form-data:**

| Key | Type | Value |
|---|---|---|
| `file` | **File** | *(seleccionar imagen del disco)* |
| `isPrimary` | Text | `true` |
| `imageOrder` | Text | `1` |

> En Postman: Body → form-data → en la columna Key hacer clic en el dropdown junto a "file" y cambiar de Text a **File**.

**Qué mostrar en la captura:** El body form-data con el tipo File visible para el campo `file`, y la respuesta 201 con la `imageUrl` de Cloudinary en el JSON de respuesta.

---

### Captura 7 — `7-postman-owner-vehicles.png`

**Descripción en reporte:** Prueba del endpoint GET /api/v1/vehicles/me obteniendo vehículos del propietario (US13).

| Campo | Valor |
|---|---|
| Método | `GET` |
| URL | `{{baseUrl}}/vehicles/me` |
| Auth | Bearer `{{token}}` |

**Query Params (opcionales):**

| Key | Value |
|---|---|
| `page` | `0` |
| `size` | `20` |

**Qué mostrar en la captura:** La pestaña Authorization con Bearer token, y la respuesta 200 con el array de vehículos del propietario autenticado.

---

### Captura 8 — `8-postman-availability.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/availability/block para bloquear fechas (US16).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/availability/block` |
| Auth | Bearer `{{token}}` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "vehicleId": 1,
  "startDate": "2025-08-01",
  "endDate": "2025-08-05",
  "requestedBy": 1
}
```

**Qué mostrar en la captura:** El body con las fechas bloqueadas y la respuesta 201 confirmando el bloqueo.

---

### Captura 9 — `9-postman-create-reservation.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/reservations para crear reserva (US24).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/reservations` |
| Auth | Bearer `{{token}}` *(del renter)* |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "vehicleId": 1,
  "renterId": 2,
  "ownerId": 1,
  "startDate": "2025-09-01",
  "endDate": "2025-09-05",
  "totalAmount": 340.00,
  "pickupLocation": "Miraflores, Lima",
  "returnLocation": "Miraflores, Lima",
  "coveragePlan": "BASIC"
}
```

**Qué mostrar en la captura:** El body completo y la respuesta 201 con el `id` de la reserva, el `status: "PENDING"`, y los datos del vehículo y fechas.

**Después de capturar:**
```javascript
pm.environment.set("reservationId", pm.response.json().id);
```

---

### Captura 10 — `10-postman-tariff-calc.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/payments/calculate con desglose de tarifa (US27).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/payments/calculate` |
| Auth | No requerida |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "baseAmount": 340.00,
  "currency": "PEN",
  "coveragePlan": "BASIC",
  "fees": [],
  "discounts": []
}
```

**Qué mostrar en la captura:** El body y la respuesta 200 mostrando el desglose completo: `subtotal`, `serviceFee`, `coverageFee`, `taxes`, `discount`, `total`.

---

### Captura 11 — `11-postman-stripe-intent.png`

**Descripción en reporte:** Prueba del endpoint POST /api/v1/payments/create-intent integrando Stripe (SP01).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/payments/create-intent` |
| Auth | Bearer `{{token}}` |
| Content-Type | `application/json` |

**Body (raw JSON):**
```json
{
  "reservationId": 1,
  "amountCents": 34000,
  "currency": "pen"
}
```

> `amountCents` es el total en centavos: S/. 340.00 = `34000`.

**Qué mostrar en la captura:** La respuesta 200 con el `clientSecret` de Stripe visible (`pi_...`) y el `id` del PaymentIntent.

---

### Captura 12 — `12-postman-stripe-webhook.png`

**Descripción en reporte:** Configuración del endpoint POST /api/v1/payments/webhook para eventos de Stripe (SP01).

| Campo | Valor |
|---|---|
| Método | `POST` |
| URL | `{{baseUrl}}/payments/webhook` |
| Auth | No requerida |
| Content-Type | `application/json` |
| Header extra | `Stripe-Signature: t=123,v1=abc` *(valor de prueba)* |

**Body (raw JSON) — evento de prueba Stripe:**
```json
{
  "id": "evt_test_webhook",
  "object": "event",
  "type": "payment_intent.succeeded",
  "data": {
    "object": {
      "id": "pi_test_123",
      "amount": 34000,
      "currency": "pen",
      "status": "succeeded",
      "metadata": {
        "reservationId": "1"
      }
    }
  }
}
```

**Qué mostrar en la captura:** Los headers con `Stripe-Signature` visible, el body del evento, y la respuesta 200 `"received"`. Si da 400 por firma inválida, captura igualmente mostrando el endpoint configurado.

---

## Orden de ejecución recomendado

```
1. POST /auth/register       (owner)
2. POST /auth/register       (renter — segundo usuario)
3. POST /auth/login          (owner → guarda token)
4. GET  /auth/me
5. POST /auth/kyc
6. POST /vehicles            → guarda vehicleId
7. POST /vehicles/{id}/images/upload
8. GET  /vehicles/me
9. POST /availability/block
10. GET /vehicles            (con filtros — búsqueda)
11. GET /vehicles/{id}       (detalle)
12. PUT /vehicles/{id}/price
13. POST /vehicles/{id}/images
14. PUT /vehicles/{id}/images/{imageId}/primary
15. POST /reservations       → guarda reservationId
16. POST /payments/calculate
17. POST /payments/create-intent
18. POST /payments/webhook
```
