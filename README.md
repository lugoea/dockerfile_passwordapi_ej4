**1.- Crear el Dockerfile**

```plaintext
FROM openjdk:11
COPY . /usr/src/passwordapi
WORKDIR /usr/src/passwordapi
EXPOSE 8080
RUN addgroup --system --gid 1001 appuser
RUN adduser  --system --uid  1001   --group appuser
RUN  chown -R appuser:appuser /usr/src/passwordapi
CMD ["java","-jar","passwordapi.jar"]
```

**2.- Construir la imagen**

```plaintext
    $ docker build -t my-password-api .
```

**3.- Correr la imagen**

```plaintext
    $ docker run -it --rm --name running-passwordapi -p 8080:8080 my-password-api
```

**4.- Crear el repo en Dockerhub**

**5.- Aplicar el tag a la imagen**

```plaintext
    docker tag 0fa2d6fab826 elugo/taller-docker-ejercicio4:1.0.0
```

**6.- Hacer Login en docker**

    docker login

    Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.

    Username: elugo

    Password:

    Login Succeeded

  
**7.- Hacer el push a la imagen**

```plaintext
    docker push elugo/taller-docker-ejercicio4:1.0.0
```

**Link**

    https://hub.docker.com/r/elugo/taller-docker-ejercicio4/tags
