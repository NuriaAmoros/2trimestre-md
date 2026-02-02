# Tema 12 — Realización de pruebas

## Objetivo del tema
Identificar los **tipos de pruebas que entran**, comprender los **bloques funcionales evaluables** y saber **crear y ejecutar pruebas unitarias con JUnit**, incluyendo **anotaciones**, **métodos que se ejecutan antes y después** y su finalidad.

## Índice
1. Apartado 3. Tipos de pruebas  
2. Apartados 5 y 6. Pruebas de integración, sistema, regresión y funcionales  
3. Apartado 8. Prácticas JUnit  
4. Apartados 9, 10 y 11. Otros tipos de pruebas  
5. JUnit: creación de una clase de pruebas y anotaciones

---

## 1. Apartado 3. Tipos de pruebas

Clasificación general que entra a examen:

- **Pruebas unitarias**
  - Verifican unidades individuales: métodos, funciones o clases.
  - Se centran en caminos lógicos concretos.
- **Pruebas de integración**
  - Evalúan la interacción entre módulos ya probados individualmente.
- **Pruebas de regresión**
  - Reejecución de pruebas tras modificaciones para comprobar que no se han introducido nuevos errores.
- **Pruebas de seguridad**
  - Evalúan mecanismos de protección, autenticación e integridad.
- **Pruebas de volumen y carga**
  - Comprueban el comportamiento ante grandes cantidades de datos o accesos simultáneos.

---

## 2. Apartados 5 y 6. Pruebas de integración, sistema, regresión y funcionales

### Pruebas de integración y sistema
- **Integración**
  - Ascendente: desde módulos inferiores a superiores.
  - Descendente: desde el módulo principal hacia los subordinados.
- **Sistema**
  - Evalúan el sistema completo como un todo, sin separar módulos.

### Pruebas de regresión
- Locales: errores introducidos por cambios recientes.
- Al descubierto: errores latentes que aparecen tras modificaciones.
- Remotas: errores surgidos al integrar partes que individualmente funcionaban.

Son **imprescindibles** para validar cambios.

### Pruebas funcionales
- Comprueban que la aplicación cumple los **requisitos funcionales** definidos.
- Deben documentarse.
- Se relacionan con normas de calidad como ISO 25010.

---

## 3. Apartado 8. Prácticas JUnit

JUnit es una librería Java para realizar **pruebas unitarias automáticas**.

Características clave:
- Permite validar el comportamiento de métodos.
- Automatiza la ejecución repetida de pruebas.
- Es especialmente útil para pruebas de regresión.

Uso típico:
- Probar métodos sin interfaz gráfica.
- Comprobar resultados esperados frente a resultados reales.

---

## 4. Apartados 9, 10 y 11. Otros tipos de pruebas

### Pruebas de usuario (Apartado 9)
- Realizadas por **usuarios reales**, no expertos.
- Detectan problemas de usabilidad.
- Basadas en observación y cuestionarios.
- Se recomienda un mínimo de 15 usuarios.

### Pruebas de aceptación (Apartado 10)
- Definidas por el **cliente o usuario final**.
- Verifican que el software cumple lo especificado.
- Se ejecutan antes de la implantación definitiva.
- Deben documentarse.

### Versiones alfa y beta (Apartado 11)
- **Alfa**
  - Primera versión.
  - Probada internamente por desarrolladores o expertos.
- **Beta**
  - Versión casi definitiva.
  - Probada por usuarios finales (beta testers).
  - Se ejecuta fuera del entorno de desarrollo.

---

## 5. JUnit: creación de una clase de pruebas y anotaciones (MUY IMPORTANTE)

### Clase de pruebas JUnit
- Es una clase Java independiente.
- Contiene métodos de prueba.
- No forma parte de la lógica de la aplicación.

### Anotaciones principales (con @)

- `@Test`
  - Marca un método como prueba unitaria.
- `@BeforeEach`
  - Se ejecuta **antes de cada prueba**.
  - Inicialización de datos comunes.
- `@AfterEach`
  - Se ejecuta **después de cada prueba**.
  - Limpieza de recursos.
- `@BeforeAll`
  - Se ejecuta **una sola vez antes de todas las pruebas**.
  - Preparación global.
- `@AfterAll`
  - Se ejecuta **una sola vez al finalizar todas las pruebas**.
  - Liberación global de recursos.

### Orden de ejecución
1. `@BeforeAll`
2. (`@BeforeEach` → `@Test` → `@AfterEach`) por cada prueba
3. `@AfterAll`

### Idea clave
- JUnit automatiza pruebas unitarias.
- Las anotaciones controlan **cuándo se ejecuta cada método**.
- Saber **qué se ejecuta antes y después** es preguntable en examen.

---

## Idea clave final para examen

- Tipos de pruebas → saber diferenciarlas.
- Integración / regresión / funcionales → muy importantes.
- JUnit → pruebas unitarias automáticas.
- Anotaciones `@Before`, `@After`, `@Test` → clave teórica y práctica.
- Pruebas de usuario, aceptación y versiones alfa/beta → bloque final del tema.
