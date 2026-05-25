# 🏗️ Arquitectura de Software
La memoria técnica del sistema se basa en un diseño modular que permite la escalabilidad institucional.

## Diagrama de Contenedores (C4 Model)
Este diagrama se renderiza dinámicamente:

![Arquitectura](https://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/TuUsuarioGithub/RutaCultural/main/docs/arquitectura/sistema.puml)

**Componentes Principales:**
* **Web Frontend:** Interfaz en React para el ciudadano.
* **API Gateway:** Punto único de entrada para seguridad y tráfico.
* **Servicio de Inventario:** Gestión de productos en PostgreSQL.

Arquitectura de Software — Ruta Cultural
Memoria Técnica Operativa y Estructura de Contenedores (Modelo C4)

El presente documento describe la arquitectura técnica del sistema Ruta Cultural. El diseño se fundamenta
en un modelo modular e independiente que garantiza la escalabilidad institucional, la mantenibilidad del
código y una clara separación de responsabilidades para optimizar la experiencia de usuario (UI/UX) y la
geolocalización de comercios locales.

1. Modelo de Contenedores (C4 Model)
Para la visualización de la arquitectura se adopta el Modelo C4, específicamente el nivel 2 (Diagrama de
Contenedores). Este nivel detalla la forma en que la aplicación está fragmentada en subsistemas operativos,
cómo interactúan entre sí y las tecnologías elegidas para el almacenamiento y transferencia de datos.
El diagrama se renderiza de forma dinámica en entornos Markdown (como repositorios de GitHub) utilizando
la sintaxis de PlantUML procesada a través de un proxy de renderizado directo. Esto asegura que cualquier
modificación en el archivo fuente de la arquitectura se refleje en tiempo real sin necesidad de precompilar
imágenes estáticas.

2. Componentes Principales del Sistema
La infraestructura lógica está segmentada en tres componentes primarios distribuidos, encargados del ciclo
de vida de los datos desde la interfaz del ciudadano hasta el almacenamiento persistente:
Contenedor /
Componente Tecnología Base Responsabilidad Operativa
Web Frontend React / JavaScript Interfaz de cara al usuario o ciudadano. Soportada sobre
pautas modernas de UI/UX, gestiona la visualización del
mapa interactivo, aplicación de filtros de búsqueda,
consumo de servicios y renderizado dinámico de la oferta
gastronómica y artesanal.

API Gateway Node.js / Express Punto único de entrada y orquestación para todas las
peticiones del cliente. Actúa como capa intermedia
encargada de la seguridad, validación de peticiones,
enrutamiento del tráfico hacia los microservicios
correspondientes y balanceo básico de carga.

Servicio de Inventario PostgreSQL /
PostGIS

Núcleo lógico enfocado en la administración integral de los
productos, comercios, artesanías y geolocalización. Utiliza
extensiones relacionales para optimizar búsquedas
basadas en coordenadas geográficas.

1

3. Especificación del Código de Arquitectura (PlantUML)
A continuación se expone la estructura formal en código PlantUML que define las relaciones, límites e
interacciones de los contenedores que componen el ecosistema de la aplicación:
sistema.puml

4. Integración y Renderizado Dinámico en GitHub
Para asegurar que este diagrama se visualice como un elemento nativo dentro del archivo README.md o
arquitectura.md del repositorio de GitHub, se implementa una referencia directa al servidor proxy oficial
de PlantUML. El formato Markdown estructurado que vincula el código fuente remoto es el siguiente:
Fragmento para arquitectura.md
@startuml "sistema"
!include https://raw.githubusercontent.com/plantuml-stdlib/C4-PlantUML/master/
C4_Container.puml
LAYOUT_WITH_LEGEND()
Person(ciudadano, "Ciudadano / Turista", "Usuario final que consulta las rutas,
gastronomía y artesanías locales.")
System_Boundary(ruta_cultural, "Sistema Ruta Cultural") {
Container(web_frontend, "Web Frontend", "React, JS", "Proporciona la interfaz
interactiva, mapas y filtros de comercios para el usuario.")
Container(api_gateway, "API Gateway", "Node.js, Express", "Punto único de entrada.
Gestiona la seguridad, autenticación y enrutamiento de peticiones.")
Container(servicio_inventario, "Servicio de Inventario", "Python / Node.js", "Maneja
la lógica de negocio asociada a productos, rutas y geolocalización.")
ContainerDb(base_datos, "Base de Datos", "PostgreSQL / PostGIS", "Almacena la
información de usuarios, comercios, coordenadas y catálogos artesanales.")
}
Rel(ciudadano, web_frontend, "Interactúa y consulta rutas usando", "HTTPS")
Rel(web_frontend, api_gateway, "Consume servicios y envía eventos a", "HTTPS / JSON")
Rel(api_gateway, servicio_inventario, "Orquesta y delega peticiones a", "gRPC / HTTP")
Rel(servicio_inventario, base_datos, "Lee y escribe datos en", "SQL / TCP")
@enduml

## Diagrama de Contenedores (C4 Model)
Este diagrama se renderiza dinámicamente:
![Arquitectura](https://www.plantuml.com/plantuml/proxy?cache=no&src=https://
raw.githubusercontent.com/TuUsuarioGithub/RutaCultural/main/docs/arquitectura/
sistema.puml)

2

Este enfoque metodológico evita el desfase clásico de la documentación de software, manteniendo la
arquitectura viva, versionada mediante Git y legible directamente desde cualquier navegador web sin
necesidad de extensiones propietarias.