# Actividad 1: Diseñar la API del Proyecto

Se diseñó la API REST para el microservicio principal: **reservas**.

---

## 📌 Endpoints

### 1. Listar reservas

* **GET** `/reservations`

**Response:**

```json
[
  {
    "id": 1,
    "userId": 10,
    "courtId": 5,
    "date": "2026-03-30",
    "time": "18:00",
    "status": "CONFIRMED"
  }
]
```

---

### 2. Obtener reserva por ID

* **GET** `/reservations/{id}`

**Response:**

```json
{
  "id": 1,
  "userId": 10,
  "courtId": 5,
  "date": "2026-03-30",
  "time": "18:00",
  "status": "CONFIRMED"
}
```

---

### 3. Crear reserva

* **POST** `/reservations`

**Request:**

```json
{
  "userId": 10,
  "courtId": 5,
  "date": "2026-03-30",
  "time": "18:00"
}
```

**Response:**

```json
{
  "message": "Reserva creada exitosamente",
  "id": 1
}
```

---

### 4. Actualizar reserva

* **PUT** `/reservations/{id}`

**Request:**

```json
{
  "date": "2026-03-31",
  "time": "20:00"
}
```

**Response:**

```json
{
  "message": "Reserva actualizada correctamente"
}
```

---

### 5. Eliminar reserva

* **DELETE** `/reservations/{id}`

**Response:**

```json
{
  "message": "Reserva eliminada correctamente"
}
```

---

# Actividad 2: Crear Proyecto Spring Boot del Gateway

## Configuración del proyecto

Se creó un proyecto en Spring Boot con las siguientes características:

* **Tipo:** Maven
* **Java:** 17
* **Dependencia principal:** Spring Cloud Gateway

---

## Estructura

El proyecto fue ubicado en:

```bash
gateway/
```

---

## Configuración `application.yml`

```yaml
spring:
  cloud:
    gateway:
      routes:
        - id: reservation-service
          uri: http://localhost:8081
          predicates:
            - Path=/reservations/**
```

---

## Descripción

* El **API Gateway** actúa como punto de entrada único.
* Redirige las solicitudes hacia el microservicio de reservas.
* Permite centralizar seguridad y control de tráfico.

---

# Actividad 3: Probar con Postman / Thunder Client

## Herramienta utilizada

Se utilizó **Postman** para probar los endpoints.

---

## Colección creada

Se creó una colección llamada:

```
Reservas API
```

---

## Requests incluidos

* GET /reservations
* GET /reservations/{id}
* POST /reservations
* PUT /reservations/{id}
* DELETE /reservations/{id}

---

## Documentación

Cada request incluye:

* URL del endpoint
* Método HTTP
* Body (en caso de POST/PUT)
* Ejemplo de respuesta esperada

---

## Uso

La colección permite:

* Validar el funcionamiento de la API
* Servir como documentación para el equipo
* Facilitar pruebas durante el desarrollo

---

## Nota

Esta actividad establece la base para la comunicación entre microservicios y permite validar el sistema desde etapas tempranas.

---

Si quieres, ahora te doy el **commit perfecto (aquí queda muy bien usar `feat(api)` o `feat(gateway)`)** o incluso dividirlo en varios para que se vea más pro.
Perfecto, te lo dejo como **entrega lista para el fork**, bien hecha y enfocada en su proyecto de **reservas de canchas** 👇

---

# Actividad 1: Diseñar la API del Proyecto

Se diseñó la API REST para el microservicio principal: **reservas**.

---

## 📌 Endpoints

### 1. Listar reservas

* **GET** `/reservations`

**Response:**

```json
[
  {
    "id": 1,
    "userId": 10,
    "courtId": 5,
    "date": "2026-03-30",
    "time": "18:00",
    "status": "CONFIRMED"
  }
]
```

---

### 2. Obtener reserva por ID

* **GET** `/reservations/{id}`

**Response:**

```json
{
  "id": 1,
  "userId": 10,
  "courtId": 5,
  "date": "2026-03-30",
  "time": "18:00",
  "status": "CONFIRMED"
}
```

---

### 3. Crear reserva

* **POST** `/reservations`

**Request:**

```json
{
  "userId": 10,
  "courtId": 5,
  "date": "2026-03-30",
  "time": "18:00"
}
```

**Response:**

```json
{
  "message": "Reserva creada exitosamente",
  "id": 1
}
```

---

### 4. Actualizar reserva

* **PUT** `/reservations/{id}`

**Request:**

```json
{
  "date": "2026-03-31",
  "time": "20:00"
}
```

**Response:**

```json
{
  "message": "Reserva actualizada correctamente"
}
```

---

### 5. Eliminar reserva

* **DELETE** `/reservations/{id}`

**Response:**

```json
{
  "message": "Reserva eliminada correctamente"
}
```

---

# Actividad 2: Crear Proyecto Spring Boot del Gateway

## Configuración del proyecto

Se creó un proyecto en Spring Boot con las siguientes características:

* **Tipo:** Maven
* **Java:** 17
* **Dependencia principal:** Spring Cloud Gateway

---

## Estructura

El proyecto fue ubicado en:

```bash
gateway/
```

---

## Configuración `application.yml`

```yaml
spring:
  cloud:
    gateway:
      routes:
        - id: reservation-service
          uri: http://localhost:8081
          predicates:
            - Path=/reservations/**
```

---

## Descripción

* El **API Gateway** actúa como punto de entrada único.
* Redirige las solicitudes hacia el microservicio de reservas.
* Permite centralizar seguridad y control de tráfico.

---

# Actividad 3: Probar con Postman / Thunder Client

## Herramienta utilizada

Se utilizó **Postman** para probar los endpoints.

---

## Colección creada

Se creó una colección llamada:

```
Reservas API
```

---

## Requests incluidos

* GET /reservations
* GET /reservations/{id}
* POST /reservations
* PUT /reservations/{id}
* DELETE /reservations/{id}

---

## Documentación

Cada request incluye:

* URL del endpoint
* Método HTTP
* Body (en caso de POST/PUT)
* Ejemplo de respuesta esperada

---

## Uso

La colección permite:

* Validar el funcionamiento de la API
* Servir como documentación para el equipo
* Facilitar pruebas durante el desarrollo

---
