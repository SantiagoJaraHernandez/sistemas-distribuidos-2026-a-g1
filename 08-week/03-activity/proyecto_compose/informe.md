# Informe — Orquestación básica con Docker Compose

## Descripción

En esta actividad se implementó un entorno multicontenedor utilizando Docker Compose, con el objetivo de orquestar un servicio web y una base de datos de manera sencilla.

Se definieron dos servicios principales:

* **web**: servidor Nginx expuesto en el puerto 8080
* **db**: base de datos PostgreSQL versión 15 con credenciales configuradas

Adicionalmente, se utilizó un volumen para garantizar la persistencia de los datos.

---

## Configuración

Se creó un archivo `docker-compose.yml` en el cual se definieron:

* Imagen oficial de Nginx para el servicio web
* Imagen oficial de PostgreSQL 15 para la base de datos
* Variables de entorno para la configuración de la base de datos
* Volumen persistente para almacenamiento de datos

---

## Ejecución

Los servicios se levantaron con el siguiente comando:

```bash
docker compose up -d
```

Se verificó el estado de los contenedores con:

```bash
docker compose ps
```

---

## Verificación del servicio web

Se accedió desde el navegador a la URL:

```
http://localhost:8080
```

Comprobando que el servidor Nginx responde correctamente.

---

## Verificación de la base de datos

Se accedió al contenedor de PostgreSQL para validar:

* La creación de la base de datos
* El correcto funcionamiento del servicio

---

## Persistencia de datos

Se realizó una prueba creando una tabla e insertando información en la base de datos.

Posteriormente, se reiniciaron los contenedores con:

```bash
docker compose down
docker compose up -d
```

Al volver a consultar la base de datos, los datos permanecían, lo que confirma la persistencia gracias al volumen configurado.

---

## Evidencias

### Estado de contenedores

<img src="Evidencias/dockercompose.png" alt="docker compose ps" width="800"/>

---

### Servicio web funcionando

<img src="Evidencias/localhost.png" alt="nginx funcionando" width="800"/>

---

### Verificación de base de datos

<img src="Evidencias/verificacionbd.png" alt="verificación base de datos" width="800"/>

---

## Reflexión

Docker Compose facilita la definición y ejecución de aplicaciones con múltiples contenedores mediante un único archivo de configuración. Esto mejora la organización del entorno, reduce errores manuales y permite replicar fácilmente la infraestructura en diferentes entornos.

El uso de volúmenes resulta clave para asegurar la persistencia de la información, especialmente en servicios como bases de datos.

---

## Conclusión

Se logró configurar y ejecutar correctamente un entorno multicontenedor compuesto por un servidor web y una base de datos. Se validó su funcionamiento y la persistencia de los datos, cumpliendo con los objetivos de la actividad.
