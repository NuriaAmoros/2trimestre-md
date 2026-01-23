# TEMA 14: Fundamentos del lenguaje Kotlin

## Objetivo del tema
Comprender los fundamentos de Kotlin como lenguaje moderno para desarrollo Android y backend, identificando **qué problemas resuelve frente a Java**, **por qué Google lo prioriza** y **cómo sus decisiones de diseño impactan directamente en la seguridad, legibilidad y mantenibilidad del código**.

## Tabla de contenidos
1) ¿Qué es Kotlin y por qué se usa en Android?
2) Kotlin vs Java: diferencias que realmente importan (para programar mejor)
3) Entorno y ejecución: Android Studio / IntelliJ / compilación
4) Variables, tipos y Strings: val/var, inferencia, conversiones, templates
5) Null safety: cómo Kotlin te evita el NullPointerException (y cuándo NO)
6) Colecciones: List/Set/Map + mutabilidad (y por qué importa)
7) Control de flujo: if como expresión, when, rangos y bucles
8) Funciones: sintaxis, defaults, nombrados, vararg y funciones locales
9) POO en Kotlin: constructores, properties/backing field, herencia, interfaces
10) Clases especiales: data class, sealed class, enum class
11) Object y companion object: “sin static” y patrones típicos
12) Extensions: añadir funciones/props sin tocar la clase

---

## 1. Introducción y contexto

Kotlin es un **lenguaje moderno, expresivo y seguro**, desarrollado por **JetBrains** y diseñado para **mejorar las limitaciones históricas de Java** sin romper el ecosistema existente.

Puntos clave de contexto (lo importante, sin paja):

- Corre sobre la **JVM** → compatible con todo el ecosistema Java.
- Es **100% interoperable con Java** → ambos lenguajes pueden convivir en el mismo proyecto.
- Google lo declara **lenguaje oficial para Android (2017)** y **preferido (2019)**.
- Prioriza **seguridad en tiempo de compilación**, no en ejecución.

👉 Idea clave: *Kotlin no sustituye Java, lo corrige.*

---
## 1.1. ¿Qué es Kotlin?

Kotlin es un lenguaje de programación **estáticamente tipado**, **moderno** y **multiparadigma** (programación orientada a objetos + programación funcional), creado por **JetBrains** y diseñado para **mejorar los problemas reales de Java** sin romper su ecosistema.

Corre sobre la **JVM** (compila a bytecode igual que Java) y, por ello, es totalmente compatible con cualquier plataforma y librería Java existente. En Android, **Google lo declara lenguaje oficial (2017) y preferido (2019)** para el desarrollo de nuevas aplicaciones.

El diseño de Kotlin se centra en tres objetivos claros:

- **Reducir código repetitivo (boilerplate)**  
  Permite escribir menos líneas para expresar la misma lógica, mejorando la legibilidad y productividad.
- **Eliminar errores comunes**, especialmente el **NullPointerException**, uno de los fallos más frecuentes en Java.
- **Forzar buenas prácticas desde el diseño**, haciendo que el compilador ayude activamente al programador.

### Características fundamentales de Kotlin

- **Interoperabilidad total con Java**  
  Kotlin y Java pueden convivir en el mismo proyecto, clase a clase y archivo a archivo.
- **Inferencia de tipos potente**  
  El compilador deduce los tipos automáticamente en la mayoría de los casos, sin perder seguridad.
- **Sistema de null safety integrado**  
  El lenguaje distingue explícitamente entre referencias que pueden ser `null` y las que no.
- **Soporte multiplataforma**, permitiendo reutilizar lógica de negocio:
  - Kotlin/JVM (Android, backend)
  - Kotlin/JS (web)
  - Kotlin/Native (iOS, desktop)
  - Kotlin Multiplatform (lógica compartida)

### Kotlin y Android: por qué se usa

En Android, Kotlin se utiliza porque permite:

- Escribir **apps más seguras**, con menos crashes en producción.
- Mantener **código más limpio y fácil de evolucionar**.
- Integrarse sin fricciones con proyectos Android ya existentes en Java.

