# TEMA 13: Fundamentos del lenguaje Swift

---

## 1) ¿Qué es Swift y qué significa que compile a nativo (vs Java en JVM)?

**Swift** es el lenguaje de programación de Apple para iOS/macOS, aunque el lenguaje en sí puede usarse más allá del ecosistema Apple.

- **Compilar a nativo**: el compilador genera **código máquina optimizado** para la plataforma (LLVM, según el temario).
- **Java en JVM**: el código se compila a **bytecode** que se ejecuta en una **máquina virtual**.

**Idea clave**  
Swift prioriza **rendimiento y seguridad en tiempo de compilación**.  
Java prioriza **portabilidad** gracias a la JVM.

> **Analogía**  
> Nativo = “hablar directamente” con el hardware  
> JVM = “intérprete/mediador” entre tú y el hardware

---

## 2) ¿Dónde puedes programar Swift y dónde desarrollar apps iOS reales?

- Swift es **multiplataforma**: se puede escribir y compilar en **Windows, Linux y macOS**.
- **Apps iOS reales**: el desarrollo oficial solo se realiza en **macOS**.
- El PDF explica:
  - Instalación en Windows con **Swift for Windows**
  - Uso de **VS Code + terminal**

> **Importante**  
> “Puedo usar Swift fuera de Mac” ≠ “Puedo crear apps iOS desde Windows”

---

## 3) ¿Cómo se documenta el código en Swift y por qué es importante?

- Comentario de una línea:

    ```swift
    // Comentario
    ```

- Comentario multilínea:

    ```swift
    /* Comentario */
    ```

¿Por qué es importante documentar el código?

- Mejora el mantenimiento del programa.
- Facilita la comprensión del algoritmo.
- Es clave en prácticas, exámenes y entregas.

## 4) ¿Cómo se declaran variables y constantes y qué implica `let` vs `var`?

- `var` → variable **mutable** (su valor puede cambiar).
- `let` → constante **inmutable** (su valor no puede cambiar).

En Swift se **prefiere usar `let`** siempre que sea posible para reducir errores por modificaciones accidentales.

**Tipado en Swift:**
- Swift puede **inferir el tipo** automáticamente al asignar un valor.
- **No se permiten variables sin inicializar**: deben tener un valor desde el principio.

> **Idea clave**  
> Usar `let` aumenta la seguridad del código y evita cambios accidentales.

> **Analogía**  
> `let` es como **precintar** un valor: una vez cerrado, no se puede tocar.

## 5) ¿Cuáles son los tipos básicos y qué operaciones se esperan que sepas?

### Tipos básicos (según el PDF)
- `Int`
- `Double`
- `Bool`
- `String`

### Operaciones habituales
- Numéricas: `+`, `-`, `*`, `/`, `%`
- Cadenas (`String`): concatenación y operaciones de texto

En Swift, las conversiones entre tipos suelen ser **explícitas**, lo que evita errores silenciosos y comportamientos inesperados.

## 6) ¿Cómo funciona la entrada y salida y qué “trampas” hay con `readLine()`?

- Salida por consola:
  
    print("Hola mundo")

- Interpolación de variables:
  
    print("Hola \(nombre)")

- Entrada por teclado:
  
    let entrada = readLine()

Puntos clave:
- `readLine()` devuelve siempre un **String opcional (`String?`)**.
- Para trabajar con números (`Int`, `Double`) hay que convertir desde `String`.
- La conversión puede fallar y devolver `nil`.
- Usar `!` puede provocar errores en tiempo de ejecución si el valor es `nil`.

## 7) ¿Qué son los opcionales y cuál es la forma correcta de gestionarlos?

Un **opcional** indica que una variable puede tener un valor o ser `nil`.

- Se declara añadiendo `?` al tipo.
- Antes de usar el valor hay que comprobar que existe.

Formas correctas de gestionar opcionales:
- `if let` para desempaquetar de forma segura.
- `guard let` para validar y salir si no hay valor.
- `??` para asignar un valor por defecto.
- `?.` para acceder de forma segura a propiedades o métodos.

Qué se debe evitar:
- `!` (desempaquetado forzado), salvo certeza absoluta de que no es `nil`.

Analogía:
- Un opcional es como una **caja**: antes de usar lo que hay dentro, compruebas si realmente hay algo.


