# TEMA 15 — Programación funcional, estructuras modernas y entorno iOS (superapuntes unificados)



---

## Índice
1. Cambio de paradigma en programación moderna  
2. Programación imperativa vs declarativa  
3. Inmutabilidad y gestión del estado  
4. Funciones como ciudadanos de primera clase  
5. Operaciones funcionales sobre colecciones  
6. Evaluación perezosa (lazy evaluation)  
7. Scope functions (Kotlin)  
8. Persistencia declarativa moderna  
9. Arquitecturas reactivas en desarrollo móvil  
10. Ecosistema Apple: MacOS, iOS y Xcode  
11. Lenguajes para iOS y Cocoa Touch  
12. Creación básica de proyectos en Xcode  
13. Síntesis técnica final (qué entra y qué no)

---

## 1. Cambio de paradigma en programación moderna
La programación moderna en Swift y Kotlin se basa en **modelos declarativos y funcionales**, frente al enfoque imperativo clásico de Java.  
El objetivo no es describir *cómo* ejecutar cada paso, sino *qué transformación* se desea aplicar sobre los datos.

Este paradigma:
- Reduce código repetitivo.
- Minimiza efectos secundarios.
- Facilita el mantenimiento, testing y concurrencia.
- Encaja de forma natural con arquitecturas reactivas (Flow, Combine).

---

## 2. Programación imperativa vs declarativa
**Imperativa**:
- Uso explícito de bucles (`for`, `while`).
- Variables mutables.
- Control detallado del flujo de ejecución.

**Declarativa / funcional**:
- Transformaciones encadenadas (`map`, `filter`, `reduce`).
- Menor dependencia del estado mutable.
- Código más expresivo y legible.

La programación funcional no elimina el control de flujo, sino que **lo abstrae en operaciones semánticas**.

---

## 3. Inmutabilidad y gestión del estado
La **inmutabilidad** implica que los datos no se modifican una vez creados.  
En su lugar, se generan **copias modificadas**.

Ventajas clave:
- Seguridad en entornos concurrentes.
- Estado predecible.
- Menos errores difíciles de depurar.
- Mejor optimización por parte del compilador.

Swift y Kotlin fomentan:
- `val` / `let` como norma.
- `data class` y `struct` con copia por valor.

---

## 4. Funciones como ciudadanos de primera clase
En Swift y Kotlin, las funciones pueden:
- Asignarse a variables.
- Pasarse como parámetros.
- Devolverse como resultado.

Conceptos esenciales:
- Lambdas (Kotlin).
- Closures (Swift).
- Captura de valores del contexto.
- Trailing closures (Swift).

Esto permite:
- Código reutilizable.
- Composición de comportamientos.
- APIs expresivas y declarativas.

---

## 5. Operaciones funcionales sobre colecciones
Operaciones fundamentales:
- **map**: transforma elementos.
- **filter**: selecciona por condición.
- **reduce / fold**: acumula valores.
- **flatMap / compactMap**: aplana estructuras.
- **sorted / reversed**: ordenación.
- **groupBy / Dictionary(grouping:)**: agrupación.
- **take / drop / prefix**: selección parcial.

Estas operaciones:
- Sustituyen bucles explícitos.
- Son combinables.
- Definen pipelines de datos claros.

---

## 6. Evaluación perezosa (lazy evaluation)
La evaluación perezosa retrasa la ejecución hasta que el resultado es necesario.

- Kotlin: `Sequence`
- Swift: `.lazy`

Diferencia clave:
- **Eager**: procesa toda la colección.
- **Lazy**: procesa solo lo necesario.

Es fundamental para:
- Colecciones grandes.
- Operaciones encadenadas.
- Optimización de rendimiento.

---

## 7. Scope functions (Kotlin)
Funciones para ejecutar bloques en el contexto de un objeto:

| Función | Contexto | Retorno | Uso principal |
|------|--------|--------|-------------|
| let | it | resultado | Transformaciones, nullables |
| run | this | resultado | Lógica y cálculo |
| with | this | resultado | Operar sin extensión |
| apply | this | objeto | Configuración |
| also | it | objeto | Logging / efectos secundarios |

Son exclusivas de Kotlin y **muy preguntables**.

---

