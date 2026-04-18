# Calculadora de Terminal

## Descripción
Esta es una herramienta de consola diseñada específicamente para ayudar a los estudiantes de básica primaria a verificar sus tareas de matemáticas de forma rápida y sencilla. El objetivo es brindar un entorno seguro y local para el aprendizaje de operaciones aritméticas básicas.

## Requisitos Previos
* **Python**: Se requiere tener instalada la versión **3.8 o superior** en la máquina.
* **Compatibilidad**: El código puede presentar errores si se ejecuta en versiones inferiores a la 3.8.
* **Dependencias**: Este proyecto es "zero-dependencies", lo que significa que no requiere instalar librerías adicionales para funcionar.

## Instalación
Para obtener una copia local del proyecto y prepararlo para su uso, nosotros ejecutamos los siguientes comandos en la terminal:

```
git clone [https://github.com/xxxxx/calc-terminal-python.git](https://github.com/xxxxx/calc-terminal-python.git)
cd calc-terminal-python
```

## Uso
El programa es interactivo y el archivo principal que ejecuta la lógica es calc_math.py. Para arrancarlo, nosotros utilizamos el comando:

```
python calc_math.py
```

El sistema solicitará los datos de entrada uno por uno en el siguiente orden:
1. **num1**: Primer valor numérico (admite enteros y decimales).
2. **operación**: El símbolo matemático deseado (+, -, *, /).
3. **num2**: Segundo valor numérico.

**Ejemplo de ejecución:**
Al ingresar el número 10, luego el operador *, y finalmente el número 5, la consola mostrará el resultado en color azul:
> El resultado de la operación es: 50.0

## Configuración y Variables
El comportamiento de la calculadora puede ajustarse mediante variables internas del código:

| Variable | Valor por defecto | Descripción |
| :--- | :--- | :--- |
| MODO_DEBUG | False | Si se cambia su valor a True, el sistema mostrará toda la traza técnica de los errores al fallar. |

## Solución de Problemas (Troubleshooting)
Nosotros hemos implementado controles para los errores más comunes para evitar que el sistema se detenga:

* **Error de División por cero**: Si el usuario intenta realizar esta operación, el sistema mostrará el mensaje: [ERROR] Operación inválida: No se puede dividir por cero.
* **Entrada de datos**: El programa está diseñado para aceptar números decimales en las entradas de valor.

## Licencia
Este proyecto es software libre y se distribuye bajo la licencia **GNU GPL v3**.
