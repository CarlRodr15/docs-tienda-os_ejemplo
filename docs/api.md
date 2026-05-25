---
hide:
  - toc
---
<style>
  /* Forza a MkDocs a usar todo el ancho de la pantalla solo en esta página */
  .md-content { max-width: 100% !important; }
</style>

# 🔌 Contrato de la API

A continuación se detalla la especificación técnica y los endpoints disponibles para integración.

<redoc spec-url="/docs-tienda-os_ejemplo/api/api-new.yaml"></redoc>
<script src="https://cdn.redoc.ly/redoc/latest/bundles/redoc.standalone.js"></script>

Para documentar las APIs de **Ruta Cultural** de forma elegante, corta y estrictamente **funcional**, lo mejor es estructurarlo en formato **OpenAPI / Swagger simplificado** usando Markdown. Esto le permite a cualquier desarrollador (o a ti misma al programar los endpoints en Python) saber exactamente qué enviar y qué esperar.

Aquí tienes el diseño del archivo `api_docs.md` listo para producción:

---

# 🔌 Documentación de la API — Ruta Cultural

Esta es la especificación técnica de los endpoints principales del sistema. La URL base para el entorno de desarrollo es: `http://localhost:5000/api/v1`.

---

## 🍔 1. Módulo de Comercios y Gastronomía

### `GET /comercios`

Devuelve la lista completa de comercios aliados (restaurantes de cocina de nostalgia, artesanías, etc.) con soporte para filtros de búsqueda.

* **Query Parameters (Opcionales):**
* `categoria`: Filtrar por tipo (ej. `gastronomia`, `artesanias`).
* `destacado`: Filtrar por relevancia (`true`/`false`).


* **Respuesta Exitosa (`200 OK`):**

```json
[
  {
    "id": 1,
    "nombre": "La Cuchara de Palo",
    "categoria": "gastronomia",
    "descripcion": "Cocina de nostalgia con recetas tradicionales y sabores auténticos.",
    "destacado": true
  }
]

```

---

## 📍 2. Módulo de Geolocalización y Rutas

### `GET /ubicaciones`

Obtiene las coordenadas geográficas de los puntos de interés para renderizar en el mapa interactivo del frontend.

* **Respuesta Exitosa (`200 OK`):**

```json
[
  {
    "comercio_id": 1,
    "nombre": "La Cuchara de Palo",
    "latitud": 3.9312,
    "longitud": -76.4856,
    "direccion": "Calle Principal, Calima El Darién"
  }
]

```

### `POST /rutas/calcular`

Calcula un trayecto sugerido uniendo diferentes puntos del mapa basados en la ubicación del usuario.

* **Cuerpo de la Petición (`Request Body`):**

```json
{
  "usuario_lat": 3.9300,
  "usuario_lng": -76.4800,
  "categoria_interes": "gastronomia"
}

```

* **Respuesta Exitosa (`201 Created`):**

```json
{
  "ruta_id": "ruta_987",
  "distancia_total_km": 1.5,
  "tiempo_estimado_min": 18,
  "paradas": [
    { "orden": 1, "nombre": "Punto de Origen" },
    { "orden": 2, "nombre": "La Cuchara de Palo" }
  ]
]

```

---

## 📦 3. Módulo de Catálogo de Productos

### `GET /comercios/{id}/productos`

Lista las artesanías o platos específicos disponibles en un comercio determinado.

* **Respuesta Exitosa (`200 OK`):**

```json
{
  "comercio": "La Cuchara de Palo",
  "productos": [
    {
      "id": 101,
      "nombre": "Plato Tradicional de Antaño",
      "precio": 25000,
      "disponible": true
    }
  ]
}

```

---

## ⚠️ Respuestas de Error Estándar

Cualquier fallo en las peticiones devolverá una estructura unificada para facilitar el manejo de errores en el frontend (UI/UX):

| Código | Estado | Razón | Ejemplo de Mensaje |
| --- | --- | --- | --- |
| `400` | Bad Request | Parámetros inválidos o faltantes. | `{"error": "Las coordenadas lat/lng son obligatorias"}` |
| `404` | Not Found | El recurso solicitado no existe. | `{"error": "El comercio especificado no fue encontrado"}` |
| `500` | Internal Error | Error inesperado en el servidor. | `{"error": "Error interno al conectar con PostGIS"}` |

---

¿Este set de endpoints inicial cubre las necesidades del prototipo de la app, o te gustaría añadir de una vez el flujo para que los negocios se registren?