## 8. Persistencia declarativa moderna
### Android
- **Room** como ORM.
- **Flow** para flujos reactivos.
- DAO declarativos con consultas tipadas.
- Integración natural con MVVM.

### iOS
- **SwiftData** (iOS 17+): modelo declarativo.
- **Core Data** (legacy): persistencia clásica.
- Uso de predicados y transformaciones funcionales.

Objetivo común:
- Separar datos, lógica y UI.
- Reaccionar automáticamente a cambios.

---

## 9. Arquitecturas reactivas en desarrollo móvil
### MVVM
- **Model**: datos.
- **ViewModel**: lógica + estado observable.
- **View**: UI reactiva.

### Repository Pattern
- Abstrae el origen de datos.
- Permite combinar local + remoto.
- Facilita testing.

### Single Source of Truth
- Una única fuente de datos.
- Flujo unidireccional.
- UI siempre sincronizada.

---

## 10. Ecosistema Apple: MacOS, iOS y Xcode
- **MacOS X**: sistema operativo de Apple basado en UNIX.
- Evolución continua (no versiones independientes).
- iOS comparte base tecnológica con MacOS.

Recomendación técnica:
- Usar siempre la **última versión estable** para desarrollo.

---

## 11. Lenguajes para iOS y Cocoa Touch
- **Swift** y **Objective-C**.
- API central: **Cocoa Touch**.
- Swift es el presente y futuro:
  - Código conciso.
  - Tipado fuerte.
  - Gestión automática de memoria.
  - Mejor integración con herramientas modernas.

Objective-C persiste por compatibilidad legacy.

---

## 12. Creación básica de proyectos en Xcode
Xcode es:
- El **único IDE oficial** para iOS/MacOS.
- Exclusivo de sistemas Apple.

Proceso esencial:
1. Crear proyecto.
2. Seleccionar tipo de app.
3. Elegir Swift como lenguaje.
4. Configurar identificadores.
5. Estructura MVC/MVVM inicial.

Conceptos evaluables:
- Estructura del proyecto.
- Uso de Storyboard / SwiftUI (conceptual).
- Relación vistas–código.

---

## 13. Síntesis técnica final (qué entra y qué no)

### Entra seguro:
- Programación funcional (map, filter, reduce).
- Inmutabilidad.
- Funciones de orden superior.
- Lazy evaluation.
- Scope functions (Kotlin).
- MVVM + Repository.
- Room / SwiftData (conceptual).
- MacOS, iOS, Xcode, Swift.

### No prioritario:
- Historia narrativa de Apple.
- Listados exhaustivos de versiones.
- Casos prácticos redactados.
- Bibliografía.
- Opiniones y reflexiones finales.

---

## Conclusión técnica
Este tema conecta **lenguaje, arquitectura y entorno real de desarrollo móvil**.  
No trata solo de aprender Swift o Kotlin, sino de **pensar en flujos de datos, transformaciones inmutables y sistemas reactivos**, que es exactamente lo que exige el desarrollo profesional actual.

---

# Glosario — TEMA 15: Programación funcional, estructuras modernas y entorno iOS

## Objetivo del glosario
Definir términos **técnicos y examinables** del Tema 15 (Swift/Kotlin, programación funcional, persistencia y arquitectura móvil), evitando material narrativo.

## Índice
1. Paradigmas y estado  
2. Funciones y closures  
3. Operaciones funcionales sobre colecciones  
4. Evaluación perezosa  
5. Scope functions (Kotlin)  
6. Persistencia moderna  
7. Arquitecturas reactivas  
8. Ecosistema Apple y herramientas iOS

---

## 1) Paradigmas y estado
- **Programación imperativa**: paradigma en el que se especifica el **cómo** (pasos concretos) mediante instrucciones secuenciales, bucles y mutación de variables.
- **Programación declarativa**: paradigma que expresa el **qué** se quiere obtener, delegando el **cómo** a abstracciones del lenguaje (transformaciones, expresiones, APIs).
- **Programación funcional**: estilo declarativo centrado en **transformaciones de datos** mediante funciones (a menudo puras), minimizando estado mutable y efectos secundarios.
- **Estado (state)**: conjunto de valores que representan la situación actual de un sistema/objeto (variables, propiedades, datos persistidos) en un instante.
- **Estado mutable**: estado que puede cambiar en el tiempo mediante asignaciones; incrementa el riesgo de inconsistencias y errores por orden de ejecución.
- **Inmutabilidad**: propiedad por la que un valor/objeto **no puede modificarse** tras su creación; las “modificaciones” se modelan como **nuevos valores**.
- **Efecto secundario**: operación que modifica el estado externo al resultado de la función (I/O, logging, escritura en BD, mutación de variables capturadas).
- **Predictibilidad**: capacidad de razonar sobre el resultado de un código a partir de sus entradas, sin depender de estado oculto o cambios externos.
- **Concurrencia**: ejecución solapada de tareas (hilos/corrutinas); el estado mutable compartido introduce riesgos de condiciones de carrera.