**Idea clave**  
Kotlin no sustituye Java ni obliga a reescribir proyectos. Es una **mejora práctica** que permite desarrollar aplicaciones Android más seguras, mantenibles y modernas, aprovechando todo el ecosistema Java existente.

**Analogía**  
Java es como conducir un coche manual antiguo: tienes control total, pero también más riesgo de error.  
Kotlin es un coche automático con asistencias: sigues conduciendo, pero el sistema evita muchos fallos comunes por ti.


---

## 1.2. Kotlin vs Java: diferencias filosóficas (lo que el profesor quiere que entiendas)

| Concepto clave | Java | Kotlin |
|---|---|---|
| Verbosidad | Alta | Baja |
| Null safety | No integrada | Integrada en el sistema de tipos |
| Mutabilidad | Mutable por defecto | Inmutabilidad promovida |
| Getters / Setters | Manuales | Automáticos (properties) |
| Inferencia de tipos | Limitada | Completa |
| Funciones | Métodos de clase | Funciones top-level |
| Data classes | Código manual | Generación automática |
| Smart casts | No | Sí |
| Checked exceptions | Sí | No |
| Punto y coma | Obligatorio | Opcional |

Conclusión clave para examen/desarrollo:

- **Java confía en el programador**
- **Kotlin desconfía y protege**

Esto reduce:
- Bugs
- Crashes en producción
- Código defensivo innecesario


## Kotlin vs Java: diferencias que realmente importan
Lo importante no es “qué es más bonito”, sino qué cambia tu forma de programar:

- **Null safety** (Kotlin) vs null libre (Java).
- **val/var**: Kotlin empuja a **inmutabilidad** (val).
- **Properties**: no escribes getters/setters a mano (aunque existen).
- **if y when** devuelven valores (son **expresiones**).
- **Data classes**: modelo de datos en 1 línea (equals/hashCode/toString/copy).
- **Sin checked exceptions**: todo es unchecked.
- **No hay static**: se usa `companion object`.

**Idea clave**
Kotlin reduce “errores tontos” (null, cast, verbosidad) y te obliga a diseñar con más intención.

---

## 1.3. Casos de uso de Kotlin (solo los relevantes)

- **Android** (principal)
- **Backend** (Spring Boot, Ktor)
- **Multiplataforma** (lógica compartida)
- **Scripting** (`.kts`)
- **Data / tooling** (integración con JVM)

👉 Para DAM: **Android + backend** son los dos focos reales.

---

## 2. Entorno de desarrollo (visión general)

Kotlin **no necesita herramientas nuevas**: se apoya en el ecosistema Java existente.

Herramientas clave:

- **Android Studio** → estándar Android
- **IntelliJ IDEA** → soporte Kotlin nativo
- **Compilador `kotlinc`** → CLI
- **Kotlin Playground** → pruebas rápidas online

👉 Idea clave: aprender Kotlin **no añade fricción**, reduce trabajo.

---

## Preguntas clave del bloque (examen + comprensión)

1. ¿Qué problema principal de Java intenta resolver Kotlin?
2. ¿Por qué Kotlin puede convivir con Java en el mismo proyecto?
3. ¿Qué significa que Kotlin sea “null-safe” a nivel de lenguaje?
4. ¿Por qué Google prioriza Kotlin frente a Java en Android?
5. ¿Qué ventajas reales aporta Kotlin al mantenimiento del código?
6. ¿En qué se diferencia la filosofía de diseño de Kotlin respecto a Java?

---

## Términos clave introducidos en este bloque

- Kotlin  
- JVM  
- Interoperabilidad  
- Null safety  
- Boilerplate  
- Inferencia de tipos  
- Multiplataforma  
- Smart cast  


---



## 3. Entorno y ejecución: ¿dónde se usa Kotlin de verdad?

Kotlin se apoya directamente en el **ecosistema Java**, por lo que no introduce complejidad adicional a nivel de herramientas. El objetivo del lenguaje es **mejorar cómo se escribe el código**, no cambiar cómo se ejecuta.

### Entornos reales de uso

