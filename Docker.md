# Servidores web ngnix docker

## Tiempo de duracion:

50 minutos

## Fundamentos:

La virtualización mediante contenedores se ha convertido en un pilar fundamental en el desarrollo moderno de aplicaciones. Docker simplifica este proceso al ofrecer una plataforma que encapsula aplicaciones y sus dependencias en unidades estandarizadas llamadas contenedores, garantizando consistencia en diferentes entornos.

En el ecosistema de servidores web, Nginx destaca como una solución robusta y versátil. Su arquitectura basada en eventos lo hace excepcionalmente eficiente en el manejo de conexiones concurrentes, mientras que su capacidad como proxy inverso y balanceador de carga lo convierte en una herramienta indispensable en infraestructuras modernas.

Esta práctica combina estas dos tecnologías utilizando Docker Playground, un entorno sandbox que permite experimentar con contenedores de manera segura. Se implementarán dos instancias de Nginx, cada una sirviendo contenido único, demostrando la flexibilidad y portabilidad de los contenedores.

Los comandos esenciales de Docker que utilizaremos son:

- `docker run`: para crear y ejecutar contenedores.
- `docker cp`: para copiar archivos entre el host y el contenedor.
- `docker exec`: para ejecutar comandos dentro de un contenedor en ejecución.

**Figura 1-1. Diagrama de contenedores desplegados en Docker Playground**

![image.png](Servidores%20web%20ngnix%20docker%201d4924d6dc5b80bbae97cfd2a5e296c8/image.png)

## **Conocimientos previos**

Para aprovechar al máximo esta experiencia práctica, es necesario dominar los siguientes aspectos:

- Familiaridad con instrucciones de consola UNIX (manipulación de archivos y directorios)
- Experiencia en el manejo de interfaces de línea de comandos
- Destrezas en el uso y configuración de navegadores web
- Comprensión de comunicaciones en red (direccionamiento IP, protocolos)
- Bases sólidas en arquitectura de servicios web
- Conocimientos básicos en tecnologías de virtualización

## Objetivo Alcanzar

- Configurar y desplegar instancias de Nginx utilizando la plataforma Docker
- Desarrollar y adaptar interfaces web personalizadas para cada servidor
- Explorar las mejores prácticas en la implementación de servicios web containerizados
- Dominar las operaciones básicas de gestión de contenedores Docker, mediante la terminal

## Equipo necesario

- Computador con sistema operativo Linux (Fedora)
- MSI Nvidia 4060 16GB 512G
- Terminal de comandos (WARP)
- Conexion a Internet
- Navegar web conpatible (Zen browser)

## Material de Apoyo:

- Documentación oficial de Docker: [https://docs.docker.com](https://docs.docker.com/)
- Guía de la asignatura mediante la plzataforma
- Videos tutoriales proporcionados por el docente
- Foro sobre dudas acerca del tema

## Procedimiento:

**Paso 1: Crear los contenedores**

```
sudo docker run -d --name nginx1 -p 8089:80 nginx
sudo docker run -d --name nginx2 -p 8090:80 nginx
```

**Paso 2: Copiar el archivo index.html al host (anfitrión)**

```
sudo docker cp nginx1:/usr/share/nginx/html/index.html ./index1.html
sudo docker cp nginx2:/usr/share/nginx/html/index.html ./index2.html
```

**Paso 3: Editar los archivos HTML vi**

```
vi index1.html
```

```
vi index2.html
```

**Paso 4: Para borrar el contenido utilizamos**

```bash
:%d
```

Remplazmos el index1.html por:

```jsx
<!DOCTYPE html>
<html>
<head>
<title>Bienvenido a instituto Tecnológico Sudamericano</title>
</head>
<body>
<h1>Separte de cambio ven inscribete en el TEC aqui podras ioptener un titulo de tercer nivel se parte del cambio  </h1>
<p>Contamos con amplias carreras  </p>
</body>
</html>
```

index2.html – Personal

```jsx
<!DOCTYPE html>
<html>
<head>
  <title>Perfil Estudiante</title>
</head>
<body>
  <h1>Elkin Sebastian Carriel Cepeda</h1>
  <p>Tengo 19 yeras old me gusta tocar la guitarra soy studiante del instituto tecnologico sudamericano</p>
</body>
</html>
```

Luego para guardar y salir se coloco:

```docker
:wq!
```

**Paso 5: Copiar los archivos editados de regreso al contenedor**

```
sudo docker cp index1.html nginx1:/usr/share/nginx/html/index.html
sudo docker cp index2.html nginx2:/usr/share/nginx/html/index.html
```

**Paso 6: Ver los resultados en el navegador**

```docker
Localhost:8089
Localhost:8090
```

**Resultados Esperados**

Al acceder al navegador por los puertos expuestos, se debe visualizar:

![Screenshot_20250412_233804.png](Servidores%20web%20ngnix%20docker%201d4924d6dc5b80bbae97cfd2a5e296c8/596d3519-555e-4d71-9018-86e65f5d2c87.png)

![Screenshot_20250412_234253.png](Servidores%20web%20ngnix%20docker%201d4924d6dc5b80bbae97cfd2a5e296c8/e2e2f320-16cd-40ec-b487-6079ae20bfb9.png)

**Audio-Resumen**

[WhatsApp Audio 2025-04-12 at 23.46.22.mp4](Servidores%20web%20ngnix%20docker%201d4924d6dc5b80bbae97cfd2a5e296c8/WhatsApp_Audio_2025-04-12_at_23.46.22.mp4)

# **Bibliografia**

Dock, M. (2023, 15 junio). Play with Docker | Docker. Docker. [https://www.docker.com/play-with-docker/](https://www.docker.com/)
Ronk, D. (2022, 24 febrero). Getting Started with Docker: Docker Playground. DEV Community. [https://dev.to/dronk6/getting-started-with-docker-docker-playground-28h3](<https://es.wikipedia.org/wiki/Docker_(software)>)
¿Qué es Docker y cómo funciona? Ventajas de los contenedores Docker. (s. f.). [https://www.redhat.com/es/topics/containers/what-is-docker](https://www.ibm.com/es-es/think/topics/docker)
Ratliff, S. (2025, 23 enero). Docker: Accelerated Container Application Development. Docker. [https://www.docker.com/](https://www.docker.com/)
