# 🛒 OpenSource Store Template
> Sistema de gestión de inventarios y ventas basado en arquitecturas desacopladas.

![Version](https://img.shields.io/badge/Version-1.0.0--beta-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)
![Docs](https://img.shields.io/badge/Docs-As--Code-brightgreen?style=for-the-badge)

## 🚀 Onboarding en 3 Pasos
1. **Configuración:** `cp .env.example .env`
2. **Dependencias:** `npm install` o `pip install -r requirements.txt`
3. **Lanzamiento:** `npm start`

## 📊 Arquitectura del Sistema
A diferencia de un diagrama estático, aquí usamos **PlantUML** para asegurar que el diseño evolucione con el código:

![Diagrama de Arquitectura](https://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/CarlRodr15/docs-tienda-os_ejemplo/main/docs/arquitectura/c4_model.puml)

## 🧪 Validación de Calidad
```bash
npm run test:unit    # Pruebas de lógica de carrito
npm run test:e2e     # Pruebas de flujo de compra completo
```

---

### Paso 3: Los 10 ADRs (Materia: Avanzada)
Para la **Fase 4 de Avanzada**, crea 10 archivos dentro de `docs/adrs/`. Aquí tienes la lista de títulos y el contenido del primero como plantilla:

**Lista de archivos:**
`ADR-001-Stack.md`, `ADR-002-BaseDatos.md`, `ADR-003-Auth.md`, `ADR-004-Pagos.md`, `ADR-005-UI-Framework.md`, `ADR-006-API-Standard.md`, `ADR-007-Cloud-Provider.md`, `ADR-008-Branch-Strategy.md`, `ADR-009-Logging.md`, `ADR-010-Testing-Library.md`.

**Plantilla para `ADR-001-Stack.md`:**
```markdown
# ADR 001: Selección del Stack Tecnológico
**Fecha:** 2026-05-09
**Estado:** Aceptado

## Contexto
Necesitamos una tecnología que permita el despliegue rápido y tenga una comunidad amplia para soporte institucional.

## Decisión
Se elige **Node.js con Express** para el backend y **React** para el frontend.

## Consecuencias
*   **Positivo:** Facilidad de contratación de devs.
*   **Negativo:** Curva de aprendizaje inicial en Hooks.