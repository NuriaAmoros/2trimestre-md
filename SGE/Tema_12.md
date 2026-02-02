# TEMA 12: Programando en Python  
**Asignatura: Sistema de Gestión Empresarial**

## Objetivo del tema
Comprender y aplicar los fundamentos intermedios de programación en Python, centrándose en la indentación como elemento estructural del lenguaje, los flujos de programación secuenciales e iterativos, el control de errores, la organización del código mediante funciones, módulos y paquetes, el trabajo con cadenas de texto y ficheros, y una introducción a la programación orientada a objetos.

## Índice
1. Indentación y flujo de programación secuencial  
2. Flujo de programación iterativo y función `range`  
3. Control de errores  
4. Estructura del código: funciones  
5. Estructura del código: módulos y librerías  
6. Ficheros y cadenas de texto  
7. Programación orientada a objetos en Python  

---

## 1. Indentación y flujo de programación secuencial
La **indentación** en Python consiste en el desplazamiento hacia la derecha de una o varias líneas de código mediante espacios o tabuladores. Es un elemento **obligatorio** del lenguaje y se utiliza para delimitar bloques de código.

A diferencia de otros lenguajes, Python:
- No utiliza llaves `{}` para delimitar bloques.
- No emplea punto y coma como terminador de sentencia.

La indentación permite:
- Agrupar instrucciones que pertenecen a un mismo bloque.
- Mejorar la legibilidad del código.
- Evitar errores estructurales comunes en otros lenguajes.

El **flujo de programación secuencial** se basa en la ejecución de instrucciones en orden, pudiendo alterarse mediante estructuras condicionales como `if`, `elif` y `else`.  
Estas estructuras permiten ejecutar determinadas instrucciones solo si se cumple una condición lógica.

---

## 2. Flujo de programación iterativo y función `range`
Python dispone de estructuras iterativas que permiten repetir bloques de código mientras se cumpla una condición o mientras se recorra una secuencia.

### Bucle `while`
El bucle `while` repite un conjunto de instrucciones **mientras la condición sea verdadera**.  
La condición se evalúa antes de cada iteración.

### Bucle `for`
El bucle `for` se utiliza para **iterar sobre secuencias** como listas, tuplas, diccionarios o cadenas de texto, recorriendo sus elementos en el orden en que aparecen.

### Sentencias de control en bucles
- `break`: interrumpe el bucle aunque la condición siga siendo verdadera.
- `continue`: salta a la siguiente iteración del bucle.

### Función `range`
La función `range()` genera una secuencia de números enteros y se utiliza habitualmente junto al bucle `for`.

Características principales:
- Comienza en 0 por defecto.
- Incrementa de 1 en 1 si no se indica lo contrario.
- Puede configurarse con valor inicial, final e incremento.

---

## 3. Control de errores
Cuando Python detecta un error, la ejecución del programa se detiene y se muestra un mensaje de error.  
Para evitar que estos errores interrumpan el programa y para ofrecer mensajes más controlados, Python permite gestionar excepciones.

Estructura básica del control de errores:
- `try`: bloque donde se escribe el código susceptible de producir errores.
- `except`: bloque que captura y gestiona el error.
- `finally`: bloque que se ejecuta siempre, haya o no error.
- `else`: bloque opcional que se ejecuta cuando no se produce ningún error.
- `raise`: permite lanzar una excepción de forma manual.

El control de errores mejora la robustez del programa y la experiencia del usuario final.

---

## 4. Estructura del código: funciones
Una **función** es un bloque de código reutilizable que realiza una tarea concreta cuando es invocada.

Características principales:
- Tiene un nombre que identifica su funcionalidad.
- Puede recibir parámetros de entrada.
- Puede devolver uno o varios valores, o ninguno.
- Permite dividir el programa en partes más pequeñas y manejables.

Las funciones favorecen:
- La reutilización de código.
- La claridad y organización del programa.
- La reducción de errores y duplicidades.

---

## 5. Estructura del código: módulos y librerías
Un **módulo** es un archivo con extensión `.py` que contiene funciones, variables o clases.  
Permite separar el código en distintos archivos según su funcionalidad.

Una **librería o paquete** es un conjunto de módulos organizados en directorios, normalmente con un archivo `__init__.py`.

Python dispone de:
- Una librería estándar incluida con el lenguaje.
- Librerías de terceros que pueden instalarse mediante el gestor de paquetes `pip`.

