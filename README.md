# Pets App

Este proyecto es una aplicación simple para mostrar un listado de mascotas.

Está compuesto por dos partes principales:

- **Backend (API REST en Java Spring Boot):** expone un endpoint `/pet/list` que devuelve una lista de mascotas en formato JSON.
- **Frontend (PHP puro):** consume la API y muestra el listado en una tabla usando Bootstrap para el estilo.

## ¿Cómo funciona?

1. El backend se ejecuta en Java y responde peticiones HTTP con información de mascotas.
2. El frontend, hecho en PHP, solicita los datos al backend y los muestra en una tabla en una página web.


## EXAMEN.. PASO A PASO Y DOCUMENTACIÓN

1. Lo primero que he hecho ha sido leer el examen lentamente, entiendo todos los puntos e intentar organizarlo de la mejor manera posible.

2. He creado los .properties de NEON y de LOCAL, poniendole su respectivo contenido. En el .properties original, he puesto el perfil que quiero que se inicie en mi docker-compose. En este caso, el local con el comando spring.profiles.active = local.

3. Acto seguido, he creado el Dcokerfile compartido entre neon y local, ambos basados en SpringBoot

4. He creado 2 archivos docker-compose.yml, uno para neon y otro para local. En el dockercompose de neon he puesto el código prestado por el maestro, eliminando 3 líenas de código. como el depends on:db:contion:service_healthy, ya que al neon ser una base de datos en la nube, no necesitamos montarnos un contenedor de neon. En cambio, como en local estamos usando MYSQL, necesitamos traernos la imagen y toda su información. Este no he podido levantarlo, ya que me esta dando un error de undefined voluma db_data el cual no se solucionar, pero sé que me he quedado muy cerca

5. Una vez los dos contenedores esten levantados, deberiamos verificar su funcionamiento. El contender NEON se que funciona correctamente, pero el local no. Sería poner en el .properties original que se inciara el perfil de neon, pero por falta de tiempo no puedo y me veo obligado a redactarlo todo.

6. Hemos subido a GitHub toda la data a un repositorio nuevo, con varias ramas. La rama feature/local donde tenemos la produccion local, la rama feauture/neon, en el cual tenemos la produccion con la base de datos neon en la nube. Y todo nuestro proyecto mergeado en el main basado en SpringBoot
