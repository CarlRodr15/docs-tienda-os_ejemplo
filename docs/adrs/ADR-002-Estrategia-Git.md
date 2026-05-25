---
title: ADR 002 — Estrategia de Git y Flujo de Trabajo
---

# ADR 002: Estrategia de Control de Versiones con Git

**Fecha:** 25 de Mayo de 2026  
**Estado:** Aceptado  

## Contexto
Al ser un proyecto modular con carpetas separadas para `frontend`, `backend` y `docs`, necesitamos organizar las contribuciones al repositorio de GitHub de manera ordenada. Esto evitará conflictos en el código fuente, pérdidas de información y mantendrá un historial de cambios limpio y legible.

## Decisión
Se adopta la estrategia de ramificación **GitFlow simplificada**:
* **Rama `main`:** Aloja únicamente código estable listo para producción o entrega académica.
* **Rama `develop` o ramas de características (`feature/`)**: Cada módulo nuevo (como el mapa, el catálogo o la documentación de las APIs) se desarrolla en una rama independiente antes de unirse a la línea principal mediante *Pull Requests*.

## Consecuencias
* **Positivas:** Permite trabajar en el diseño de las APIs o en los estilos visuales del frontend sin romper las partes del sistema que ya están funcionando.
* **Negativas:** Obliga a realizar fusiones (`merges`) constantes y a mantener una disciplina estricta al usar comandos de la terminal para actualizar el repositorio local.