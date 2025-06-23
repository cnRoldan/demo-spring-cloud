# Demo Spring Cloud Config

Este repositorio es un ejemplo sencillo de un **repositorio de configuración** para aplicaciones basadas en Spring Cloud. Solo contiene archivos `.properties` que definen la configuración de dos microservicios, cada uno con una variante para el entorno `dev`.

## Estructura

```
./
├── artefacto1.properties
├── artefacto1-dev.properties
├── artefacto2.properties
└── artefacto2-dev.properties
```

- **artefacto1.properties**: Configuración principal del artefacto 1.
- **artefacto1-dev.properties**: Variante para el perfil `dev` del artefacto 1.
- **artefacto2.properties**: Configuración principal del artefacto 2.
- **artefacto2-dev.properties**: Variante para el perfil `dev` del artefacto 2.

Cada archivo define el puerto en el que corre el microservicio y, en algunos casos, propiedades adicionales como la exposición de endpoints de Actuator.

## Aspectos importantes

1. **Perfiles de entorno**
   Los archivos `*-dev.properties` se utilizan cuando está activo el perfil `dev`. Spring Boot combina estas propiedades con las generales según el nombre de la aplicación y los perfiles.

2. **Definición de puertos**
   Los puertos cambian entre producción y `dev` para que sea posible ejecutar los servicios simultáneamente sin conflictos.

3. **Actuator**
   El archivo `artefacto1.properties` expone endpoints de Actuator como `refresh`, `health` e `info`.

## Recomendaciones para seguir aprendiendo

1. **Spring Boot y Spring Cloud Config**
   Investiga cómo un servidor de configuración carga estos archivos y los envía a los microservicios. Presta atención a `spring.application.name` y `spring.profiles.active`.

2. **Buenas prácticas de configuración**
   Mantén la configuración separada por entornos y versiona los cambios para saber cuándo y por qué se modificaron.

3. **Microservicios en Spring**
   Este repositorio es solo una parte de un sistema de microservicios. Revisa un proyecto que consuma esta configuración para entender el proceso completo.

