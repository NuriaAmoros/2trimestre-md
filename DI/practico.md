# Aclaración exacta de lo que entra por PARTES 

## 🟡 Parte 2 — Preguntas de Desarrollo (3 puntos)

En esta parte **NO hay código**, se pide **explicar**.

### Tema 12 — Apartado 8 (Prácticas JUnit)
Se puede pedir:
- Qué es **JUnit** y para qué se usa.
- Qué tipo de pruebas permite realizar.
- Ventajas de las pruebas automáticas frente a las manuales.
- Explicación de una **clase de pruebas JUnit**.
- Explicación de las **anotaciones**:
  - `@Test`
  - `@BeforeEach`
  - `@AfterEach`
  - `@BeforeAll`
  - `@AfterAll`
- **Orden de ejecución** de los métodos antes y después de las pruebas.

👉 Aquí entra **muy fuerte** lo de:
> “qué métodos se lanzan antes y después de las pruebas”.

---

### Tema 08 — Apartado 6
Se puede pedir:
- Qué son las **variables y valores calculados** en informes.
- Diferencia entre:
  - `$F{}` (Fields)
  - `$V{}` (Variables)
  - `$P{}` (Parámetros)
- Dónde se colocan en el informe (Detail, Summary, etc.).
- Para qué se usan (mostrar datos, cálculos, filtros).

---

### Tema 12 — Apartado 3 (Tipos de pruebas)
Se puede pedir:
- Clasificación de los **tipos de pruebas**.
- Explicar diferencias entre:
  - Pruebas unitarias
  - Integración
  - Regresión
  - Seguridad
  - Volumen / carga
- Caja blanca vs caja negra.

---

## 🔴 Parte 3 — Casos Prácticos (3 puntos)

Aquí **SÍ hay práctica / aplicación**, no solo teoría.

### Tema 12 — Apartado 8 (Casos prácticos JUnit)
Se puede pedir:
- Crear una **clase de pruebas JUnit**.
- Escribir métodos de prueba.
- Usar correctamente:
  - `@Test`
  - `@BeforeEach`
  - `@AfterEach`
- Comprobar resultados esperados.
- Simular un pequeño escenario de pruebas unitarias.

👉 Aquí no basta con saber qué es JUnit:  
👉 hay que **saber montarlo**.

---

### Tema 10 — Apartado 7 (JavaHelp)
Caso práctico relacionado con:
- **Sistema de ayuda JavaHelp**.
- Uso de:
  - `HelpSet`
  - `toc.xml`
  - `index.xml`
  - `map`
- **Ayuda contextual**, especialmente:
  - Asociación de ayuda a componentes.
  - Uso de **F1**.
- Entender cómo se integra la ayuda en una aplicación Java.

👉 Puede ser:
- Explicar el flujo, o
- Completar / razonar un caso de ayuda.

---

## Resumen mental rápido (para ir segura al examen)

### Desarrollo (Parte 2)
- Tema 12 → JUnit explicado (sin código).
- Tema 08 → `$F`, `$V`, `$P`.
- Tema 12 → Tipos de pruebas.

### Casos prácticos (Parte 3)
- Tema 12 → JUnit práctico.
- Tema 10 → JavaHelp práctico (muy probable F1).

Esto ya es el **mapa exacto de examen**, sin relleno.


## AÑADIDO IMPORTANTE — Comparación entre tipos de pruebas (dicho explícitamente por el profesor)

En el examen puede aparecer **comparar qué prueba hace qué y en qué se diferencia de otra**.  
No solo definirlas, sino **contrastar**.

---

## Comparaciones típicas que pueden pedir

### Pruebas unitarias vs pruebas de integración
- **Unitarias**
  - Evalúan métodos o clases de forma aislada.
  - Se centran en lógica interna.
  - Se automatizan habitualmente con **JUnit**.
- **Integración**
  - Evalúan cómo interactúan varios módulos juntos.
  - Se ejecutan después de las unitarias.
  - Detectan errores en la comunicación entre componentes.

