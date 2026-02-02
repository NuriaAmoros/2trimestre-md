# Tema 9 — Confección de informes II (Extracto según guía)

## Objetivo del tema
Extraer **exclusivamente** el contenido del **Tema 9** que **exige la guía de estudio**, sin añadir apartados adicionales ni casos prácticos no solicitados.

## Índice
1. Apartado 3. Estilos (según guía)

---

## 1. Apartado 3. Estilos

> En la guía de estudio, del **Tema 09** se solicita **únicamente el Apartado 3 (Estilos)**.

En el material oficial del Tema 9, este contenido se corresponde con los **elementos de presentación visual y formato aplicados a los datos del informe**, concretamente durante la **inclusión y representación de datos desde base de datos**, diferenciando elementos estáticos y dinámicos y su colocación correcta en el informe.

### Elementos de estilo en informes

En el diseño de informes con iReport/JasperReports es necesario distinguir entre:

- **Static Text**
  - Elementos de texto estático.
  - Se utilizan como etiquetas, títulos o encabezados.
  - No dependen del origen de datos.
  - Se emplean habitualmente para:
    - Títulos del informe.
    - Nombres de columnas.
    - Textos descriptivos.

- **Text Field**
  - Elementos de texto dinámico.
  - Muestran datos procedentes de la base de datos.
  - Se vinculan a campos obtenidos en la consulta SQL.
  - Permiten aplicar formato visual a los datos mostrados.

### Colocación de elementos y estilo visual

- Los **Text Field** colocados en **Column Header** solo muestran el primer registro.
- Para que se muestren **todos los registros**, los campos deben colocarse en la sección **Details**.
- Al colocar un campo dinámico:
  - Se selecciona el `Text Field`.
  - Se asocia al campo correspondiente mediante el menú **Field**.
  - El editor de expresiones genera automáticamente la referencia al campo.

### Aplicación de estilos

Los elementos del informe permiten modificar sus propiedades visuales desde la **zona de propiedades**, entre ellas:
- Tipo y tamaño de fuente.
- Alineación del texto.
- Bordes y separación.
- Formato numérico aplicado a los datos.

Estas propiedades permiten adaptar la presentación del informe sin modificar el origen de los datos, separando **contenido** y **estilo visual**.

---

### Confirmación de alcance
✔ Incluido solo el **contenido del Apartado 3 solicitado por la guía**  
✘ No se incluyen consultas, subinformes, parámetros, imágenes, gráficos ni casos prácticos  

Si quieres, el siguiente paso puede ser:
- convertir esto en **resumen de memorización**, o  
- redactarlo en **formato respuesta de examen**, o  
- continuar directamente con **Tema 10** siguiendo el mismo criterio estricto.


## Parte práctica completa 


## Índice
1. Informes parametrizados  
2. Uso de parámetros ($P{})  
3. Campos y variables ($F{}, $V{})  
4. Imágenes condicionales  
5. Gráficos estadísticos (Pie Chart)  
6. Subinformes (Master–Detail)  
7. Estilos básicos  
8. Estilos condicionales  
9. Problemas reales y soluciones aplicadas  

---

## 1. Informes parametrizados

Has creado informes que **reciben valores externos** para filtrar datos sin modificar el diseño.

Ejemplo práctico:
- Informe de préstamos filtrado por fechas.
- El usuario introduce los valores al ejecutar el informe.

Ventaja:
- El mismo informe sirve para distintos periodos.

---

## 2. Uso de parámetros ($P{})

### Parámetros creados
- `FechaInicio` → java.sql.Date  
- `FechaFin` → java.sql.Date  
- `ID_LIBRO_PARAM` → Integer  
- `CiudadFiltro`  
- `FechaDesde`  
- `FechaHasta`

