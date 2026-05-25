# Arquitectura de Software
La memoria técnica del sistema se basa en un diseño modular que permite la escalabilidad institucional.

## Diagrama de Contenedores (C4 Model)
Este diagrama se renderiza dinámicamente:

![Arquitectura](https://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/TuUsuarioGithub/RutaCultural/main/docs/arquitectura/sistema.puml)

**Componentes Principales:**
* **Web Frontend:** Interfaz en React para el ciudadano.
* **API Gateway:** Punto único de entrada para seguridad y tráfico.
* **Servicio de Inventario:** Gestión de productos en PostgreSQL.

# 🏛️ Arquitectura de Software — Ruta Cultural

La memoria técnica del sistema se basa en un diseño modular que permite la escalabilidad, mantenibilidad y una correcta separación de responsabilidades para potenciar la experiencia del usuario (UI/UX) y la promoción del comercio local.

## 📊 Diagrama de Contenedores (C4 Model)
Este diagrama se renderiza dinámicamente en tiempo real desde el código fuente del repositorio utilizando el proxy oficial de PlantUML:

![Arquitectura de Ruta Cultural](https://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/TU_USUARIO_GITHUB/TU_REPOSITORIO/main/docs/arquitectura/sistema.puml)

---

### 🚀 Componentes Principales:

* 🌐 **Web Frontend:** Interfaz desarrollada en **React** construida bajo principios de UI/UX intuitivos para el ciudadano o turista. Permite la visualización de un mapa geolocalizado intermitente, aplicación de filtros avanzados y navegación interactiva por directorios comerciales.
* 🛡️ **API Gateway:** Desarrollado sobre **Node.js / Express**. Funciona como el punto único de entrada para todas las peticiones desde el cliente, centralizando políticas de seguridad, validación y gestión de tráfico.
* ⚙️ **Servicio de Inventario y Rutas:** Componente lógico desarrollado en **Python** encargado de procesar las búsquedas por categorías (gastronomía, artesanías), la lógica de negocio del catálogo de productos y el cálculo de trayectos culturales.
* 🗄️ **Base de Datos:** Motor relacional **PostgreSQL** con la extensión espacial **PostGIS** para el manejo optimizado de coordenadas geográficas, geocercas y posicionamiento de los comercios aliados.