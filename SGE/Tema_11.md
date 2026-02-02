# TEMA 11: Lenguaje de programación de un sistema ERP-CRM: Python  
**Sistemas de Gestión Empresarial**

## Objetivo del tema
Conocer el **lenguaje de programación Python** como base tecnológica de los sistemas ERP-CRM, identificando sus **características principales**, su **entorno de trabajo**, y los **conceptos fundamentales de programación** necesarios para comprender su uso dentro de plataformas empresariales como Odoo.

## Índice
1. ¿Qué es Python?  
2. Instalación de Python  
3. Entorno de desarrollo: IDE PyCharm  
4. El comando `pip`  
5. Palabras reservadas y comentarios  
6. Tipos de datos en Python  
7. Casting de tipos  
8. Funciones `print()` e `input()`  
9. Variables, constantes y errores  
10. Operadores en Python  

---

## 1. ¿Qué es Python?
Python es un lenguaje de programación creado a finales de los años ochenta por **Guido van Rossum**. Su nombre no proviene de la serpiente, sino del grupo humorístico británico *Monty Python*.

Python se caracteriza por ser:
- **Interpretado**: el código se ejecuta línea a línea sin compilación previa.
- **Multiparadigma**: admite programación estructurada, orientada a objetos y funcional.
- **De alto nivel**: abstrae detalles internos del hardware.
- **De tipado dinámico y fuerte**: el tipo de una variable se asigna en tiempo de ejecución y no se realizan conversiones implícitas inseguras.

Es ampliamente utilizado en entornos empresariales por ser:
- Software libre y open source.
- Multiplataforma.
- Fácil de leer y mantener.
- Muy extensible mediante librerías estándar y de terceros.
- Lenguaje base del ERP **Odoo**.

---

## 2. Instalación de Python
Python puede instalarse en los principales sistemas operativos:

- **Windows**: descarga desde la web oficial y ejecución del instalador.
- **macOS**: incluye una versión preinstalada; es posible instalar otras versiones.
- **GNU/Linux**: suele venir preinstalado; se pueden instalar versiones adicionales mediante el gestor de paquetes.

Es posible tener **varias versiones de Python** en el mismo equipo sin conflicto.

Una vez instalado, Python puede usarse de dos formas:
- **Modo interactivo**: ejecución directa de instrucciones desde el terminal.
- **Ejecución de scripts**: archivos con extensión `.py` ejecutados desde consola.

---

## 3. Entorno de desarrollo: IDE PyCharm
PyCharm es un entorno de desarrollo integrado (IDE) desarrollado por JetBrains. Se utiliza habitualmente la **versión Community**, gratuita.

Funciones principales:
- Autocompletado de código.
- Detección de errores.
- Refactorización.
- Depuración.
- Gestión de proyectos.

Al crear un proyecto, PyCharm permite:
- Usar un **intérprete existente**.
- Crear un **entorno virtual (Virtualenv)**, recomendado para aislar dependencias del proyecto.

---

## 4. El comando `pip`
`pip` es el sistema de gestión de paquetes de Python.

Permite:
- Instalar librerías externas.
- Actualizar paquetes.
- Gestionar dependencias del proyecto.

Se ejecuta desde el terminal, fuera del intérprete de Python, y es fundamental para ampliar las capacidades del lenguaje en proyectos empresariales.

---

## 5. Palabras reservadas y comentarios
Python dispone de un conjunto de **palabras reservadas** que no pueden utilizarse como identificadores, ya que forman parte de la sintaxis del lenguaje.

Ejemplos:
- `if`, `for`, `while`
- `class`, `def`
- `and`, `or`, `not`

Los **comentarios** permiten documentar el código:
- Comentarios de una línea: usando `#`
- Comentarios multilínea: usando triple comilla doble

---

## 6. Tipos de datos en Python
Python permite distintos tipos de datos básicos:

- **Numéricos**: `int`, `float`, `complex`
- **Cadenas de texto**: `str`
- **Booleanos**: `bool`
- **Listas**: `list` (mutables)
- **Tuplas**: `tuple` (inmutables)
- **Rangos**: `range`
- **Diccionarios**: `dict` (clave-valor)
- **Conjuntos**: `set` (no ordenados, sin índices)

Las listas y tuplas pueden contener datos heterogéneos.

---

## 7. Casting de tipos
El **casting** permite convertir un valor de un tipo a otro de forma explícita.

Funciones principales:
- `int()` → convierte a entero.
- `float()` → convierte a número decimal.
- `str()` → convierte a cadena de texto.