👉 Diferencia clave:  
**aislado (unitaria)** vs **conjunto de módulos (integración)**.

---

### Pruebas de integración vs pruebas de sistema
- **Integración**
  - Evalúan grupos de módulos relacionados.
  - Todavía se distingue la estructura interna.
- **Sistema**
  - Evalúan la aplicación completa como un todo.
  - No se distinguen módulos internos.

👉 Diferencia clave:  
**por módulos** vs **visión global del sistema**.

---

### Pruebas funcionales vs pruebas de regresión
- **Funcionales**
  - Comprueban que la aplicación cumple los requisitos funcionales.
  - Se basan en lo que debe hacer el sistema.
- **Regresión**
  - Comprueban que cambios nuevos no rompen funcionalidades antiguas.
  - Se repiten tras modificaciones.

👉 Diferencia clave:  
**verificar requisitos** vs **verificar que no se rompe lo anterior**.

---

### Pruebas manuales vs pruebas automáticas
- **Manuales**
  - Ejecutadas por una persona.
  - Más lentas.
  - Dependientes del criterio humano.
- **Automáticas**
  - Ejecutadas por herramientas (JUnit, JMeter).
  - Rápidas y repetibles.
  - Ideales para regresión.

👉 Diferencia clave:  
**persona** vs **herramienta**.

---

### Pruebas de usuario vs pruebas de aceptación
- **Usuario**
  - Realizadas por usuarios reales.
  - Detectan problemas de usabilidad.
  - No siguen criterios técnicos estrictos.
- **Aceptación**
  - Definidas por el cliente.
  - Verifican si el producto cumple lo contratado.
  - Deciden si el software se acepta o no.

👉 Diferencia clave:  
**experiencia de uso** vs **validación contractual**.

---

### Pruebas alfa vs pruebas beta
- **Alfa**
  - Internas.
  - En entorno de desarrollo.
  - Usuarios simulados.
- **Beta**
  - Externas.
  - En entorno real.
  - Usuarios finales (beta testers).

👉 Diferencia clave:  
**interno** vs **externo**.

---

## Frase tipo examen (muy útil)
> *Las pruebas se diferencian por el momento en que se ejecutan, el nivel del sistema que evalúan y el objetivo que persiguen.*

Esto conecta **todas las comparaciones** y suele puntuar bien.

---

## AÑADIDO IMPORTANTE — Comparación entre tipos de pruebas 

En el examen puede aparecer **comparar qué prueba hace qué y en qué se diferencia de otra**.  
No solo definirlas, sino **contrastar**.

---

## Comparaciones típicas que pueden pedir

### Pruebas unitarias vs pruebas de integración
- **Unitarias**
  - Evalúan métodos o clases de forma aislada.
  - Se centran en lógica interna.
  - Se automatizan habitualmente con **JUnit**.
- **Integración**
  - Evalúan cómo interactúan varios módulos juntos.
  - Se ejecutan después de las unitarias.
  - Detectan errores en la comunicación entre componentes.

👉 Diferencia clave:  
**aislado (unitaria)** vs **conjunto de módulos (integración)**.

---

### Pruebas de integración vs pruebas de sistema
- **Integración**
  - Evalúan grupos de módulos relacionados.
  - Todavía se distingue la estructura interna.
- **Sistema**
  - Evalúan la aplicación completa como un todo.
  - No se distinguen módulos internos.

👉 Diferencia clave:  
**por módulos** vs **visión global del sistema**.

---

### Pruebas funcionales vs pruebas de regresión
- **Funcionales**
  - Comprueban que la aplicación cumple los requisitos funcionales.
  - Se basan en lo que debe hacer el sistema.
- **Regresión**
  - Comprueban que cambios nuevos no rompen funcionalidades antiguas.
  - Se repiten tras modificaciones.

👉 Diferencia clave:  
**verificar requisitos** vs **verificar que no se rompe lo anterior**.

