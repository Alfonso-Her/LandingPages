# Contexto del Proyecto: Plataforma de Validación SaaS

## Resumen
Este proyecto es un **monorepo dockerizado** diseñado para la creación ágil de **landing pages** optimizadas para **SEO** y **viralidad**. El objetivo principal es validar ideas de negocio y SaaS de manera rápida y eficiente, bajo una filosofía de "David contra Goliat": maximizar impacto con recursos limitados. El código debe ser escalable, mantenible y seguir el principio **DRY** (Do Not Repeat Yourself).
La idea actual no es comercializar esta plataforma, sino que es un proyecto pensando para que yo valide mis propias ideas de negocio y SaaS de manera rápida y eficiente. Si mas adelante es un proyecto que crea que puede tener interes lo sacaremos mas tarde de momento genera todos los datos con preguntas como si estuviesemos creando una landing page para I love pdf.

## Stack Tecnológico
- **Frontend**: Svelte (JS, HTML, CSS) BUN 
- **Backend**: Go (Golang)
- **Base de Datos**: Postgres (Desarrollo posterior)
- **Infraestructura**: Docker & Docker Compose

## Características Clave
1.  **Navegación Interactiva**: Menús basados en preguntas para guiar al usuario.
2.  **Registro Simplificado**: Autenticación y registro únicamente mediante email.
3.  **Presentación de Ideas**: Campos y componentes específicos para exponer propuestas de valor.
4.  **Monitoreo**: Tracking del comportamiento del usuario en la web.
5.  **Diseño Modular**: Biblioteca de componentes para generar variedad de diseños de landing pages.
6.  **Feedback**: Entradas y cajón de sugerencias.
7.  **SEO & Viralidad**: Optimización técnica para posicionamiento orgánico.

## Requerimientos Técnicos
- Arquitectura de microservicios simplificada en monorepo.
- Sistema de componentes reutilizables en Svelte.
- API RESTful en Go para gestión de usuarios y datos.
- Persistencia de datos en Postgres.
- Despliegue contenerizado.