El casting es especialmente importante al trabajar con datos introducidos por el usuario, ya que estos se reciben siempre como cadenas.

---

## 8. Funciones `print()` e `input()`
- **`print()`**: muestra información por pantalla.
- **`input()`**: solicita información al usuario desde teclado.

La función `input()` siempre devuelve un valor de tipo `str`, por lo que suele ser necesario aplicar casting antes de operar con el dato.

---

## 9. Variables, constantes y errores
### Variables
- Se crean al asignarles un valor.
- No requieren declaración previa.
- Pueden cambiar de tipo durante la ejecución.

Reglas de nombrado:
- Comienzan por letra o `_`.
- No pueden empezar por números.
- Son sensibles a mayúsculas y minúsculas.

### Constantes
Python no tiene constantes reales. Por convención, se usan **variables en mayúsculas** para indicar que su valor no debe modificarse.

### Errores
Tipos principales:
- **Errores de sintaxis**: el código no cumple las reglas del lenguaje.
- **Errores de ejecución**: el código es correcto, pero falla al ejecutarse.

La interpretación de los mensajes de error es clave para depurar programas.

---

## 10. Operadores en Python
Python incluye varios tipos de operadores:

- **Aritméticos**: `+`, `-`, `*`, `/`, `%`, `**`, `//`
- **De asignación**: `=`, `+=`, `-=`, `*=`, etc.
- **De comparación**: `==`, `!=`, `<`, `>`, `<=`, `>=`
- **Lógicos**: `and`, `or`, `not`
- **De identidad**: `is`, `is not`
- **De pertenencia**: `in`, `not in`
- **Bit a bit**: `&`, `|`, `^`, `~`, `<<`, `>>`

Estos operadores permiten construir expresiones lógicas y matemáticas dentro de los programas.

---

## Idea clave para examen
- Python es el **lenguaje base de Odoo**.
- Es interpretado, de alto nivel y tipado dinámico.
- El uso de `pip` y entornos virtuales es fundamental.
- Los conceptos básicos (tipos, variables, operadores) son esenciales para comprender cualquier desarrollo ERP-CRM.
- No se evalúa programación avanzada, sino **comprensión del lenguaje y su uso empresarial**.

# Glosario — Tema 11: Lenguaje de programación de un sistema ERP-CRM: Python  
**Sistemas de Gestión Empresarial**

## Conceptos generales
- **Lenguaje de programación**: Conjunto de reglas y símbolos que permiten expresar instrucciones ejecutables por un ordenador.
- **Python**: Lenguaje de programación interpretado, de alto nivel y multiparadigma, utilizado como base tecnológica en sistemas ERP-CRM como Odoo.
- **ERP-CRM**: Sistema integrado para la gestión de recursos empresariales y relaciones con clientes.

## Características de Python
- **Lenguaje interpretado**: El código se ejecuta línea a línea sin una fase previa de compilación.
- **Lenguaje de alto nivel**: Oculta detalles del hardware y facilita la escritura y lectura del código.
- **Tipado dinámico**: El tipo de una variable se asigna en tiempo de ejecución.
- **Tipado fuerte**: No se realizan conversiones implícitas entre tipos incompatibles.
- **Multiparadigma**: Soporta programación estructurada, orientada a objetos y funcional.

## Instalación y ejecución
- **Instalación de Python**: Proceso de añadir el intérprete de Python al sistema operativo.
- **Intérprete**: Programa que ejecuta el código Python.
- **Modo interactivo**: Ejecución de instrucciones Python directamente desde la consola.
- **Script**: Archivo con extensión `.py` que contiene código Python ejecutable.

## Entornos de desarrollo
- **IDE (Entorno de Desarrollo Integrado)**: Aplicación que facilita la programación mediante herramientas como editor, depurador y autocompletado.
- **PyCharm**: IDE desarrollado por JetBrains para programar en Python.
- **Proyecto**: Conjunto organizado de archivos y configuraciones de una aplicación.
- **Entorno virtual (Virtualenv)**: Entorno aislado que permite gestionar dependencias de un proyecto de forma independiente.

## Gestión de paquetes
- **pip**: Gestor de paquetes de Python que permite instalar, actualizar y eliminar librerías.
- **Paquete**: Conjunto de módulos que amplían las funcionalidades del lenguaje.
- **Dependencia**: Librería externa necesaria para el funcionamiento de un proyecto.

## Sintaxis y estructura
- **Palabra reservada**: Término con significado especial en Python que no puede usarse como identificador.
- **Comentario**: Texto no ejecutable que sirve para documentar el código.
- **Identificador**: Nombre asignado a variables, funciones o clases.

