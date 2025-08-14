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


**Märkus:** See versioon sisaldab ainult POST teenust vastavalt algsele ülesandele.