El uso de módulos y librerías permite:
- Reutilizar código propio o de terceros.
- Mantener proyectos más ordenados y escalables.

---

## 6. Ficheros y cadenas de texto
Python permite trabajar con ficheros para almacenar y recuperar información de forma persistente.

Operaciones básicas con ficheros:
- Apertura de ficheros en distintos modos (lectura, escritura, añadir, creación).
- Lectura completa o por líneas.
- Escritura de información.
- Cierre del fichero tras su uso.

Además, Python ofrece múltiples herramientas para trabajar con **cadenas de texto**, como:
- Uso de comillas simples o dobles.
- Caracteres especiales (`\n`, `\t`, `\`).
- Subcadenas.
- Funciones de manipulación de texto.

---

## 7. Programación orientada a objetos en Python
Python es un lenguaje orientado a objetos. Prácticamente todo en Python es un objeto con propiedades y métodos.

Conceptos básicos:
- **Clase**: define la estructura y comportamiento de los objetos.
- **Objeto**: instancia de una clase.
- **Método `__init__`**: constructor que se ejecuta al crear un objeto.
- **`self`**: referencia al propio objeto dentro de la clase.

La programación orientada a objetos permite:
- Modelar entidades del mundo real.
- Encapsular datos y comportamiento.
- Crear programas más modulares y mantenibles.

---

## Glosario de términos

**Indentación**  
Desplazamiento de código hacia la derecha que define bloques en Python.

**Flujo secuencial**  
Ejecución de instrucciones en el orden en que aparecen.

**Bucle**  
Estructura que permite repetir un conjunto de instrucciones.

**range**  
Función que genera secuencias de números enteros.

**Excepción**  
Error que se produce durante la ejecución de un programa.

**Función**  
Bloque de código reutilizable que realiza una tarea específica.

**Módulo**  
Archivo Python que contiene código reutilizable.

**Paquete / librería**  
Conjunto de módulos organizados en directorios.

**Fichero**  
Elemento de almacenamiento persistente gestionado desde un programa.

**Clase**  
Plantilla que define las propiedades y métodos de un objeto.

**Objeto**  
Instancia concreta de una clase.

**Programación orientada a objetos**  
Paradigma que organiza el código en clases y objetos.

## Ejercicio 1

### Código
```python
PASSWORD_CORRECTA = "admin123"
intentos = 3

while intentos > 0:
    password = input("Introduce la contraseña: ")

    if password == PASSWORD_CORRECTA:
        print("Acceso permitido")
        break

    intentos -= 1

    if intentos > 0:
        print("Contraseña incorrecta. Intentos restantes:", intentos)
    else:
        print("Acceso bloqueado")


```

---

## Ejercicio 2

### Código
```python
fichero = open("ventas.txt", "w")

producto = input("Introduce un producto vendido (o 'fin' para terminar): ")

while producto != "fin":
    fichero.write(producto + "\n")
    producto = input("Introduce un producto vendido (o 'fin' para terminar): ")

fichero.close()

fichero = open("ventas.txt", "r")
contenido = fichero.read()
fichero.close()

print(contenido)

```

---

## Ejercicio 3

### Código
```python
def convertir_binario(numero):
    return bin(numero)[2:]


try:
    fichero = open("decimal.txt", "r")
    contenido = fichero.read()
    fichero.close()

    numero_decimal = int(contenido)

    resultado_binario = convertir_binario(numero_decimal)

    fichero = open("binario.txt", "w")
    fichero.write(resultado_binario)
    fichero.close()

    print("Conversión realizada correctamente")

except FileNotFoundError:
    print("El fichero decimal.txt no existe")

except ValueError:
    print("El contenido del fichero no es un número válido")
```

---

## Ejercicio 4

### Código
```python
class Producto:
    def __init__(self, nombre, precio, cantidad):
        self.nombre = nombre
        self.precio = precio
        self.cantidad = cantidad

    def valor_total(self):
        return self.precio * self.cantidad


try:
    producto1 = Producto("Teclado", 25.0, 2)
    producto2 = Producto("Ratón", 15.0, 3)
    producto3 = Producto("Monitor", 180.0, 1)

    fichero = open("resultado.txt", "w")

    for producto in (producto1, producto2, producto3):
        total = producto.valor_total()
        linea = f"{producto.nombre}: {total}\n"
        fichero.write(linea)
        print(linea.strip())

    fichero.close()

except Exception as e:
    print("Se ha producido un error:", e)
```
