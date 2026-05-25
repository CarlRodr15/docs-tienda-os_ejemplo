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

@startuml C4_Container
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/C4_Container.puml

title Ruta Cultural - Diagrama de Contenedores

Person(turista, "Turista")
Person(emprendedor, "Emprendedor Local")
Person(admin, "Administrador")

System_Boundary(system, "Ruta Cultural") {

    Container(web, "Aplicación Web", "HTML, CSS, JavaScript", "Interfaz para turistas y emprendedores.")

    Container(api, "API Backend", "Python - Flask/FastAPI", "Gestiona lógica de negocio y reglas del sistema.")

    ContainerDb(db, "Base de Datos", "PostgreSQL / MySQL", "Almacena emprendimientos, productos, horarios y usuarios.")

    Container(auth, "Módulo de Autenticación", "Python", "Gestiona inicio de sesión y control de acceso.")

    Container(media, "Gestor Multimedia", "Python", "Administra imágenes de productos y emprendimientos.")

}

System_Ext(maps, "Google Maps / OpenStreetMap", "Ubicación y rutas.")
System_Ext(github, "GitHub", "Repositorio y control de versiones.")

Rel(turista, web, "Consulta información")
Rel(emprendedor, web, "Gestiona emprendimientos")
Rel(admin, web, "Administra plataforma")

Rel(web, api, "Consume API REST", "JSON/HTTPS")

Rel(api, db, "Lee y escribe datos", "SQL")
Rel(api, auth, "Valida usuarios")
Rel(api, media, "Gestiona imágenes")
Rel(api, maps, "Consulta ubicaciones y rutas")

Rel(api, github, "Despliegue y control de versiones")

@enduml