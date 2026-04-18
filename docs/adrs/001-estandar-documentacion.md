# ADR 001: Implementación de Documentación como Código (Docs as Code)

* **Estado:** Aceptado
* **Fecha:** 18 de abril de 2026
* **Relacionado con:** Fase 4 - Integración Sistémica

---

## 1. Contexto (El Problema)
Nosotros necesitamos centralizar toda la información técnica del proyecto (README, guías de onboarding, diagramas y decisiones de arquitectura) en un solo lugar que sea accesible, profesional y que no se desactualice con el tiempo.

Tradicionalmente, la documentación se hace en archivos de Word dispersos, lo que causa la "amnesia técnica" del equipo al no saber por qué se tomaron ciertas decisiones.

## 2. Decisión (La Solución)
Hemos decidido adoptar la metodología **Docs as Code** utilizando las siguientes herramientas:

* **MkDocs:** Como generador de sitios estáticos para convertir archivos Markdown en este portal web. 
* **GitHub Actions:** Para automatizar el despliegue (Pipeline CI/CD). Cada vez que hagamos un `git push`, el portal se actualizará solo.
* **ADRs (Architecture Decision Records):** Para registrar formalmente cada decisión técnica importante y evitar la pérdida de conocimiento.

## 3. Consecuencias

### Positivas (+)
* **Única fuente de verdad:** Todo el equipo consulta el mismo portal (DevDocs Hub).
* **Historial versionado:** Podemos ver cómo evolucionó la documentación junto con el código. 
* **Profesionalismo:** El portal cuenta con buscador integrado, navegación fluida y diseño adaptable para móviles.

### Negativas (-)
* **Curva de aprendizaje:** El equipo debe aprender la sintaxis Markdown y la estructura de archivos YAML para configurar el portal.
* **Dependencia técnica:** Si el Pipeline de GitHub falla, el portal no se actualizará hasta que se corrija el error en el código.

---
*Este registro asegura la transparencia técnica y facilita el Onboarding de nuevos miembros al equipo de Calima El Darién.*