- **Android Studio**  
  Es el **estándar para desarrollo Android** y el entorno principal donde se usa Kotlin en la práctica.  
  Incluye:
  - Soporte completo para Kotlin.
  - Conversión automática de Java a Kotlin (útil, pero no perfecta).
  - Autocompletado y detección temprana de errores.
  - Integración total con Gradle y el sistema Android.

- **IntelliJ IDEA**  
  IDE desarrollado por **JetBrains**, creadores de Kotlin.  
  Es el entorno con **mejor soporte general** del lenguaje:
  - Ideal para aprender Kotlin puro.
  - Muy usado en backend (Spring Boot, Ktor).
  - Herramientas de refactorización muy avanzadas.

- **Kotlin Playground**  
  Entorno online para:
  - Probar sintaxis rápidamente.
  - Entender conceptos sin configurar nada.
  - Experimentar con ejemplos pequeños.  

  No es un entorno profesional, pero es útil para **aprendizaje y pruebas rápidas**.

---

## Ejecución y compilación (idea esencial)

Kotlin **no se interpreta**, se **compila**:

- El código Kotlin se compila a **bytecode JVM**.
- Ese bytecode se ejecuta exactamente igual que el de Java.
- En Android, Kotlin se integra en el proceso normal de build (Gradle).

Ejemplo mínimo de punto de entrada:

```kotlin
fun main() {
    println("Hola desde Kotlin")
}
```

---

## 4) Variables, tipos y Strings: lo que más te van a preguntar
### 4.1 val vs var
- `val`: referencia **inmutable** (no reasignas).
- `var`: referencia **mutable** (reasignas).

**Regla práctica**
Usa **val por defecto**. Cambia a **var** solo si hay una razón clara.


---

## Idea clave del bloque

Para aprender Kotlin **no es crítico el entorno**, sino comprender:

- **La sintaxis**
- **El sistema de tipos**
- **El null safety**
- **Las decisiones de diseño del lenguaje**

El IDE solo **acelera y ayuda**, pero el conocimiento real está en **el lenguaje**, no en la herramienta.
### 4.2 Inferencia de tipos (continuación)
- Kotlin aplica **inferencia de tipos estática**: el compilador deduce el tipo en compilación y **no cambia**.
- La inferencia ocurre en la **primera asignación**; a partir de ahí, el símbolo queda tipado.
- Declarar el tipo explícito es recomendable cuando:
  - El literal no documenta bien la intención (p. ej. `0` vs `0L` vs `0.0`).
  - Quieres fijar un contrato (API pública, propiedades, parámetros).
  - Necesitas expresar **nulabilidad** explícita (`String?`).
  - Hay genéricos donde la inferencia puede ser menos evidente.

Ejemplos típicos (lo esencial):
- `val n = 42` → `Int`
- `val p = 19.99` → `Double`
- `val f = 3.14f` → `Float`
- `val s = "hola"` → `String`
- `val b = true` → `Boolean`

### 4.3 Tipos de datos básicos (qué debes dominar)
- Kotlin en JVM optimiza a primitivos cuando procede, pero a nivel de lenguaje trabajas con tipos:
  - Numéricos: `Byte`, `Short`, `Int`, `Long`, `Float`, `Double`
  - Lógicos: `Boolean`
  - Caracteres: `Char`
  - Texto: `String`
- Literales relevantes:
  - `L` para `Long`, `f/F` para `Float`
  - Separador `_` para legibilidad: `1_000_000`
  - Hex `0x...`, binario `0b...`

### 4.4 Conversión explícita entre tipos (punto clásico de examen)
- Kotlin **no permite** conversiones numéricas implícitas (evita errores sutiles).
- Conversión mediante métodos:
  - `toInt()`, `toLong()`, `toDouble()`, `toFloat()`, etc.
- Conversión desde `String`:
  - `toInt()`, `toDouble()` (fallan si el contenido no es válido)
  - `toIntOrNull()`, `toDoubleOrNull()` (devuelven `null` si falla)

Idea crítica:
- Si un operador mezcla tipos (p. ej. `Int` + `Long`), debes unificar con conversión explícita.

### 4.5 String templates (imprescindible por productividad)
- Interpolación con `$variable`.
- Expresiones con `${expresión}` (llamadas, operaciones, propiedades).
- Escape de `$` literal: `"\$100"`.

