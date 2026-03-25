# Actividad 1: Levantar PostgreSQL con Docker

## Configuración

Se agregó el archivo `docker-compose.yml` en la raíz del monorepo con la configuración de PostgreSQL.

```yaml
version: '3.8'

services:
  postgres:
    image: postgres:15
    container_name: reservas-db
    environment:
      POSTGRES_DB: reservas_db
      POSTGRES_USER: postgres
      POSTGRES_PASSWORD: password
    ports:
      - "5432:5432"
    volumes:
      - postgres_data:/var/lib/postgresql/data

volumes:
  postgres_data:
```

---

## Ejecución

Se levantó el contenedor con:

```bash
docker-compose up -d
```

---

## Verificación

* Se accedió a pgAdmin para verificar la creación de la base de datos
* Se ejecutó el microservicio
* Se validó que la tabla se crea automáticamente mediante JPA (`ddl-auto: update`)

---

# Actividad 2: Implementar Entidades con Relación

Se implementaron dos entidades relacionadas: **Reserva** y **Cancha**.

---

## Relación

* Una **Cancha** puede tener muchas **Reservas**
* Relación: `@OneToMany` / `@ManyToOne`

---

## Entidades

### Cancha

```java
@Entity
public class Court {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
    private String location;
}
```

---

### Reserva

```java
@Entity
public class Reservation {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;

    private Long userId;
    private String date;
    private String time;

    @ManyToOne
    @JoinColumn(name = "court_id")
    private Court court;
}
```

---

## Implementación

Se desarrollaron:

* Repository para ambas entidades
* Service con lógica de negocio
* Controller con endpoints REST

---

## Uso de DTOs

Se implementaron DTOs para evitar exponer directamente las entidades:

* `ReservationRequestDTO`
* `ReservationResponseDTO`

---

## Verificación

* Se probaron endpoints con Postman
* Se validó la relación entre entidades
* Se comprobó persistencia en PostgreSQL

---

# Actividad 3: Manejo de Errores y Validación

## GlobalExceptionHandler

Se implementó un manejador global de excepciones para respuestas controladas:

```java
@RestControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(Exception.class)
    public ResponseEntity<String> handleException(Exception ex) {
        return ResponseEntity.status(500).body(ex.getMessage());
    }
}
```

---

## Validaciones en DTOs

Se agregaron anotaciones de validación:

```java
public class ReservationRequestDTO {

    @NotBlank
    private String date;

    @NotBlank
    private String time;
}
```

---

## Verificación

* Se enviaron datos inválidos desde Postman
* Se confirmó respuesta con:

  * Código **400 Bad Request**
  * Mensaje claro de error

---

# Actividad 4: Commit, PR y Merge

## Flujo realizado

1. Creación de feature branch
2. Implementación de cambios
3. Commit siguiendo convención
4. Push al repositorio
5. Creación de Pull Request hacia `develop`
6. Code Review por otro equipo
7. Aprobación y merge

---

## Validación final

* La rama `develop` funciona correctamente con PostgreSQL
* Persistencia y relaciones operativas

