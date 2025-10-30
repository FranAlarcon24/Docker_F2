# Empezando Docker

Este proyecto es una aplicación Java que utiliza Docker para facilitar su construcción y despliegue. A continuación se detallan los componentes principales del proyecto y cómo trabajar con ellos.

## Estructura del Proyecto

```
empezando-docker
├── .github
│   └── workflows
│       └── ci.yml          # Flujo de trabajo de integración continua
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── example
│   │   │           └── App.java  # Clase principal de la aplicación
│   │   └── resources
│   │       └── application.properties  # Configuración de la aplicación
│   └── test
│       └── java
│           └── com
│               └── example
│                   └── AppTest.java  # Pruebas unitarias para la clase App
├── Dockerfile                  # Instrucciones para construir la imagen Docker
├── pom.xml                    # Configuración de Maven
├── .gitignore                 # Archivos y directorios a ignorar por Git
└── README.md                  # Documentación del proyecto
```

## Requisitos

- Java 21
- Maven 3.9.9
- Docker

## Construcción de la Aplicación

Para construir la aplicación, asegúrate de tener Maven instalado y ejecuta el siguiente comando en la raíz del proyecto:

```
mvn clean package
```

Esto generará un archivo JAR en el directorio `target`.

## Ejecución de la Aplicación

Para ejecutar la aplicación, puedes usar Docker. Primero, construye la imagen Docker con el siguiente comando:

```
docker build -t nombre-de-tu-imagen .
```

Luego, ejecuta la imagen:

```
docker run -p 8080:8080 -e PORT=8080 nombre-de-tu-imagen
```

La aplicación estará disponible en `http://localhost:8080`.

## Pruebas

Las pruebas unitarias se encuentran en el directorio `src/test/java/com/example/AppTest.java`. Para ejecutarlas, utiliza el siguiente comando:

```
mvn test
```

## Contribuciones

Las contribuciones son bienvenidas. Si deseas contribuir, por favor abre un issue o envía un pull request.

## Licencia

Este proyecto está bajo la licencia MIT.