Incluye:
- Multilínea con `"""..."""` y normalización con `trimIndent()` / `trimMargin()` cuando aplique.

---

## Preguntas clave del bloque

1. ¿Por qué Kotlin no necesita un entorno distinto al de Java?
2. ¿Qué papel juega Android Studio en el uso real de Kotlin?
3. ¿Por qué IntelliJ IDEA ofrece el mejor soporte para Kotlin?
4. ¿En qué casos es útil Kotlin Playground y en cuáles no?
5. ¿Cómo se ejecuta realmente un programa Kotlin en la JVM?

## 5) Null safety: cómo Kotlin te evita el NullPointerException (y cuándo NO)

### 5.1 El problema en Java (base conceptual)
- En Java, cualquier referencia puede ser `null` y el compilador no obliga a tratarlo.
- Resultado: `NullPointerException` aparece en **runtime**, no en compilación.

### 5.2 Tipos nullable y non-nullable (núcleo del tema)
- Por defecto, un tipo **no acepta null**: `String`
- Si puede ser null, debe declararse explícitamente: `String?`
- El compilador restringe el acceso a miembros de tipos nullable:
  - No puedes usar `x.length` si `x: String?` sin una estrategia segura.

### 5.3 Safe call `?.`
- Ejecuta el acceso solo si el receptor no es `null`.
- La expresión resultante suele volverse nullable:
  - `val len: Int? = nombre?.length`

### 5.4 Elvis `?:`
- Devuelve un valor por defecto si la izquierda es `null`.
- Patrón típico:
  - `val len = nombre?.length ?: 0`
- También se usa para **cortar flujo**:
  - `val x = nullable ?: return`
  - `val y = nullable ?: throw ...`

### 5.5 Not-null assertion `!!` (cuándo NO)
- Fuerza a tratar el valor como no-null.
- Si es `null` en runtime: `NullPointerException`.
- Regla de uso:
  - Evitarlo en producción salvo justificación clara (precondiciones, tests, invariantes comprobadas).

### 5.6 Safe cast `as?`
- `as` puede lanzar `ClassCastException`.
- `as?` devuelve `null` si no es casteable.
- Se combina típicamente con `?.` y `?:`.

### 5.7 `let` como patrón idiomático de manejo seguro
- `nullable?.let { ... }` ejecuta bloque solo si no es `null`.
- Dentro del bloque, el valor es tratado como no-null (smart cast).

---

## 6) Colecciones: List/Set/Map + mutabilidad (y por qué importa)

### 6.1 Inmutabilidad vs mutabilidad (concepto que debes explicar)
- Kotlin distingue:
  - Interfaces de solo lectura: `List`, `Set`, `Map`
  - Mutables: `MutableList`, `MutableSet`, `MutableMap`
- Diferencia clave: **API disponible**, no “inmutabilidad absoluta” del objeto subyacente.

Punto que suele confundir:
- `val`/`var` controla la **referencia**, no la mutabilidad interna.
  - `val lista = mutableListOf(...)` impide reasignar `lista`, pero permite `lista.add(...)`.

### 6.2 List / MutableList
- Lista ordenada, indexada, permite duplicados.
- Operaciones típicas:
  - Acceso: `[i]`, `get(i)`
  - Info: `size`, `isEmpty()`
  - Iteración: `for (e in lista)`, `withIndex()`
  - Mutación (solo en `MutableList`): `add`, `remove`, `removeAt`, `clear`, asignación por índice

### 6.3 Set / MutableSet
- Elementos únicos, sin orden garantizado.
- Operaciones típicas:
  - `add` (en mutable), `remove`, pertenencia `in`
  - Operaciones de conjunto: `union`, `intersect`, `subtract`

### 6.4 Map / MutableMap
- Pares clave-valor.
- Acceso por clave devuelve nullable: `map["k"] : V?`
- Patrones:
  - `getOrDefault`, `containsKey`, iteración por `entries` o destructuring `(k, v)`.

---

[BLOCK 4/4]

## 7) Control de flujo: if como expresión, when, rangos y bucles

