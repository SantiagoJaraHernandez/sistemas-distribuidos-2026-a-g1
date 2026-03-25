# Actividad 1: Configurar el Monorepo

Se realizó la configuración inicial del repositorio siguiendo el enfoque de monorepo.

## Estructura definida

Se crearon los siguientes directorios en la raíz del proyecto:

```bash
/
├── gateway/
├── service-one/
├── .github/
│   └── workflows/
├── .gitignore
├── README.md
```

## Archivos configurados

* **.gitignore:**
  Se configuró para excluir archivos innecesarios como dependencias, logs y variables de entorno.

* **README.md:**
  Incluye:

  * Nombre del proyecto
  * Integrantes del equipo
  * Descripción general
  * Arquitectura basada en microservicios

---

# Actividad 2: Configurar Ramas y Protecciones

## Ramas creadas

Se definieron las siguientes ramas principales:

* `main`: rama estable de producción
* `develop`: integración de desarrollo
* `qa`: pruebas

## Protección de la rama main

Se configuraron reglas de protección en GitHub:

* Requiere Pull Request para realizar cambios
* Requiere al menos 1 aprobación antes de hacer merge

## Validación

Se verificó que:

* No es posible hacer push directo a `main`
* Los cambios deben pasar por Pull Request

## Flujo de trabajo

Se implementó el siguiente flujo:

1. Creación de rama feature desde `develop`
2. Desarrollo de cambios
3. Creación de Pull Request hacia `develop`
4. Revisión y aprobación
5. Integración de cambios

---

# Actividad 3: Primer GitHub Action

## Configuración del workflow

Se creó el archivo:

```bash
.github/workflows/ci.yml
```

Con un workflow básico de integración continua.

## Funcionalidad

* Se ejecuta automáticamente en cada push a `develop`
* Permite validar el estado del proyecto

## Verificación

* El workflow se ejecuta correctamente en la pestaña **Actions** de GitHub
* El resultado del workflow aparece como **status check** en los Pull Requests

---

## Nota

Esta configuración establece una base sólida para:

* Trabajo colaborativo estructurado
* Integración continua
* Control de calidad mediante revisiones
* Escalabilidad del proyecto
