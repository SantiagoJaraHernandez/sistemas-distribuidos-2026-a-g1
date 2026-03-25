## Informe — Orquestación básica con Docker Compose

### Configuración

Se creó un archivo `docker-compose.yml` en el cual se definieron dos servicios:

* **web**: basado en la imagen `nginx:latest`, expuesto en el puerto 8080 del host hacia el puerto 80 del contenedor.
* **db**: basado en `postgres:15`, configurado mediante variables de entorno para usuario, contraseña y nombre de la base de datos.

Adicionalmente, se configuró un volumen llamado `postgres_data` para garantizar la persistencia de la información.

---

### Ejecución y verificación

Los servicios se levantaron con el comando:

```cmd
docker compose up -d
```

Se verificó su estado con:

```cmd
docker compose ps
```

El servicio web fue accesible desde el navegador en `http://localhost:8080`, mostrando la página de Nginx.
El servicio de base de datos se validó mediante la revisión de logs, confirmando que estaba listo para aceptar conexiones.

---

### Persistencia

Se utilizó un volumen para la base de datos. Después de detener y volver a iniciar los contenedores, los datos se mantuvieron, lo que confirma el funcionamiento correcto de la persistencia.

---

### Evidencias

* Estado de contenedores:
  ![docker ps](Evidencias%20Activity/dockerps.png)

* Levantamiento de servicios:
  ![docker compose up](Evidencias%20Activity/Levantamiento%20del%20contenedor.png)

* Servicio web en ejecución:
  ![nginx](Evidencias%20Activity/nginx%20funcionando%20en%20el%20puerto%20asignado.png)

* Verificación de base de datos:
  ![db](Evidencias%20Activity/Verificacion%20BD.png)

---

### Reflexión

Docker Compose permite definir y gestionar múltiples servicios de forma centralizada, facilitando el despliegue y la administración de entornos de desarrollo. Además, el uso de volúmenes asegura la persistencia de datos, lo cual es fundamental en aplicaciones que utilizan bases de datos.
