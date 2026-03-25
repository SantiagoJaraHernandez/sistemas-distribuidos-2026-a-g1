# Actividad 1: User Stories

Se definieron las siguientes User Stories utilizando el formato estándar y priorizadas con MoSCoW:

---

### 1. Registro de usuario

* **User Story:**
  Como usuario, quiero registrarme en la plataforma, para poder acceder a las funcionalidades de reserva.
* **Criterios de aceptación:**

  * El usuario puede crear una cuenta con correo y contraseña
  * Validación de datos obligatorios
* **Prioridad:** Must

---

### 2. Inicio de sesión

* **User Story:**
  Como usuario, quiero iniciar sesión, para acceder a mi cuenta.
* **Criterios de aceptación:**

  * Autenticación correcta con credenciales
  * Mensaje de error si falla
* **Prioridad:** Must

---

### 3. Ver canchas disponibles

* **User Story:**
  Como usuario, quiero ver las canchas disponibles, para elegir dónde jugar.
* **Criterios de aceptación:**

  * Lista de canchas con información básica
  * Visualización de horarios disponibles
* **Prioridad:** Must

---

### 4. Reservar cancha

* **User Story:**
  Como usuario, quiero reservar una cancha, para asegurar mi espacio de juego.
* **Criterios de aceptación:**

  * Selección de fecha y hora
  * Confirmación de reserva
* **Prioridad:** Must

---

### 5. Cancelar reserva

* **User Story:**
  Como usuario, quiero cancelar una reserva, para liberar el horario si no puedo asistir.
* **Criterios de aceptación:**

  * Opción de cancelar reservas activas
  * Actualización de disponibilidad
* **Prioridad:** Should

---

### 6. Ver historial de reservas

* **User Story:**
  Como usuario, quiero ver mi historial de reservas, para llevar control de mis actividades.
* **Criterios de aceptación:**

  * Lista de reservas pasadas y futuras
* **Prioridad:** Should

---

### 7. Pago en línea

* **User Story:**
  Como usuario, quiero pagar mi reserva en línea, para confirmar el uso de la cancha.
* **Criterios de aceptación:**

  * Integración con pasarela de pago
  * Confirmación de transacción
* **Prioridad:** Must

---

### 8. Notificaciones

* **User Story:**
  Como usuario, quiero recibir notificaciones, para recordar mis reservas.
* **Criterios de aceptación:**

  * Envío de recordatorios
  * Confirmación de reservas
* **Prioridad:** Could

---

### 9. Administración de canchas

* **User Story:**
  Como administrador, quiero gestionar canchas, para actualizar disponibilidad y precios.
* **Criterios de aceptación:**

  * Crear, editar y eliminar canchas
* **Prioridad:** Must

---

### 10. Gestión de horarios

* **User Story:**
  Como administrador, quiero definir horarios disponibles, para organizar el uso de las canchas.
* **Criterios de aceptación:**

  * Configuración de horarios por cancha
* **Prioridad:** Must

---

# Actividad 2: Diagrama de Arquitectura

Se propone una arquitectura basada en microservicios:

---

## Microservicios identificados

1. **Servicio de usuarios**

   * Base de datos: PostgreSQL
2. **Servicio de reservas**

   * Base de datos: PostgreSQL
3. **Servicio de canchas**

   * Base de datos: MongoDB
4. **Servicio de pagos**

   * Base de datos: PostgreSQL
5. **Servicio de notificaciones**

   * Base de datos: No persistente / Redis (opcional)

---

## Comunicación

* Comunicación principal mediante **REST APIs**
* Posible uso de mensajería (eventos) para notificaciones

---

## API Gateway

* Punto de entrada único para:

  * Autenticación
  * Enrutamiento de solicitudes
  * Control de acceso

---

## Flujo general

Cliente (Web) → API Gateway → Microservicios → Bases de datos

---

# Actividad 3: Configurar GitHub Project

Se configuró un tablero Kanban en GitHub con el objetivo de gestionar el desarrollo del proyecto.

---

## Columnas creadas

* Backlog
* To Do
* In Progress
* In Review
* Done

---

## Issues creados

Se crearon al menos 5 issues basados en las User Stories más importantes:

* Registro de usuario
* Inicio de sesión
* Ver canchas disponibles
* Reservar cancha
* Pago en línea

---

## Labels configurados

* `feature`
* `bug`
* `enhancement`
* `documentation`

---

## Milestone

* **Nombre:** Release 1 — MVP
* **Objetivo:** Implementar funcionalidades básicas del sistema de reservas
