# Actividad 1: Identificar Subdominios

Para el sistema de reservas de canchas, se identificaron los siguientes subdominios:

---

## 1. Subdominio: Gestión de Usuarios

* **Tipo:** Supporting

* **Entidades:**

  * Usuario
  * Rol

* **Value Objects:**

  * Email
  * Contraseña
  * Nombre

---

## 2. Subdominio: Gestión de Reservas

* **Tipo:** Core

* **Entidades:**

  * Reserva
  * Horario
  * EstadoReserva

* **Value Objects:**

  * Fecha
  * RangoHorario
  * IdentificadorReserva

---

## 3. Subdominio: Gestión de Canchas

* **Tipo:** Core

* **Entidades:**

  * Cancha
  * Ubicación

* **Value Objects:**

  * TipoCancha
  * Precio
  * Disponibilidad

---

## 4. Subdominio: Pagos

* **Tipo:** Supporting

* **Entidades:**

  * Pago
  * Transacción

* **Value Objects:**

  * Monto
  * MétodoPago
  * EstadoPago

---

## 5. Subdominio: Notificaciones

* **Tipo:** Generic

* **Entidades:**

  * Notificación

* **Value Objects:**

  * Mensaje
  * FechaEnvio
  * TipoNotificación

---

# Actividad 2: Context Map

Se definió un Context Map basado en los subdominios identificados:

---

## Bounded Contexts

* **User Context**
* **Reservation Context**
* **Court Context**
* **Payment Context**
* **Notification Context**

---

## Relaciones

* **User → Reservation**

  * Tipo: REST
  * Uso: autenticación y gestión de reservas

* **Reservation → Court**

  * Tipo: REST
  * Uso: validación de disponibilidad

* **Reservation → Payment**

  * Tipo: REST
  * Uso: procesamiento de pagos

* **Reservation → Notification**

  * Tipo: Eventos
  * Uso: envío de confirmaciones

---

## Datos compartidos

* ID de usuario
* ID de cancha
* Estado de reserva
* Información de pago

---

# Actividad 3: Mapeo de Bounded Contexts a Microservicios

Se define la siguiente tabla de implementación:

| Bounded Context      | Microservicio        | Base de Datos   | Comunicación | Release |
| -------------------- | -------------------- | --------------- | ------------ | ------- |
| User Context         | user-service         | PostgreSQL      | REST         | 1       |
| Reservation Context  | reservation-service  | PostgreSQL      | REST         | 1       |
| Court Context        | court-service        | MongoDB         | REST         | 1       |
| Payment Context      | payment-service      | PostgreSQL      | REST         | 2       |
| Notification Context | notification-service | MongoDB / Redis | Eventos      | 2       |

---

## Justificación

* Los **Core (Reservas y Canchas)** se implementan en el Release 1 por ser críticos.
* Los **Supporting (Usuarios y Pagos)** se priorizan según dependencia funcional.
* Los **Generic (Notificaciones)** pueden implementarse posteriormente sin afectar la lógica principal.
* Se combinan bases de datos relacionales y NoSQL según el tipo de datos.

---

## Nota

Este diseño permite:

* Separación clara de responsabilidades
* Escalabilidad por microservicio
* Evolución independiente de cada contexto
