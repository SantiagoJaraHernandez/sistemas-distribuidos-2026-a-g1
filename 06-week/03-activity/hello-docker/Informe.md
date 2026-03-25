Aquí tienes el **README final sin emojis**, limpio y profesional, listo para pegar:

---

# Hello Docker

## Descripción

Esta actividad consiste en la creación de una aplicación mínima en Python, la cual fue contenerizada utilizando Docker. El objetivo es comprender el proceso de construcción de imágenes, ejecución de contenedores, uso de variables de entorno y persistencia de datos.

---

## Estructura del proyecto

```bash
hello-docker/
│
├── app.py
├── requirements.txt
├── Dockerfile
├── .dockerignore
├── data/
└── Evidencias/
    ├── dockerps.png
    └── localhostweb.png
```

---

## Construcción de la imagen

Para construir la imagen Docker, se ejecuta el siguiente comando:

```bash
docker build -t hello-docker:1.0 .
```

---

## Ejecución del contenedor

Para ejecutar el contenedor:

```bash
docker run -d -p 8000:8000 --name hello hello-docker:1.0
```

Esto permite acceder a la aplicación en:

```
http://localhost:8000
```

---

## Verificación

Se puede verificar que el contenedor está en ejecución con:

```bash
docker ps
```

---

## Prueba de la aplicación

Al acceder desde el navegador o usando curl:

```bash
curl http://localhost:8000
```

Se obtiene:

```
Hello from Docker! Running on port 8000
```

---

## Variables de entorno

La aplicación utiliza la variable de entorno `PORT` para definir el puerto de ejecución, permitiendo flexibilidad sin modificar el código.

---

## Persistencia de datos

Se implementó persistencia mediante un volumen (bind mount):

```bash
docker run -d -p 8000:8000 -v %cd%/data:/app/data --name hello hello-docker:1.0
```

Esto permite mantener los datos fuera del contenedor.

---

## Evidencias

### Contenedor en ejecución

![docker ps](Evidencias/dockerps.png)

---

### Aplicación funcionando en navegador

![localhost](Evidencias/localhostweb.png)

---

## Dificultades encontradas

* El código inicial presentaba errores de sintaxis, los cuales fueron corregidos.
* Problemas con rutas de volumen en Windows, solucionados usando `%cd%`.
* Validación del puerto expuesto correctamente.

---

## Conclusiones

Docker permite empaquetar aplicaciones junto con sus dependencias en entornos aislados, facilitando su despliegue y ejecución en diferentes sistemas. Además, el uso de volúmenes y variables de entorno aporta flexibilidad y persistencia al desarrollo de aplicaciones.