### 7.1 `if` como expresión
- En Kotlin, `if` puede devolver un valor:
  - `val x = if (cond) a else b`
- En bloques multilínea, el valor de la rama es la **última expresión**.

### 7.2 `when`
- Sustituye y amplía `switch`:
  - Por valores
  - Por rangos (`in 1..10`)
  - Por tipos (`is String`) con smart cast
  - Sin argumento (`when { ... }`) como cadena de condiciones
- En uso como expresión, conviene cubrir todos los casos (o `else`).

### 7.3 Rangos
- `..` inclusivo, `until` exclusivo, `downTo` descendente, `step` para salto.
- Pertenencia: `in`, `!in`.

### 7.4 Bucles
- `for` sobre rangos, colecciones, mapas.
- `while` y `do-while`.
- Control: `break`, `continue`.
- Etiquetas para bucles anidados (`outer@ ... break@outer`).

---

## 8) Funciones: sintaxis, defaults, nombrados, vararg y funciones locales

### 8.1 Declaración
- `fun nombre(params): TipoRetorno { ... }`
- Retorno `Unit` equivale a `void` (se omite normalmente).

### 8.2 Funciones de expresión única
- `fun f(x: Int): Int = x * 2`
- Puede omitirse tipo de retorno si el compilador lo infiere de forma clara.

### 8.3 Parámetros por defecto
- Sustituyen sobrecargas típicas de Java.
- Permiten APIs más compactas y legibles.

### 8.4 Parámetros nombrados
- Mejoran legibilidad y reducen errores por orden.
- Se combinan con defaults para “saltarse” parámetros.

### 8.5 `vararg`
- Permite número variable de argumentos.
- Spread operator `*` para pasar arrays.

### 8.6 Funciones locales
- Funciones anidadas para encapsular validaciones o lógica auxiliar.

---

## 9) POO en Kotlin: constructores, properties/backing field, herencia, interfaces

### 9.1 Clases y propiedades
- Propiedades reemplazan el patrón Java de campos + getters/setters manuales.
- `val` (solo lectura), `var` (lectura/escritura).

### 9.2 Backing field `field`
- Cuando defines getter/setter personalizados, `field` representa el almacenamiento real.
- Se usa para evitar recursión en el setter y mantener invariantes.

### 9.3 Constructores
- Primario en la cabecera de la clase.
- `init { }` para lógica de inicialización.
- Secundarios si aportan variantes, pero en Kotlin se prefieren defaults y named args cuando es viable.

### 9.4 Herencia e interfaces
- (Recordatorio) Kotlin hace que las clases sean “cerradas” por defecto; la herencia debe ser explícita cuando aplique.
- `override` obligatorio.
- Interfaces pueden incluir implementaciones por defecto.

---

## 10) Clases especiales: data class, sealed class, enum class

### 10.1 `data class`
- Genera automáticamente: `equals`, `hashCode`, `toString`, `copy`, `componentN`.
- Uso típico: modelos de datos y DTOs.

### 10.2 `sealed class`
- Jerarquías cerradas para modelar estados.
- Permite `when` exhaustivo (sin `else` si están todos los casos cubiertos).

### 10.3 `enum class`
- Conjunto finito de constantes, puede incluir propiedades y métodos.

---

## 11) Object y companion object: “sin static” y patrones típicos

### 11.1 `object` (singleton)
- Declaración de instancia única con miembros y estado.

### 11.2 `companion object`
- Miembros asociados a la clase (equivalente práctico a `static`).
- Uso típico:
  - Constantes (`const val`)
  - Factories (`fun create(...)`)

### 11.3 `object expression`
- Objetos anónimos para implementar interfaces/clases base en línea.

---

## 12) Extensions: añadir funciones/props sin tocar la clase

### 12.1 Funciones de extensión
- Añaden comportamiento “externo” a un tipo sin herencia ni modificación del código fuente.

### 12.2 Propiedades de extensión
- Propiedades calculadas; no añaden estado real al objeto.

### 12.3 Extensions sobre nullable
- Utilidades sobre `T?` para normalizar validaciones (`isNullOrEmpty`, etc.).

---

