# Simulación de Menú Digital - Confitería Paradiso

## Descripción General
Este proyecto consiste en un sitio web estático desarrollado para el lugar ficticio **Confitería Paradiso**. Presenta una carta/menú interactivo y *responsive* donde se puede navegar de forma intuitiva por distintas categorías de productos: Cafetería, Bebidas, Dulces, Tortas y Sandwiches. 

El proyecto fue desarrollado como parte de un Trabajo Práctico Integrador para la materia Ingeniería de Software, aplicando prácticas de control de versiones mediante **Git** y contenedorización de aplicaciones con **Docker** servido sobre un servidor de alto rendimiento (**Nginx**).

---

## Estructura del Proyecto

```text
.
├── index.html        # Estructura principal del sitio web
├── styles.css        # Estilos y diseño responsive (CSS Grid, Flexbox)
├── Dockerfile        # Configuración para la creación de la imagen Docker
├── README.md         # Documentación general del proyecto
└── imgs/             # Directorio con las imágenes de los productos
```

---

## Tecnologías Utilizadas

* **HTML5:** Estructuración semántica de la página web.
* **CSS3:** Diseño responsivo, fuentes personalizadas y estilos modernos mediante variables CSS y Grid.
* **Git & GitHub:** Control de versiones del código fuente.
* **Docker:** Plataforma para la contenedorización de la aplicación.
* **Nginx (Alpine Linux):** Servidor web ligero utilizado como imagen base en el contenedor.

---

## Requisitos Previos

Para ejecutar la aplicación mediante contenedores se requiere:
* **Docker Engine** o **Docker Desktop** instalado en tu sistema.
* **Git** (opcional, para clonar el repositorio).

---

## Instrucciones de Construcción y Ejecución con Docker

Sigue estos pasos para construir la imagen e iniciar el contenedor en tu entorno local:

### 1. Clonar el Repositorio
```bash
git clone https://github.com/jibonaventura/TP-IdS-ISTEA.git
cd TP-IdS-ISTEA
```

### 2. Construir la Imagen Docker
Ejecuta el siguiente comando en la raíz del proyecto (donde se encuentra el archivo `Dockerfile`):

```bash
docker build -t confiteria-paradiso:v1 .
```

### 3. Ejecutar el Contenedor
Inicia el contenedor mapeando el puerto `8080` de tu máquina host al puerto `80` expuesto por Nginx dentro del contenedor:

```bash
docker run -d -p 8080:80 --name menu-paradiso confiteria-paradiso:v1
```

### 4. Acceder al Sitio Web
Abre tu navegador e ingresa a la siguiente dirección:
```text
http://localhost:8080
```

---

## Comandos Útiles de Docker

* **Ver el contenedor en ejecución:**
  ```bash
  docker ps
  ```
* **Detener el contenedor:**
  ```bash
  docker stop menu-paradiso
  ```
* **Eliminar el contenedor:**
  ```bash
  docker rm menu-paradiso
  ```