### Uso real
- En consultas SQL:
  ```sql
  WHERE fecha BETWEEN $P{FechaInicio} AND $P{FechaFin}
## 3. Campos y variables ($F{}, $V{})

### $F{} — Fields
- Representan **columnas de la base de datos**.
- Ejemplos usados:
  - `$F{titulo}`
  - `$F{nombre}`
  - `$F{fecha_prestamo}`
  - `$F{dias_prestamo}`
  - `$F{fecha_devolucion}`
- Se colocan principalmente en la banda **Detail** para que se repitan por registro.

### $V{} — Variables
- Usadas para **cálculos y resúmenes**.
- Variables creadas:
  - `V_CORTOS` → préstamos ≤ 15 días
  - `V_LARGOS` → préstamos > 15 días
- Uso real:
  - Mostrar resultados al final del informe.
  - Evitar errores de **claves duplicadas** en gráficos.

---

## 4. Imágenes condicionales

- Uso de **imágenes que solo se muestran si se cumple una condición**.

### Caso práctico
- Icono de alerta para préstamos largos.

### Condición aplicada
- `Print When Expression = $F{dias_prestamo} > 15`

### Resultado
- El icono solo aparece en registros con **préstamos largos**.

---

## 5. Gráficos estadísticos (Pie Chart)

### Tipo de gráfico
- **Pie Chart**

### Ubicación
- Banda **Summary**

### Configuración real
- No se usaron claves dinámicas por **errores de duplicidad**.
- Se usaron variables calculadas:
  - `V_CORTOS`
  - `V_LARGOS`
- Cada porción del gráfico representa una **variable**.

### Conclusión práctica
- JasperReports es más complejo que Excel para gráficos.
- Requiere control manual de **variables** y **datasets**.

---

## 6. Subinformes (Master–Detail)

### Subinforme
- Archivo: `Subinforme_Historial_Libro.jrxml`
- Bandas usadas: **solo Detail**
- Parámetro:
  - `ID_LIBRO_PARAM`
- Consulta filtrada:
  - `WHERE p.id_libro = $P{ID_LIBRO_PARAM}`

### Informe maestro
- Archivo: `Informe_Maestro_Libros.jrxml`
- Consulta principal:
  - `SELECT id_libro, titulo, autor, categoria FROM libros ORDER BY titulo`

### Enlace maestro–subinforme
- Parámetro:
  - Name: `ID_LIBRO_PARAM`
  - Expression: `$F{id_libro}`

### Conexión
- Opción activada:
  - **Use same connection used to fill the report**

### Resultado
- Cada libro muestra su **historial de préstamos** correctamente.

---

## 7. Estilos básicos

- Aplicados directamente desde **Properties**, sin tocar SQL.

### Elementos estilizados
- Static Text
- Text Field
- Campos dinámicos (`$F{}`, `$V{}`, `$P{}`)

### Propiedades usadas
- Font Name
- Font Size
- Bold
- Forecolor
- Backcolor
- Horizontal Alignment
- Pattern (formato numérico)

### Uso real
- Encabezados diferenciados.
- Totales resaltados.
- Datos alineados correctamente.

---

## 8. Estilos condicionales (clave del tema)

### Estilo creado
- Nombre: `EstiloDevolucion`

### Condición aplicada
- `$F{fecha_devolucion} == null`

### Formato aplicado
- Color rojo
- Negrita

### Campo afectado
- `fecha_devolucion` (Text Field del subinforme)

### Detalle importante
- Fue necesario **eliminar el atributo `forecolor` del XML**
  para que el estilo condicional tuviera efecto.

### Resultado
- Fechas de devolución nulas se muestran en **rojo**.
- Facilita la identificación visual de **préstamos pendientes**.

---

## 9. Problemas reales y soluciones

### Problema
- El subinforme no mostraba datos dentro del informe maestro.

### Solución
- Pasar correctamente el parámetro:
  - `$F{id_libro}`
- Usar la misma conexión.
- Compilar el subinforme (`.jasper`).

---

### Problema
- Gráfico con errores de **claves duplicadas**.

### Solución
- Uso de **variables calculadas** en lugar de claves dinámicas.

---

### Problema
- Los estilos condicionales no se aplicaban.

### Solución
- Eliminar estilos inline (`forecolor`) del XML.

---

## Idea clave para examen / práctica
- `$P{}` → filtra y personaliza informes  
- `$F{}` → muestra datos  
- `$V{}` → calcula resultados  
- **Estilos** → cambian apariencia  
- **Estilos condicionales** → resaltan información clave  
- **Subinformes** → relación Master–Detail real