## Preguntas clave (5–10) para cubrir el núcleo del tema (examen + desarrollo)
1) ¿Qué significa en Kotlin que la nulabilidad forme parte del sistema de tipos y cómo cambia eso el diseño del código respecto a Java?  
2) Explica `?.`, `?:`, `as?`, `let` y `!!`: qué resuelve cada uno y en qué casos `!!` es un riesgo real.  
3) Diferencia entre `val/var` y `List/MutableList`: qué controla cada uno y qué error conceptual se comete al confundirlos.  
4) ¿Por qué Kotlin obliga a conversiones numéricas explícitas y cómo se gestionan conversiones seguras desde `String`?  
5) Justifica por qué `if` y `when` se consideran expresiones en Kotlin y qué ventajas aporta en legibilidad/mantenibilidad.  
6) Explica los mecanismos de Kotlin que reducen “boilerplate” en modelos de datos y estados (data class + sealed class) y cómo impactan en el código.  
7) ¿Cómo sustituyen `object` y `companion object` el uso de `static` y qué patrones típicos aparecen en Android/backend?  
8) ¿Qué son las extensions (funciones/propiedades) y qué límites tienen (especialmente respecto a estado y override)?

---

## Bloque de código “tipo ejercicio para completar” (conceptos clave mezclados)
```kotlin
// OBJETIVO: completar aplicando null safety, when expresivo, colecciones mutables/inmutables,
// data class, sealed class y companion object.

data class Usuario(
    val id: Int,
    val nombre: String,
    val email: String?
)

sealed class Resultado {
    data class Ok(val usuario: Usuario) : Resultado()
    data class Error(val motivo: String) : Resultado()
}

class RepositorioUsuarios private constructor() {

    private val usuarios: MutableMap<Int, Usuario> = mutableMapOf()

    fun guardar(usuario: Usuario): Resultado {
        // TODO 1: validar nombre no vacío (si está vacío -> Error)
        // TODO 2: validar email si no es null (por ejemplo: contiene '@') usando let
        // TODO 3: guardar en el map por id y devolver Ok(usuario)
        return Resultado.Error("Pendiente")
    }

    fun buscarEmail(id: Int): String {
        // TODO 4: devolver el email del usuario o "Sin email"
        // PISTA: safe call + Elvis
        return "Pendiente"
    }

    fun contarPorDominio(): Map<String, Int> {
        // TODO 5: construir un Map dominio->conteo (dominio = parte después de '@')
        // - ignora usuarios sin email
        // - el resultado debe ser inmutable (Map)
        return emptyMap()
    }

    companion object {
        // TODO 6: implementar factory "crear()" que devuelva una instancia de RepositorioUsuarios
        fun crear(): RepositorioUsuarios {
            return RepositorioUsuarios()
        }
    }
}

fun clasificarEdad(edad: Int): String {
    // TODO 7: usar when con rangos para devolver:
    // 0..12 -> "Niño", 13..17 -> "Adolescente", 18..64 -> "Adulto", else -> "Otro"
    return "Pendiente"
}

fun main() {
    val repo = RepositorioUsuarios.crear()

    val u1 = Usuario(1, "Ana", "ana@example.com")
    val u2 = Usuario(2, "Luis", null)

    // TODO 8: guardar usuarios y mostrar por println el Resultado usando when exhaustivo
    // (Ok -> imprime nombre, Error -> imprime motivo)

    println(repo.buscarEmail(1))
    println(repo.buscarEmail(2))
    println(repo.contarPorDominio())
    println(clasificarEdad(25))
}
```

---

## Glosario de términos — Tema 14: Kotlin

- **Kotlin**  
  Lenguaje de programación moderno, estáticamente tipado y multiparadigma (POO + funcional), diseñado para la JVM y orientado a seguridad, concisión y mantenibilidad.

- **JVM (Java Virtual Machine)**  
  Máquina virtual que ejecuta bytecode Java/Kotlin. Permite portabilidad y acceso al ecosistema Java.

- **Interoperabilidad**  
  Capacidad de Kotlin para convivir con Java en el mismo proyecto, permitiendo llamadas bidireccionales entre ambos lenguajes.