---

### Pruebas manuales vs pruebas automáticas
- **Manuales**
  - Ejecutadas por una persona.
  - Más lentas.
  - Dependientes del criterio humano.
- **Automáticas**
  - Ejecutadas por herramientas (JUnit, JMeter).
  - Rápidas y repetibles.
  - Ideales para regresión.

👉 Diferencia clave:  
**persona** vs **herramienta**.

---

### Pruebas de usuario vs pruebas de aceptación
- **Usuario**
  - Realizadas por usuarios reales.
  - Detectan problemas de usabilidad.
  - No siguen criterios técnicos estrictos.
- **Aceptación**
  - Definidas por el cliente.
  - Verifican si el producto cumple lo contratado.
  - Deciden si el software se acepta o no.

👉 Diferencia clave:  
**experiencia de uso** vs **validación contractual**.

---

### Pruebas alfa vs pruebas beta
- **Alfa**
  - Internas.
  - En entorno de desarrollo.
  - Usuarios simulados.
- **Beta**
  - Externas.
  - En entorno real.
  - Usuarios finales (beta testers).

👉 Diferencia clave:  
**interno** vs **externo**.

---

## Frase tipo examen (muy útil)
> *Las pruebas se diferencian por el momento en que se ejecutan, el nivel del sistema que evalúan y el objetivo que persiguen.*

Esto conecta **todas las comparaciones** y suele puntuar bien.

---
# RESUMEN CLAVE PARA EXAMEN — MUY CONCRETO

---

## TEMA 12 — JUnit (cómo se crea y para qué sirven las @)

## 1. Cómo crear una clase JUnit (muy concreto)
1. Crear **nueva clase Java**.
2. Importar **JUnit**.
3. Escribir métodos de prueba.
4. Ejecutar la clase como **JUnit Test**.

Se usa para:
- Probar métodos.
- Ver si el resultado es el esperado.
- Detectar errores automáticamente.

---

## 2. Anotaciones JUnit (las importantes, muy cortas)

- `@Test`  
  → Marca un método como **prueba**.

- `@BeforeEach`  
  → Se ejecuta **antes de cada prueba**.  
  Inicializa datos.

- `@AfterEach`  
  → Se ejecuta **después de cada prueba**.  
  Limpia datos.

- `@BeforeAll`  
  → Se ejecuta **una vez antes de todas las pruebas**.  
  Preparación general.

- `@AfterAll`  
  → Se ejecuta **una vez al final**.  
  Liberación final.

### Orden real de ejecución
1. `@BeforeAll`
2. (`@BeforeEach` → `@Test` → `@AfterEach`)  
3. `@AfterAll`

---

## Para qué sirve JUnit (frase examen)
JUnit sirve para **automatizar pruebas unitarias** y comprobar que los métodos funcionan correctamente tras cambios.

---

# TEMA 8 — Variables y bandas (MUY CLARO)

## 3. Bandas del informe — Detail
- **Detail**
  - Se repite **por cada registro**.
  - Aquí van los `$F{}`.
  - Muestra datos fila a fila.

---

## 4. Variables en JasperReports (para qué se usa cada una)

### `$F{}` — Field
- Viene de la **base de datos**.
- Se usa para **mostrar datos**.
- Va en **Detail**.

Ejemplo:
- Nombre
- Fecha
- Precio

---

### `$V{}` — Variable
- Es un **valor calculado**.
- Se usa para:
  - Contar
  - Sumar
  - Totales
- Va en **Summary** o **Footer**.

Ejemplo:
- Total compras
- Número de registros

---

### `$P{}` — Parameter
- Dato **externo** al informe.
- Se usa para:
  - Filtros
  - Personalización
- Se usa en consultas o textos.

Ejemplo:
- Fecha inicio
- Id cliente

---

## Diferencia clave (frase de examen)
- `$F{}` muestra datos  
- `$V{}` calcula datos  
- `$P{}` recibe datos  

---