---

## 2) Funciones y closures
- **Función de primera clase (first-class function)**: función tratable como valor: puede guardarse en variables, pasarse como parámetro y devolverse.
- **Función de orden superior (higher-order function)**: función que recibe funciones como parámetros y/o devuelve funciones como resultado.
- **Lambda (Kotlin)**: función anónima definida como expresión, normalmente usada como argumento en APIs funcionales.
- **Closure (Swift)**: bloque de código (función anónima) que puede **capturar** valores del contexto donde se declara.
- **Captura (capture)**: mecanismo por el que una lambda/closure “recuerda” y puede acceder a variables del ámbito externo.
- **Trailing closure (Swift)**: sintaxis que permite escribir el closure **fuera** de los paréntesis cuando es el último parámetro, mejorando legibilidad.
- **Parámetro implícito `it` (Kotlin)**: nombre implícito del único parámetro de una lambda cuando no se declara explícitamente.
- **Parámetros `$0, $1…` (Swift)**: identificadores posicionales para parámetros de closures en sintaxis abreviada.
- **Composición de funciones**: construcción de una función aplicando otra sobre su resultado (encadenamiento `f(g(x))`).

---

## 3) Operaciones funcionales sobre colecciones
- **Colección**: estructura de datos que agrupa elementos (listas, conjuntos, mapas/diccionarios).
- **Transformación**: operación que produce una nueva colección/valor aplicando una regla a los elementos (p. ej. `map`).
- **Predicado**: función booleana que expresa una condición sobre un elemento (p. ej. para `filter`).
- **`map`**: operación que transforma cada elemento en otro valor, manteniendo cardinalidad (salvo variaciones específicas).
- **`filter`**: operación que conserva solo los elementos que cumplen un predicado.
- **`reduce`**: operación de acumulación que colapsa una colección en un único valor combinando elementos sucesivamente.
- **`fold` (Kotlin)**: variante de acumulación con **valor inicial** explícito; evita casos vacíos y define tipo de acumulador.
- **`flatMap`**: operación que transforma y **aplana** (flatten) colecciones anidadas en una única colección.
- **`compactMap` (Swift)**: transforma y elimina resultados `nil` (aplana “opcionalidad”).
- **`mapNotNull` (Kotlin)**: transforma y elimina resultados `null`.
- **`sorted` / `sortedBy`**: operaciones de ordenación por orden natural o por clave/criterio.
- **`reversed`**: invierte el orden (según implementación puede ser vista/colección).
- **`groupBy` (Kotlin)**: agrupa elementos por una clave y devuelve un mapa clave→lista.
- **`Dictionary(grouping:)` (Swift)**: agrupación equivalente en Swift.
- **Encadenamiento (chaining)**: composición secuencial de operaciones (`filter().map().sorted()...`) formando un pipeline.

---

## 4) Evaluación perezosa (Lazy evaluation)
- **Evaluación eager**: las operaciones se ejecutan inmediatamente y recorren toda la colección.
- **Evaluación lazy**: las operaciones se ejecutan solo cuando se solicita un resultado terminal; procesa **lo mínimo necesario**.
- **Operación intermedia**: transforma un flujo/colección y devuelve una nueva estructura lazy (no ejecuta por sí sola).
- **Operación terminal**: materializa resultado (lista/valor) y **dispara** la ejecución de la cadena lazy.
- **`Sequence` (Kotlin)**: abstracción lazy para pipelines sobre colecciones, ejecutada al consumir con terminales (`toList`, `first`, etc.).
- **`.lazy` (Swift)**: vista lazy que retrasa operaciones hasta materialización (`Array(...)`, `prefix`, etc.).
- **Corto-circuito (short-circuit)**: finalización anticipada de un pipeline cuando una terminal como `first`, `take/prefix` ya satisface el resultado.

