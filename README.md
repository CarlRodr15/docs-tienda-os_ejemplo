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