# Actividad 1: Análisis CAP

Se analiza cada sistema según el **Teorema CAP (Consistencia, Disponibilidad y Tolerancia a particiones)**:

---

### a) Sistema bancario de transferencias

* **Prioriza:** Consistencia (C) + Tolerancia a particiones (P) → **CP**
* **Justificación:**

  * Es crítico que los datos sean correctos en todo momento (no puede haber doble gasto o saldos incorrectos).
  * Ante fallos de red, el sistema puede sacrificar disponibilidad antes que consistencia.
  * Ejemplo: si no se puede garantizar la consistencia, la transacción se rechaza.

---

### b) Feed de Twitter/X

* **Prioriza:** Disponibilidad (A) + Tolerancia a particiones (P) → **AP**
* **Justificación:**

  * Es más importante que el sistema esté disponible para los usuarios.
  * Se permite consistencia eventual (los posts pueden tardar en aparecer).
  * Los usuarios pueden ver información ligeramente desactualizada sin afectar críticamente la experiencia.

---

### c) Sistema de reservas de cine

* **Prioriza:** Consistencia (C) + Tolerancia a particiones (P) → **CP**
* **Justificación:**

  * Es necesario evitar la doble reserva del mismo asiento.
  * La consistencia es más importante que la disponibilidad en momentos críticos.
  * El sistema puede bloquear o rechazar operaciones si no puede garantizar integridad.

---

### d) Sistema DNS

* **Prioriza:** Disponibilidad (A) + Tolerancia a particiones (P) → **AP**
* **Justificación:**

  * Es fundamental que el sistema responda rápidamente a las consultas.
  * Se maneja consistencia eventual (los cambios en registros DNS tardan en propagarse).
  * Es preferible responder con datos antiguos que no responder.

---

# Actividad 2: Setup de Git

Cada integrante del equipo realizó la configuración inicial de Git y GitHub:

* Instalación de Git en el entorno local.
* Configuración de credenciales:

  ```bash
  git config --global user.name "Nombre"
  git config --global user.email "correo@ejemplo.com"
  ```
* Creación de cuenta en GitHub.
* Práctica de comandos básicos:

  * Inicialización de repositorio
  * Creación de commits
  * Creación y cambio de ramas

Esto permitió estandarizar el flujo de trabajo del equipo.

---

# Actividad 3: Crear Repositorio del Proyecto

Se realizó la configuración inicial del repositorio del proyecto:

* Creación del repositorio en GitHub por el Tech Lead.
* Definición de ramas principales:

  * `main`: rama estable
  * `develop`: integración de desarrollo
  * `qa`: pruebas
* Adición de todos los integrantes como colaboradores.
* Creación del archivo `README.md` con:

  * Nombre del proyecto
  * Integrantes del equipo
  * Descripción general

---

## Nota

Estas configuraciones permiten establecer una base sólida para el desarrollo colaborativo, facilitando el control de versiones, la integración continua y la organización del equipo.