## Tipos de datos
- **Tipo de dato**: Categoría que define el tipo de valor que puede almacenar una variable.
- **int**: Tipo numérico entero.
- **float**: Tipo numérico decimal.
- **str**: Cadena de texto.
- **bool**: Tipo lógico con valores `True` o `False`.
- **list**: Colección ordenada y mutable.
- **tuple**: Colección ordenada e inmutable.
- **dict**: Colección de pares clave–valor.
- **set**: Colección no ordenada sin elementos duplicados.
- **range**: Secuencia de números generada automáticamente.

## Casting y entrada/salida
- **Casting**: Conversión explícita de un tipo de dato a otro.
- **`int()` / `float()` / `str()`**: Funciones de conversión de tipos.
- **`print()`**: Función que muestra información por pantalla.
- **`input()`**: Función que solicita datos al usuario desde teclado.

## Variables y errores
- **Variable**: Espacio de memoria al que se asigna un valor.
- **Constante (convención)**: Variable cuyo valor no debería cambiar, escrita en mayúsculas.
- **Error de sintaxis**: Error producido por incumplir las reglas del lenguaje.
- **Error de ejecución**: Error que ocurre durante la ejecución del programa.

## Operadores
- **Operador**: Símbolo que permite realizar operaciones sobre datos.
- **Operadores aritméticos**: Realizan cálculos matemáticos.
- **Operadores de comparación**: Comparan valores.
- **Operadores lógicos**: Combinan expresiones booleanas.
- **Operadores de asignación**: Asignan valores a variables.
- **Operadores de pertenencia**: Comprueban si un elemento pertenece a una colección.
- **Operadores de identidad**: Comparan referencias a objetos.

## Claves conceptuales de examen
- **Python como base de Odoo**: Lenguaje principal para el desarrollo del ERP.
- **Lectura e interpretación del código**: Prioritaria frente a la programación avanzada.
- **Entorno y dependencias**: Uso de `pip` y entornos virtuales.
- **Sintaxis clara y legible**: Rasgo distintivo de Python en entornos empresariales.

## Ejercicio 1

### Enunciado
Escribir un programa que pregunte el nombre del usuario en la consola y después de que el usuario lo introduzca muestre por pantalla la cadena `¡Hola <nombre>!`, donde `<nombre>` es el nombre que el usuario haya introducido.

---

### Código
```python
nombre = input("Introduce tu nombre: ")
print(f"¡Hola {nombre}!")
```

---


### Explicación línea por línea

Línea 1: nombre = input("Introduce tu nombre: ")
	•	input("Introduce tu nombre: "):
	•	Muestra el texto "Introduce tu nombre: " en la consola.
	•	Detiene la ejecución del programa hasta que el usuario introduce un valor y pulsa Enter.
	•	Devuelve siempre un dato de tipo cadena de texto (str).
	•	= (operador de asignación):
	•	Asigna el valor devuelto por input() a la variable nombre.
	•	nombre:
	•	Es una variable que almacena el texto introducido por el usuario.
	•	En Python no se declara el tipo de la variable de forma explícita.
	•	El tipo se asigna automáticamente en tiempo de ejecución.
	•	En este caso, nombre es de tipo str.

Línea 2: print(f"¡Hola {nombre}!")
	•	print():
	•	Muestra información por pantalla enviándola a la salida estándar (consola).
	•	f"¡Hola {nombre}!":
	•	Es una cadena formateada (f-string).
	•	Permite insertar el valor de una variable dentro del texto.
	•	{nombre}:
	•	Se sustituye por el contenido almacenado en la variable nombre.
	•	El resultado final es una cadena que contiene el saludo seguido del nombre introducido por el usuario.



## Ejercicio 2

Enunciado  
Vamos a crear un programa en Python donde vamos a declarar tres variables y las vamos a imprimir por pantalla:  
- Modulo_Cursado: Desarrollo de Aplicaciones Multiplataforma  
- Años_Modulo: 2  
- Nombre_Alumno: indicamos nuestro nombre  

---

Código
```python
Modulo_Cursado = "Desarrollo de Aplicaciones Multiplataforma"
Anios_Modulo = 2
Nombre_Alumno = "Nuria"

print(Modulo_Cursado)
print(Anios_Modulo)
print(Nombre_Alumno)

```

---

### Explicación línea por línea

