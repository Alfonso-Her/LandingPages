# LandingPages

Plataforma de Validación SaaS diseñada para crear landing pages optimizadas para SEO y viralidad.

## Filosofía del Proyecto
El objetivo principal es validar ideas de negocio de manera rápida y eficiente, bajo una filosofía de **"David contra Goliat"**: maximizar el impacto con recursos limitados.

### Lógica de Negocio y Características
1.  **Validación Ágil**: Creación rápida de landing pages para testear propuestas de valor.
2.  **Navegación Interactiva**: Menús basados en preguntas para guiar al usuario y aumentar el engagement.
3.  **Captura de Leads**: Registro simplificado (solo email) para minimizar la fricción.
4.  **SEO y Viralidad**: Arquitectura optimizada para posicionamiento orgánico y compartición social.
5.  **Diseño Modular**: Biblioteca de componentes Svelte para generar variedad de diseños manteniendo la consistencia.

## Stack Tecnológico

- **Frontend**: Svelte (Bun)
- **Backend**: Go
- **Base de Datos**: Postgres
- **Infraestructura**: Docker & Docker Compose

## Requisitos Previos

- [Docker](https://www.docker.com/)
- [Bun](https://bun.sh/) (Opcional, para desarrollo local fuera de Docker)
- [Go](https://go.dev/) (Opcional, para desarrollo local fuera de Docker)

## Configuración y Ejecución

1.  **Clonar el repositorio**:
    ```bash
    git clone <url-del-repo>
    cd LandingPages
    ```

2.  **Levantar servicios con Docker Compose**:
    ```bash
    docker-compose up --build
    ```

    Esto iniciará:
    - Frontend en `http://localhost:5173`
    - Backend en `http://localhost:8080`
    - Postgres en el puerto `5433`

## Estructura del Proyecto

- `/frontend`: Código fuente de la aplicación Svelte.
- `/backend`: Código fuente del servidor API en Go.
- `/postgres`: Configuración y scripts de la base de datos.
- `docker-compose.yml`: Orquestación de contenedores.