---

## 5) Scope functions (Kotlin)
- **Scope function**: función que ejecuta un bloque en el contexto de un objeto para configurar, transformar o realizar efectos secundarios.
- **Context receiver**: forma de referirse al objeto dentro del bloque (`this` o `it`) según la scope function.
- **`let`**: contexto `it`, retorna el resultado del bloque; común para nullables y transformaciones.
- **`run`**: contexto `this`, retorna el resultado del bloque; útil para lógica sobre un objeto.
- **`with`**: función no extension; contexto `this`, retorna resultado del bloque; agrupa operaciones.
- **`apply`**: contexto `this`, retorna el propio objeto; típica para inicialización/configuración estilo builder.
- **`also`**: contexto `it`, retorna el propio objeto; típica para logging/validaciones sin romper la cadena.

---

## 6) Persistencia moderna
- **Persistencia**: almacenamiento de datos de forma duradera (BD local, archivos, remoto) para sobrevivir a cierres de app.
- **ORM (Object-Relational Mapping)**: capa que mapea tablas a objetos/entidades para reducir SQL manual y aportar tipado.
- **Room (Android)**: ORM oficial sobre SQLite con entidades, DAOs y validación de consultas en compilación.
- **Entidad (`@Entity`)**: clase que representa una tabla (Room) con columnas y clave primaria.
- **DAO (`@Dao`)**: interfaz de acceso a datos que declara consultas y operaciones CRUD.
- **CRUD**: Create, Read, Update, Delete; operaciones básicas sobre datos persistidos.
- **Flow (Kotlin)**: stream asíncrono reactivo; emite valores en el tiempo y permite transformar flujos de datos.
- **SwiftData**: persistencia declarativa moderna en iOS (modelado con anotaciones, consultas declarativas).
- **Core Data**: framework clásico de persistencia en Apple; modelo de objetos + contexto de persistencia.
- **Predicado**: condición formal para filtrar resultados en una consulta (Room SQL, Core Data NSPredicate, SwiftData predicates).

---

## 7) Arquitecturas reactivas
- **Arquitectura reactiva**: diseño en el que la UI se actualiza automáticamente en respuesta a cambios de estado/datos.
- **MVVM**: patrón que separa Model (datos), View (UI) y ViewModel (lógica + estado observable).
- **ViewModel**: capa que expone datos en formato consumible por la vista, aplica transformaciones y coordina casos de uso.
- **Binding / Observabilidad**: mecanismo por el que la UI observa cambios y re-renderiza (Flow/StateFlow, Combine, Published).
- **Repository Pattern**: capa que abstrae el origen de datos (local/remoto) y centraliza la política de obtención/actualización.
- **Single Source of Truth (SSOT)**: principio por el que existe una única fuente autoritativa del estado para evitar divergencias.
- **Flujo unidireccional de datos**: datos fluyen en una dirección (fuente→transformación→UI), reduciendo incoherencias.

---

## 8) Ecosistema Apple y herramientas iOS
- **macOS**: sistema operativo de Apple (base UNIX) requerido para desarrollo nativo iOS con herramientas oficiales.
- **iOS**: sistema operativo móvil de Apple; comparte fundamentos con macOS en frameworks y tooling.
- **Xcode**: IDE oficial de Apple para desarrollo iOS/macOS; integra editor, compilador, simulador y herramientas de build.
- **SDK**: conjunto de librerías/herramientas para compilar y ejecutar apps para una plataforma concreta (iOS SDK).
- **Cocoa Touch**: frameworks base de iOS para UI, eventos, ciclo de vida de app y servicios del sistema.
- **Swift**: lenguaje moderno principal para iOS (tipado fuerte, seguridad y ecosistema actual).
- **Objective-C**: lenguaje legacy aún presente por compatibilidad con bases de código antiguas.
- **Simulador**: entorno de ejecución virtual en Xcode para probar apps sin dispositivo físico.
- **Provisioning / Signing (conceptual)**: proceso de firma y permisos para ejecutar apps en dispositivos y distribuirlas.

---

