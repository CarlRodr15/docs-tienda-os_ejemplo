🚀 Guía de Instalación y Configuración
Sigue estos pasos para clonar el proyecto y ejecutarlo en tu entorno local.

📋 Prerrequisitos
Antes de comenzar, asegúrate de tener instalado en tu sistema:

Git (Para clonar el repositorio)

Node.js (Versión LTS recomendada)

Python (Versión 3.10 o superior)

PostgreSQL con la extensión PostGIS activa.

1. Clonar el Repositorio
Abre tu terminal y ejecuta el siguiente comando para traer el proyecto a tu máquina:

Bash
git clone https://github.com/TU_USUARIO/RutaCultural.git
cd RutaCultural
2. Configuración de la Base de Datos
Abre tu gestor de PostgreSQL (o usando psql en la terminal) y crea una base de datos llamada ruta_cultural_db.

Habilita la extensión espacial ejecutando la siguiente consulta:

SQL
CREATE EXTENSION postgis;
3. Configuración del Backend 🐍
Navega a la carpeta del servidor para instalar las dependencias y levantar la API:

Entrar al directorio:

Bash
cd backend
Crear y activar un entorno virtual (Recomendado para mantener las dependencias limpias):

En Windows:

Bash
python -m venv venv
.\venv\Scripts\activate
En macOS/Linux:

Bash
python3 -m venv venv
source venv/bin/activate
Instalar dependencias:

Bash
pip install -r requirements.txt
Configurar variables de entorno:
Crea un archivo llamado .env en la raíz de la carpeta backend y añade las credenciales de tu base de datos:

Fragmento de código
DB_HOST=localhost
DB_USER=tu_usuario_postgres
DB_PASSWORD=tu_contraseña
DB_NAME=ruta_cultural_db
PORT=5000
Iniciar el servidor:

Bash
python main.py
(El backend debería quedar corriendo en http://localhost:5000)

4. Configuración del Frontend 🌐
Abre una nueva pestaña o ventana de la terminal y regresa a la raíz del proyecto para configurar la interfaz de usuario:

Entrar al directorio del cliente:

Bash
cd frontend
Instalar los paquetes y dependencias de Node:

Bash
npm install
Configurar la conexión con la API:
Crea un archivo .env en la raíz de la carpeta frontend:

Fragmento de código
REACT_APP_API_URL=http://localhost:5000
Ejecutar la aplicación en modo desarrollo:

Bash
npm start
¡Listo! Tu navegador debería abrir automáticamente una pestaña en http://localhost:3000 mostrando la aplicación interactiva de la Ruta Cultural.