- **Boilerplate**  
  Código repetitivo y estructural (getters/setters, equals, hashCode, toString) que no aporta lógica de negocio.

- **Inferencia de tipos**  
  Mecanismo por el cual el compilador deduce el tipo de una variable en tiempo de compilación a partir de su primera asignación.

- **Tipo non-null (`T`)**  
  Tipo que **no admite `null`**. El compilador impide accesos inseguros.

- **Tipo nullable (`T?`)**  
  Tipo que **puede ser `null`**. Obliga a usar operadores de acceso seguro.

- **Null safety**  
  Sistema de tipos de Kotlin que distingue explícitamente entre referencias nullable y non-nullable para evitar `NullPointerException`.

- **Safe call (`?.`)**  
  Operador que ejecuta el acceso solo si el receptor no es `null`, devolviendo `null` en caso contrario.

- **Operador Elvis (`?:`)**  
  Proporciona un valor por defecto o controla el flujo cuando el operando izquierdo es `null`.

- **Not-null assertion (`!!`)**  
  Fuerza el desempaquetado de un nullable; si el valor es `null`, lanza `NullPointerException`.

- **Safe cast (`as?`)**  
  Conversión de tipo segura que devuelve `null` si el casting no es posible.

- **`let`**  
  Scope function que ejecuta un bloque solo si el valor no es `null`, habilitando smart cast dentro del bloque.

- **`val`**  
  Referencia inmutable (no reasignable). Promueve inmutabilidad.

- **`var`**  
  Referencia mutable (reasignable).

- **Colecciones de solo lectura**  
  `List`, `Set`, `Map`. Exponen una API sin operaciones de mutación.

- **Colecciones mutables**  
  `MutableList`, `MutableSet`, `MutableMap`. Permiten modificar el contenido.

- **Expresión**  
  Construcción que devuelve un valor (por ejemplo, `if` y `when` en Kotlin).

- **`when`**  
  Estructura de control potente que reemplaza `switch` y soporta valores, rangos, tipos y condiciones.

- **Rangos**  
  Secuencias definidas con `..`, `until`, `downTo` y `step`, usadas en control de flujo e iteración.

- **Función de expresión única**  
  Función cuyo cuerpo es una sola expresión, definida con `=`.

- **Parámetros por defecto**  
  Valores asignados a parámetros que evitan sobrecargas de funciones.

- **Parámetros nombrados**  
  Llamadas a funciones indicando el nombre del parámetro para mayor legibilidad.

- **`vararg`**  
  Parámetro que acepta un número variable de argumentos.

- **Propiedad**  
  Abstracción que reemplaza campos + getters/setters; puede tener getter/setter personalizados.

- **Backing field (`field`)**  
  Campo implícito que almacena el valor real de una propiedad cuando se definen getters/setters personalizados.

- **Constructor primario**  
  Constructor definido en la cabecera de la clase, responsable de inicializar propiedades.

- **`init`**  
  Bloque de inicialización que se ejecuta al crear la instancia.

- **Herencia**  
  Mecanismo de reutilización donde una clase deriva de otra; en Kotlin debe declararse explícitamente cuando aplica.

- **Interfaz**  
  Contrato que define métodos y propiedades; puede incluir implementaciones por defecto.

- **`data class`**  
  Clase orientada a datos que genera automáticamente `equals`, `hashCode`, `toString`, `copy` y `componentN`.

- **`sealed class`**  
  Jerarquía cerrada de tipos, ideal para modelar estados y habilitar `when` exhaustivo.

- **`enum class`**  
  Conjunto finito de constantes, con soporte para propiedades y métodos.

- **`object`**  
  Declaración de singleton; crea una única instancia de forma automática.

- **`companion object`**  
  Miembros asociados a la clase (equivalente práctico a `static`), usados para constantes y factories.

- **Object expression**  
  Objeto anónimo creado en línea para implementar interfaces o clases base.

- **Extension function**  
  Función que añade comportamiento a un tipo existente sin herencia ni modificación del código fuente.

- **Extension property**  
  Propiedad calculada añadida a un tipo; no introduce estado real en el objeto.
