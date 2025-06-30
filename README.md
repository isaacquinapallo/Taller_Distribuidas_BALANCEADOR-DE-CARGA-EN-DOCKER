# Taller_Distribuidas_BALANCEADOR-DE-CARGA-EN-DOCKER

Este proyecto fue desarrollado como parte del taller de Sistemas Distribuidos, con el objetivo de implementar un balanceador de carga utilizando Docker y Nginx, que distribuya peticiones entre tres aplicaciones web HTML estáticas.

## Tecnologías utilizadas

- **Docker**
- **Docker Compose**
- **Nginx** (como balanceador de carga)
- **Apache Httpd (httpd:alpine)** para servir cada aplicación

## Estructura del proyecto

```
.
├── docker-compose.yml
├── nginx.conf
├── app1/
│   └── index.html     --> Hoja de vida de Isaac Quinapallo
├── app2/
│   └── index.html     --> Hoja de vida del Compañero 1
├── app3/
│   └── index.html     --> Hoja de vida del Compañero 2
```

## Descripción de servicios

- `nginx`: balanceador de carga que redirige solicitudes entre los contenedores `app1`, `app2` y `app3` de forma **round-robin**.
- `app1`: contiene la hoja de vida de **Isaac Quinapallo**.
- `app2` y `app3`: contienen las hojas de vida de los compañeros del grupo.

## Ejecución del proyecto

1. Clona el repositorio:
   ```bash
   git clone https://github.com/tuusuario/Taller_Distribuidas_BALANCEADOR-DE-CARGA-EN-DOCKER.git
   cd Taller_Distribuidas_BALANCEADOR-DE-CARGA-EN-DOCKER
   ```

2. Construye y ejecuta los contenedores:
   ```bash
   docker-compose up -d
   ```

3. Accede desde el navegador:
   ```
   http://localhost:8080
   ```

   Al recargar la página, Nginx distribuirá la carga entre `app1`, `app2` y `app3`.

---

### Notas

- Asegúrate de que el puerto `8080` no esté en uso antes de ejecutar el proyecto.
- Puedes modificar el archivo `nginx.conf` para cambiar el comportamiento del balanceador.