## Relación rápida
- Detail → `$F{}`
- Summary → `$V{}`
- Filtros → `$P{}`

---

## Mini resumen mental
- JUnit → pruebas automáticas
- `@Test` → prueba
- `@Before` / `@After` → antes y después
- `$F` → base de datos
- `$V` → cálculo
- `$P` → filtro externo

---
# TEMA 10 — JavaHelp (paso a paso, 1 por 1)

## 1/6 — help_set.hs (qué es y qué hay que saber)

### Qué es
- Es el **archivo principal** del sistema de ayuda.
- Su función es **enlazar**:
  - el `map.jhm`
  - el `toc.xml`
  - el `index.xml`

### Qué te pueden pedir (rellenar huecos)
- Dónde se referencia el **map**.
- Dónde se indica el **toc**.
- Dónde se indica el **index**.

### Plantilla mínima (para reconocer y completar)
```xml
<helpset version="2.0">
  <title>...</title>

  <maps>
    <mapref location="map.jhm"/>
  </maps>

  <view>
    <type>javax.help.TOCView</type>
    <data>toc.xml</data>
  </view>

  <view>
    <type>javax.help.IndexView</type>
    <data>index.xml</data>
  </view>
</helpset

```



## 2/6 — map.jhm (ID ↔ HTML)

### Qué es
- Es el archivo que **relaciona un identificador** con una **página HTML**.
- Es imprescindible para:
  - la **ayuda contextual**
  - el uso de **F1**

### Para qué sirve
- Cuando desde Java se pide mostrar una ayuda con un ID,
  JavaHelp busca ese ID en el `map.jhm`
  y abre el HTML correspondiente.

👉 **Sin map, F1 no funciona.**

---

### Estructura mínima que debes reconocer
```xml
<map version="1.0">
  <mapID target="intro" url="html/introduccion.html"/>
  <mapID target="altaSocio" url="html/alta_socios.html"/>
</map>
```


## 3/6 — toc.xml (estructura de la ayuda)

### Qué es
- Es el archivo que define la **estructura jerárquica** de la ayuda.
- Es lo que se ve como **árbol de contenidos** en la ventana de ayuda.

---

### Para qué sirve
- Organiza los temas por niveles:
  - secciones
  - subsecciones
- Facilita la navegación del usuario.

👉 **No abre la ayuda**, solo **la organiza**.

---

### Estructura mínima que debes reconocer
- El toc define la estructura de la ayuda
```xml
<toc version="2.0">
  <tocitem text="Introducción" target="intro">
    <tocitem text="Alta de socios" target="altaSocio"/>
    <tocitem text="Reservas" target="reservas"/>
  </tocitem>
</toc>

```

## 4/6 — index.xml (índice alfabético)

### Qué es
- Es el archivo que define el **índice alfabético** de la ayuda.
- Permite **buscar por palabras clave**.
- helpset.hs **archico principal**
- enableHelpOnButton **abre la ayuda al hacer clic.**

---

### Para qué sirve
- Acceso rápido a temas sin navegar por el árbol.
- El usuario escribe o selecciona un término y va directo al contenido.

👉 **No organiza** (eso lo hace el toc), **facilita la búsqueda**.

---

### Estructura mínima que debes reconocer
```xml
<index version="1.0">
  <indexitem text="Socios" target="altaSocio"/>
  <indexitem text="Reservas" target="reservas"/>
</index>

```


## 6/6 — Ayuda CONTEXTUAL con F1 (LA MÁS IMPORTANTE)

### Qué es
- Es la ayuda que se abre **al pulsar F1**.
- Depende del **componente que tiene el foco**.

👉 Esto es lo que **más suele caer en el examen**.

---

### Qué se hace en clase
1. Elegir un **componente** (campo, botón, combo…).
2. Asociarle un **ID del map.jhm**.
3. Al pulsar **F1**, se abre su ayuda específica.

---

### Código típico visto en clase (para completar en examen)

