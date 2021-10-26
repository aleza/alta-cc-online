# Alta de Cuenta Corriente Online

Aplicación basada en el repository [template-java-spring](https://github.com/lorfinsa/template-java-spring). 
Con Spring Framework y Spring Boot 2.2.5, estructurada en 3 capas.
Contiene chequeos en el momento de compilación de código limpio y de cobertura mediante tests.

## Dependencias

- BD MySQL 8+
- Maven 3+

## Documentación

[Documentación técnica](/doc)

## Requisitos

* Java 8 configurado en variable de entorno JAVA_HOME

## Cómo correrla

### Con Netbeans
- Configurar el profile `local` para que use application-local.properties
  - Ir a Propiedades del proyecto > Run
  - En VM Options agregar: `-Dspring.profiles.active=local`
  - Si hace falta sobrescribir alguna property privada, hacerlo de la misma manera, anteponiendo `-D`

### Con Java
- Compilar: `./mvnw clean package`
- Ejecutar: `java -jar target/app.jar`

### Con Docker
- Compilar imagen: `docker build -t app:0.0.1 .`
- Ejecutar container: `docker run -d -p 8080:8080 -v ./src/main/resources:/app/config app:0.1.1`

### Reportes

Correr `./mvnw clean package site`. Los reportes quedarán en `/target/site/project-reports.html`

### Configuración externa

https://docs.spring.io/spring-boot/docs/current/reference/html/spring-boot-features.html#boot-features-external-config

[application.properties](/src/main/java/resources/application-prod.properties)

## CI

El archivo Jenkinsfile indica que se va a utilizar un pipeline compartido, configurado en la propia instancia de Jenkins
# alta-cc-online
