# 4. Actividades de Clase

## Actividad 1: Identificar Sistemas Distribuidos

Se analizaron tres aplicaciones de uso cotidiano para clasificarlas según su arquitectura:

### 1. WhatsApp

* **Clasificación:** Sistema distribuido
* **Justificación:**

  * Soporte multiplataforma (móvil y web).
  * Sincronización en tiempo real entre dispositivos.
  * Manejo de múltiples servicios independientes (mensajería, archivos, notificaciones).
  * Persistencia y entrega diferida de mensajes (funcionamiento parcial offline).

### 2. Spotify

* **Clasificación:** Sistema distribuido
* **Justificación:**

  * Disponible en múltiples plataformas (web, móvil, escritorio).
  * Uso de streaming desde servidores distribuidos.
  * Separación de funcionalidades (recomendaciones, reproducción, gestión de biblioteca).
  * Soporte offline mediante descarga de contenido.

### 3. Calculadora básica

* **Clasificación:** Sistema monolítico
* **Justificación:**

  * Funciona completamente de manera local.
  * No depende de servicios externos.
  * Toda la lógica está contenida en una única aplicación.

---

## Actividad 2: Formación de Equipos

El equipo está conformado por 5 integrantes con los siguientes roles:

* **Project Manager (PM):** Iván Perdomo
* **Backend:** Santiago Jara Hernández
* **Base de Datos:** Nelson Gutiérrez
* **Frontend:** Sneider Díaz
* **DevOps:** Óscar León

**Nota:** Los roles podrán rotar durante el semestre según las necesidades del proyecto y la organización del equipo.

---

## Actividad 3: Brainstorming del Proyecto

Se plantean tres ideas de proyecto con enfoque en arquitectura distribuida basada en microservicios:

---

### Idea 1: Plataforma de empleo para jóvenes sin experiencia

* **Problema:**
  Los jóvenes sin experiencia laboral enfrentan barreras para acceder a su primer empleo.

* **Arquitectura propuesta (microservicios):**

  * Servicio de usuarios y perfiles
  * Servicio de ofertas laborales
  * Servicio de recomendación (matching)
  * Servicio de cursos y capacitación
  * Servicio de notificaciones

* **Datos:**

  * Perfiles de usuario
  * Vacantes
  * Postulaciones
  * Cursos realizados
  * Empresas

---

### Idea 2: Aplicación de rutas seguras (SafeRoute)

* **Problema:**
  Riesgos de seguridad en desplazamientos urbanos.

* **Arquitectura propuesta:**

  * Servicio de geolocalización
  * Servicio de cálculo de rutas seguras
  * Servicio de reportes ciudadanos
  * Servicio de usuarios
  * Servicio de notificaciones en tiempo real

* **Datos:**

  * Ubicación de usuarios
  * Reportes de incidentes
  * Historial de rutas
  * Zonas de riesgo

---

### Idea 3: Plataforma web de reservas de canchas deportivas

* **Problema:**
  Dificultad para gestionar reservas de canchas deportivas, falta de disponibilidad visible y procesos manuales ineficientes.

* **Solución propuesta:**
  Plataforma web que permita a los usuarios consultar disponibilidad en tiempo real, reservar canchas y gestionar pagos de manera digital.

---

### Arquitectura propuesta (enfoque distribuido)

Se plantea una arquitectura basada en microservicios, donde cada componente sea independiente, escalable y mantenible:

* **API Gateway**

  * Punto de entrada único para clientes (web/móvil)
  * Manejo de autenticación y enrutamiento

* **Microservicios:**

  1. **Servicio de usuarios**

     * Registro, login, autenticación
     * Gestión de perfiles

  2. **Servicio de reservas**

     * Creación, modificación y cancelación de reservas
     * Validación de disponibilidad

  3. **Servicio de canchas**

     * Información de canchas
     * Horarios disponibles
     * Ubicación

  4. **Servicio de pagos**

     * Integración con pasarelas de pago
     * Gestión de transacciones

  5. **Servicio de notificaciones**

     * Confirmaciones de reserva
     * Recordatorios

---

### Datos que maneja

* Usuarios (datos personales, credenciales)
* Canchas (ubicación, tipo, disponibilidad)
* Reservas (fechas, horarios, estado)
* Pagos (transacciones, estado)
* Historial de actividad

---

### Tecnologías sugeridas

* **Frontend:** React + Tailwind
* **Backend:** Node.js / Spring Boot
* **Base de datos:** PostgreSQL / MongoDB
* **DevOps:** Docker + Docker Compose
* **Comunicación:** REST APIs

---

### Justificación como sistema distribuido

* Separación de responsabilidades en microservicios.
* Escalabilidad independiente (por ejemplo, reservas o pagos).
* Alta disponibilidad.
* Facilita mantenimiento y evolución del sistema.
* Permite integración con servicios externos (pagos, notificaciones).
