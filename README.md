# Birthdays REST Service (Spring Boot)

Väike Spring Boot teenus, mis salvestab POST päringuga saadetud JSON andmebaasi (H2, JPA).

## Käivitamine

### Eeldused
- Java 17+
- Maven 3.9+

```bash
mvn spring-boot:run
# või
mvn clean package && java -jar target/birthdays-service-0.0.1-SNAPSHOT.jar
```

Rakendus käivitub porti `8080`.

## API

### POST /api/v1/persons
Salvestab isiku.
Body (JSON):
```json
{
  "birthDate": "2000-06-22",
  "name": "John McClane"
}
```
Vastuse staatus: `201 Created` ja Location päis.

### GET /api/v1/persons
Tagastab kõik.

### GET /api/v1/persons/{id}
Tagastab ühe.

### DELETE /api/v1/persons/{id}
Kustutab.

## Näidis CURL
```bash
curl -X POST http://localhost:8080/api/v1/persons   -H "Content-Type: application/json"   -d '{"birthDate":"2000-06-22","name":"John McClane"}'

curl http://localhost:8080/api/v1/persons
```

## H2 Console
Aadress: `http://localhost:8080/h2-console`  
JDBC URL: `jdbc:h2:mem:birthdays`