## 8) ¿Cómo se modelan “grupos” y “colecciones” en Swift y cuándo usar cada cosa?

- **Tupla**: agrupa valores **heterogéneos** sin crear un tipo nuevo. Útil para devolver varios resultados juntos.
- **Array**: colección **ordenada** de elementos del mismo tipo. Se declara con `[]` y puede ser `var` o `let`.

Operaciones esenciales de arrays (según el temario):
- `count`
- `append`
- `insert`
- `remove(at:)`
- `sort`
- `reversed`
- `shuffle`
- Acceso por índice y asignación

(Temario ampliado)
- **Dictionary**: colección **clave–valor**.
- **Set**: colección **sin duplicados**.

Clave de examen:
- Orden
- Duplicados
- Forma de acceso
- Coste de búsqueda (array peor buscando que set/dictionary)

## 9) ¿Qué diferencia real hay entre `struct` y `class` y por qué importa?

- **struct** → tipo de **valor** (se copia al asignar o pasar como parámetro).
- **class** → tipo de **referencia** (varias variables pueden apuntar a la misma instancia).

Consecuencias:
- Con `struct`, modificar una copia **no afecta** al original.
- Con `class`, modificar una referencia **afecta** a todos los que apuntan a esa instancia.

Regla práctica (temario):
- Usar **struct por defecto**.
- Usar **class** cuando se necesita identidad, herencia o compartir estado.

Analogía:
- `struct` = **fotocopia**.
- `class` = **documento compartido en Drive**.

## Glosario (términos clave)

- **Swift**: lenguaje de programación de Apple para iOS/macOS; multiparadigma y con foco en la seguridad.
- **Multiplataforma (Swift)**: puede instalarse y compilarse en Windows, Linux y macOS para programas Swift, pero el desarrollo de apps iOS se realiza en macOS.
- **Xcode**: IDE oficial en macOS para desarrollar aplicaciones del ecosistema Apple.
- **Swift for Windows**: paquete que permite disponer del compilador Swift en Windows.
- **VS Code + terminal**: entorno sugerido en el PDF para compilar y ejecutar programas Swift en Windows.
- **Compilación**: proceso de traducir código Swift a un ejecutable o artefacto que puede ejecutarse.
- **var**: palabra clave para declarar una variable mutable.
- **let**: palabra clave para declarar una constante inmutable.
- **Inferencia de tipos**: el tipo de una variable se deduce automáticamente al asignarle un valor por primera vez.
- **Tipos básicos**: `Int`, `Double`, `Bool`, `String`.

- **print()**: función para mostrar salida por consola.
- **readLine()**: función de entrada por teclado; devuelve un `String` opcional.
- **Interpolación**: insertar valores dentro de un `String` usando `\(variable)`.
- **Opcional (T?)**: tipo que puede contener un valor o `nil`.
- **Unwrap**: proceso de extraer el valor de un opcional.
- **if let**: forma segura de desempaquetar un opcional de manera condicionada.
- **guard let**: desempaquetado con salida temprana si el valor es `nil`.
- **?? (nil coalescing)**: operador que asigna un valor por defecto si el opcional es `nil`.
- **?. (optional chaining)**: acceso seguro a propiedades o métodos si el valor existe.
- **! (force unwrap)**: desempaquetado forzado; puede provocar un error si el valor es `nil`.

- **Array ([T])**: colección ordenada de elementos; métodos típicos `count`, `append`, `insert`, `remove`, `sort`, etc.
- **Tupla**: agrupación ligera de valores, posiblemente de distintos tipos.
- **Dictionary**: colección de pares clave–valor.
- **Set**: colección sin elementos duplicados.

- **struct**: tipo de valor; se copia al asignar o pasar como parámetro.
- **class**: tipo de referencia; varias variables pueden compartir la misma instancia.
- **Herencia**: mecanismo disponible solo en clases.
- **Protocol**: contrato que define propiedades y métodos que un tipo debe implementar.
- **Extension**: permite añadir funcionalidad a un tipo sin modificar su definición original.
- **throws / do-catch**: mecanismo estructurado para el manejo de errores.
- **defer**: bloque de código que se ejecuta al salir del scope.
- **Control de acceso**: niveles `open`, `public`, `internal`, `fileprivate`, `private`.

