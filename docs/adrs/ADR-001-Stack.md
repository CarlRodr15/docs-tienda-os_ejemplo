---
title: ADR 001 — Selección del Stack Tecnológico
---

# ADR 001: Selección del Stack Tecnológico

**Fecha:** 25 de Mayo de 2026  
**Estado:** Aceptado  

## Contexto
El proyecto **Ruta Cultural** requiere una plataforma web interactiva capaz de geolocalizar comercios tradicionales, calcular trayectos de interés en tiempo real y mostrar catálogos gastronómicos y artesanales de manera fluida. Necesitamos un stack que soporte el procesamiento de datos geográficos y garantice una experiencia de usuario (UI/UX) ágil en dispositivos móviles y de escritorio.

## Decisión
Se selecciona el siguiente stack tecnológico principal:
* **Frontend:** React (JavaScript) para construir una interfaz reactiva e interactiva.
* **Backend:** Python debido a su eficiencia en lógica de negocio y su facilidad de integración con librerías de datos.
* **Base de Datos:** PostgreSQL con la extensión **PostGIS** para el manejo nativo de coordenadas espaciales, distancias y geocercas.
* **Documentación:** MkDocs y Redocly bajo el enfoque *Docs as Code* para automatizar el portal técnico.

## Consecuencias
* **Positivas:** El uso de PostGIS optimiza las consultas de mapas reduciendo la carga del servidor. React permite que los filtros por categorías se sientan instantáneos para el turista.
* **Negativas:** Requiere una curva de aprendizaje inicial para la configuración de las extensiones de bases de datos espaciales y el entorno virtual de Python.