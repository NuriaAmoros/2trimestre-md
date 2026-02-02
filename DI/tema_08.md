# Tema 8 — Confección de informes I (Extracto según guía)

## Objetivo del tema
Identificar y comprender **únicamente** los contenidos del Tema 8 que exige la guía de estudio para la evaluación: herramientas gráficas integradas en el IDE, estructura general de un informe y uso de variables y valores calculados.

## Índice
1. Herramientas gráficas integradas en el IDE  
2. Estructura general y secciones de un informe  
3. Variables y valores calculados en un informe  

---

## 1. Herramientas gráficas integradas en el IDE

Las herramientas gráficas de creación de informes permiten diseñar informes de forma visual, integradas directamente en el entorno de desarrollo.

### Herramientas principales
- **iReport + JasperReports**  
  - Solución más utilizada en entornos Java (Eclipse, NetBeans).  
  - **JasperReports** se encarga del motor y la generación del informe.  
  - **iReport** proporciona la interfaz gráfica para el diseño visual del informe.
- **Eclipse BIRT**  
  - Herramienta open source orientada a inteligencia empresarial.  
  - Uso habitual en aplicaciones Java de escritorio y web.
- **Crystal Reports**  
  - Herramienta de inteligencia empresarial, principalmente en entornos Microsoft Visual Studio.

### iReport + JasperReports en Eclipse
- Se instala como **plugin desde Eclipse Marketplace**.
- Una vez instalado, se accede desde la perspectiva de informes.
- Permite:
  - Crear informes a partir de plantillas o en blanco.
  - Definir orígenes de datos (bases de datos, CSV, XML, hojas de cálculo).
  - Diseñar visualmente el informe y generar automáticamente el código asociado.

### Estructura de la herramienta iReport
La interfaz se divide en:
- Explorador de informes (proyectos, ficheros `.jrxml`, conexiones a datos).
- Zona de diseño (lienzo del informe).
- Paleta de elementos (componentes visuales).
- Zona de propiedades (configuración de cada elemento).
- Zona de errores (errores de compilación del informe).

---

## 2. Estructura general y secciones de un informe

Un informe se organiza en **bandas o secciones**, cada una con una función concreta dentro del documento generado.

### Secciones principales
- **Title**  
  Contiene el título del informe. Debe ser claro y representativo del contenido.
- **Page Header**  
  Aparece en la parte superior de cada página. Suele incluir datos generales como la fecha.
- **Column Header**  
  Define los encabezados de las columnas cuando el informe se organiza en formato tabular.
- **Details**  
  Sección central del informe. Contiene los datos detallados obtenidos del origen de datos.
- **Column Footer**  
  Muestra información relacionada con cada columna, como subtotales.
- **Page Footer**  
  Parte inferior de la página. Suele incluir numeración de páginas u otra información general.
- **Summary**  
  Sección final del informe. Incluye valores calculados, totales y recuentos globales.  
  Si los valores calculados no se colocan en esta sección, no se mostrarán.

---

## 3. Variables y valores calculados en un informe

Las variables permiten realizar cálculos y mostrar resultados derivados de los datos del informe.

### Tipos de variables
- **Variables de usuario**  
  - Definidas por el desarrollador.
  - Normalmente vinculadas a campos del origen de datos.
- **Variables predefinidas**  
  Incluidas por defecto en la herramienta:
  - `PAGE_NUMBER`: número de página del informe.
  - `COLUMN_NUMBER`: número de columnas.
  - `REPORT_COUNT`: número total de registros de la consulta.
  - `PAGE_COUNT`: número de registros mostrados en cada página.

### Valores calculados habituales
- **Numeración de líneas**  
  - Se utiliza para numerar registros.
  - Requiere una variable que incremente su valor.
- **Recuentos y totales**  
  - Operaciones sobre columnas numéricas.
  - Ejemplo: suma de todos los valores de una columna.

### Uso de variables en el informe
- Los campos se colocan en la sección **Details** para mostrar los datos.
- Al añadir variables en Details, se generan automáticamente etiquetas en **Column Header**.
- Los resultados de operaciones y cálculos deben colocarse en la sección **Summary**.
- Las operaciones se configuran desde el editor de expresiones de cada variable.

---



## 4. Apartados (secciones) de un informe

Un informe en JasperReports se organiza en **bandas**. Cada banda tiene una función concreta y fija.

- **Title**  
  Muestra el título del informe. Aparece una sola vez, al inicio.

- **Page Header**  
  Encabezado de página. Aparece en todas las páginas.  
  Ejemplos: fecha, nombre del informe.

- **Column Header**  
  Encabezado de columnas.  
  Se colocan aquí las etiquetas de los campos (nombres de columnas).

- **Detail**  
  Sección principal del informe.  
  Aquí se colocan los campos dinámicos para que se repitan por cada registro.

- **Column Footer**  
  Pie de columna.  
  Se usa para mostrar operaciones asociadas a una columna (subtotales).

- **Page Footer**  
  Pie de página.  
  Suele contener el número de página u otros datos generales.

- **Summary**  
  Sección final del informe.  
  Aquí se colocan **totales, recuentos y valores calculados globales**.  
  Si un cálculo no se coloca en Summary, **no se muestra**.

---

## 2. Tipos de variables en JasperReports

En JasperReports se trabaja con **campos, variables y parámetros**, cada uno con una finalidad distinta.

### Tipos conceptuales
- **Campos**: datos que vienen directamente de la base de datos.
- **Variables**: valores calculados durante la ejecución del informe.
- **Parámetros**: valores externos que se pasan al informe.

---

## 3. Notación $F{}, $V{} y $P{}

### $F{ } — Fields (Campos)
- Representan **columnas de la consulta SQL**.
- Obtienen su valor directamente del origen de datos.
- Se colocan normalmente en la sección **Detail**.

Ejemplo conceptual:
- Nombre de producto
- Precio
- Fecha

Uso típico:
- Mostrar datos fila a fila.

---

### $V{ } — Variables
- Representan **valores calculados**.
- Pueden ser:
  - **Predefinidas** (ya existen en JasperReports).
  - **Definidas por el usuario**.
- Se usan para:
  - Sumas
  - Contadores
  - Numeración de líneas
  - Totales

Variables predefinidas habituales:
- `PAGE_NUMBER` → número de página.
- `REPORT_COUNT` → número total de registros.
- `PAGE_COUNT` → registros por página.
- `COLUMN_NUMBER` → número de columna.

Uso típico:
- Colocar en **Column Footer** o **Summary**.

---

### $P{ } — Parameters (Parámetros)
- Valores **externos al informe**.
- No vienen de la base de datos directamente.
- Permiten:
  - Filtrar datos
  - Personalizar el informe
  - Reutilizar el mismo diseño con distintos valores

Ejemplos conceptuales:
- Fecha inicial / fecha final
- Id de cliente
- Nombre de la conexión

Uso típico:
- En consultas SQL (WHERE).
- En textos del informe.

---

## Relación clara para examen

- **$F{}** → dato de la base de datos  
- **$V{}** → dato calculado  
- **$P{}** → dato externo / de entrada  


Si quieres, en el siguiente mensaje puedo:
- convertir esto en **respuesta tipo examen**, o  
- hacer un **esquema ultra-memorizable**, o  
- cruzarlo con **preguntas tipo test reales**.