Línea 1: Modulo_Cursado = "Desarrollo de Aplicaciones Multiplataforma"
	•	"Desarrollo de Aplicaciones Multiplataforma":
	•	Es una cadena de texto (str).
	•	Representa el nombre del módulo cursado.
	•	= (operador de asignación):
	•	Asigna el valor de la cadena a la variable Modulo_Cursado.
	•	Modulo_Cursado:
	•	Es una variable que almacena texto.
	•	El tipo se asigna automáticamente en tiempo de ejecución.
	•	En este caso, Modulo_Cursado es de tipo str.

Línea 2: Anios_Modulo = 2
	•	2:
	•	Es un valor numérico entero.
	•	Representa la duración del módulo en años.
	•	= (operador de asignación):
	•	Asigna el valor entero a la variable Anios_Modulo.
	•	Anios_Modulo:
	•	Es una variable que almacena un número entero.
	•	En este caso, Anios_Modulo es de tipo int.

Línea 3: Nombre_Alumno = "Nuria"
	•	"Nuria":
	•	Es una cadena de texto (str).
	•	Representa el nombre del alumno.
	•	= (operador de asignación):
	•	Asigna el valor de la cadena a la variable Nombre_Alumno.
	•	Nombre_Alumno:
	•	Es una variable que almacena texto.
	•	En este caso, Nombre_Alumno es de tipo str.

Línea 4: print(Modulo_Cursado)
	•	print():
	•	Muestra información por pantalla enviándola a la salida estándar (consola).
	•	Modulo_Cursado:
	•	Se sustituye por el contenido almacenado en la variable.
	•	Muestra el texto del módulo cursado.

Línea 5: print(Anios_Modulo)
	•	print():
	•	Muestra información por pantalla.
	•	Anios_Modulo:
	•	Se sustituye por el valor entero almacenado en la variable.
	•	Muestra el número de años del módulo.

Línea 6: print(Nombre_Alumno)
	•	print():
	•	Muestra información por pantalla.
	•	Nombre_Alumno:
	•	Se sustituye por el contenido almacenado en la variable.
	•	Muestra el nombre del alumno.


## Ejercicio 3

Enunciado  
Vamos a crear un programa en Python que nos pida nuestra edad usando la función `input()`.  
Creamos una constante con la edad de jubilación, con valor 67.  
Finalmente, queremos que nos muestre por pantalla los años que nos quedan para jubilarnos, es decir, la edad de jubilación menos la edad introducida.

---

Código
```python
edad = int(input("Introduce tu edad: "))
EDAD_JUBILACION = 67

años_restantes = EDAD_JUBILACION - edad

print("Te quedan", años_restantes, "años para jubilarte")

```

### Explicación línea por línea

Línea 1: edad = int(input("Introduce tu edad: "))
	•	input("Introduce tu edad: "):
	•	Muestra el texto "Introduce tu edad: " en la consola.
	•	Detiene la ejecución del programa hasta que el usuario introduce un valor y pulsa Enter.
	•	Devuelve siempre un dato de tipo cadena de texto (str).
	•	int(...):
	•	Convierte la cadena de texto devuelta por input() en un número entero.
	•	Esta conversión es necesaria para poder realizar operaciones matemáticas.
	•	edad:
	•	Es una variable que almacena la edad introducida por el usuario.
	•	El tipo se asigna automáticamente en tiempo de ejecución.
	•	En este caso, edad es de tipo int.

Línea 2: EDAD_JUBILACION = 67
	•	67:
	•	Es un valor numérico entero.
	•	Representa la edad de jubilación establecida.
	•	= (operador de asignación):
	•	Asigna el valor entero a la variable EDAD_JUBILACION.
	•	EDAD_JUBILACION:
	•	Es una constante por convención.
	•	Se escribe en mayúsculas para indicar que no debe modificarse.
	•	En este caso, EDAD_JUBILACION es de tipo int.

Línea 3: años_restantes = EDAD_JUBILACION - edad
	•	EDAD_JUBILACION - edad:
	•	Realiza una operación aritmética de resta.
	•	Calcula los años que faltan para la jubilación.
	•	= (operador de asignación):
	•	Asigna el resultado de la operación a la variable años_restantes.
	•	años_restantes:
	•	Es una variable que almacena el resultado del cálculo.
	•	El tipo se asigna automáticamente en tiempo de ejecución.
	•	En este caso, años_restantes es de tipo int.

Línea 4: print("Te quedan", años_restantes, "años para jubilarte")
	•	print():
	•	Muestra información por pantalla enviándola a la salida estándar (consola).
	•	"Te quedan":
	•	Es una cadena de texto literal.
	•	años_restantes:
	•	Se sustituye por el valor entero almacenado en la variable.
	•	"años para jubilarte":
	•	Es una cadena de texto literal.
	•	print combina los distintos elementos y los muestra separados por espacios.