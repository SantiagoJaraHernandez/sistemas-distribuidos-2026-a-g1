# Actividad 1: Crear el Microservicio Base

Se creó el microservicio base utilizando Spring Boot.

## Configuración del proyecto

* **Tipo:** Maven
* **Java:** 17
* **Dependencias:**

  * Spring Web
  * Spring Data JPA
  * PostgreSQL Driver
  * Lombok

---

## Ubicación en el monorepo

El microservicio fue agregado en:

```bash
service-one/
```

---

## Estructura de paquetes

Se organizó el proyecto siguiendo buenas prácticas:

```bash
service-one/
└── src/main/java/com/project/reservations/
    ├── controller/
    ├── service/
    ├── repository/
    └── entity/
```

---

## Configuración `application.yml`

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/reservas_db
    username: postgres
    password: password
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: true
```

---

# Actividad 2: Implementar CRUD Completo

Se implementó el CRUD completo para la entidad **Reserva**.

---

## Entidad: Reserva

```java
@Entity
public class Reservation {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private Long userId;
    private Long courtId;
    private String date;
    private String time;
    private String status;
}
```

---

## Endpoints implementados

### GET /reservations

Obtiene todas las reservas.

### GET /reservations/{id}

Obtiene una reserva por ID.

### POST /reservations

Crea una nueva reserva.

### PUT /reservations/{id}

Actualiza una reserva existente.

### DELETE /reservations/{id}

Elimina una reserva.

---

## Pruebas realizadas

* Se probaron todos los endpoints usando Postman
* Se verificó la correcta inserción, actualización y eliminación en PostgreSQL
* Se validó el flujo completo del CRUD

---

# Actividad 3: Hacer Commit y PR

## Flujo aplicado

1. Se creó la rama:

```bash
feature/SD-001-first-microservice
```

2. Se realizaron commits separados por componente:

* Entity
* Repository
* Service
* Controller

3. Se realizó push al repositorio remoto

4. Se creó Pull Request hacia `develop`

5. Se realizó Code Review por un miembro del equipo y se aprobó el PR