```java
hb.enableHelpKey(textFieldTarifa, "tarifas", hs);
```
## Diferencia entre
```java
hb.enableHelpOnButton(botonAyuda, "intro", hs);
hb.enableHelpKey(textFieldNombre, "altaSocio", hs);
```
- enableHelpOnButton → clic manual

- enableHelpKey → F1, ayuda contextual

# TEMA 12 — JUnit (paso a paso, 1 por 1)

## 1/6 — Qué es JUnit y para qué se usa (en examen)

### Qué es
- JUnit es una **herramienta para hacer pruebas unitarias en Java**.

### Para qué se usa
- Comprobar que un **método funciona correctamente**.
- Ver si el resultado obtenido es el **esperado**.
- Detectar errores cuando se cambia el código (regresión).

👉 **JUnit = pruebas automáticas de métodos**.

---

### Qué NO es
- No es para probar interfaces gráficas.
- No es para probar toda la aplicación completa.
- Eso serían pruebas de sistema o de usuario.

---

### Frase corta tipo examen
> JUnit se utiliza para automatizar pruebas unitarias y verificar el correcto funcionamiento de métodos de forma repetida.

---


## 2/6 — Crear una clase JUnit (estructura mínima)

### Qué es una clase JUnit
- Es una **clase Java independiente**.
- Sirve **solo para probar** otras clases.
- Una clase JUnit contiene métodos de prueba, no lógica de negocio.

---

### Cómo se crea (lo visto en clase)
1. Crear una **nueva clase Java**.
2. Nombre habitual:  
   - `ClaseTest`  
   - Ejemplo: `CalculadoraTest`
3. Importar JUnit.

---

### Estructura mínima que debes reconocer / escribir

```java
class CalculadoraTest {
}
```


## 3/6 — `@Test` (la anotación principal)

### Qué es
- `@Test` **marca un método como prueba**.
- Sin `@Test`, el método **no se ejecuta** como prueba.

---

### Para qué se usa
- Ejecutar un método.
- Comparar **resultado esperado** vs **resultado real**.
- Decidir si la prueba **pasa o falla**.

---

### Ejemplo mínimo (tal cual visto en clase)
```java
@Test
void testSuma() {
    int resultado = Calculadora.sumar(2, 3);
    assertEquals(5, resultado);
}
```

## 4/6 — `@BeforeEach` (antes de cada prueba)

- @BeforeEach se ejecuta antes de cada prueba para preparar el entorno


### Qué es
- Método que se ejecuta **ANTES de cada `@Test`**.

### Para qué se usa
- Preparar datos comunes.
- Inicializar objetos.
- Dejar el entorno listo para la prueba.

👉 Se ejecuta **una vez por cada test**, justo antes.

---

### Ejemplo típico (visto en clase)
```java
@BeforeEach
void setUp() {
    calculadora = new Calculadora();
}
```


## 5/6 — `@AfterEach` (después de cada prueba)

### Qué es
- Método que se ejecuta **DESPUÉS de cada `@Test`**.

### Para qué se usa
- Limpiar datos.
- Liberar recursos.
- Dejar el entorno limpio para la siguiente prueba.
- @AfterEach se ejecuta después de cada prueba para limpiar el entorno.
- limpia después de cada test.

👉 Se ejecuta **una vez por cada test**, al terminar.

---

### Ejemplo típico (visto en clase)
```java
@AfterEach
void tearDown() {
    calculadora = null;
}
```


## 6/6 — `@BeforeAll` y `@AfterAll` (una sola vez)

### Qué son
- Métodos que se ejecutan **una única vez** en toda la clase de pruebas.

---

### `@BeforeAll`
- Se ejecuta **ANTES de todos los tests**.
- Se usa para:
  - Preparación global
  - Configuración común costosa
  - @BeforeAll y @AfterAll se ejecutan una sola vez para toda la clase de pruebas.

⚠️ Normalmente el método debe ser **static**.

```java
@BeforeAll
static void initAll() {
    // preparación global
}
```