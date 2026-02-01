# TEMA 9: Organización de la información. Bases de datos  
**Sistemas de Gestión Empresarial**

## Objetivo del tema
Comprender cómo se organiza y gestiona la **información en los sistemas de gestión empresarial**, identificando el papel de las **bases de datos**, el uso de **PostgreSQL** como SGBD, la herramienta **PgAdmin** y su integración con **Odoo**, así como la estructura de **tablas, vistas, campos, relaciones** y las tareas básicas de **consulta, modificación y copias de seguridad**.

## Índice
1. La base de datos y PgAdmin  
2. La conexión en PgAdmin  
3. Tablas, vistas y campos de la base de datos  
4. Tablas, vistas y campos en Odoo  
5. Usos de PgAdmin: conexión Odoo y base de datos  
6. Usos de PgAdmin: modificación de valores  
7. Otras consideraciones con la base de datos  

---

## 1. La base de datos y PgAdmin
Odoo utiliza **PostgreSQL** como sistema gestor de bases de datos. PostgreSQL es un **SGBD objeto-relacional**, de código abierto, que emplea el lenguaje **SQL** para la gestión de la información.

En una instalación estándar de Odoo:
- PostgreSQL se instala y configura automáticamente.
- Cada base de datos de Odoo corresponde a una base de datos en PostgreSQL.
- El acceso directo a la base de datos permite tareas de análisis, mantenimiento y administración.

Para la gestión visual de PostgreSQL se utiliza **PgAdmin**, una herramienta gráfica que permite:
- Administrar servidores y bases de datos.
- Gestionar usuarios y roles.
- Consultar y modificar tablas y datos.
- Realizar copias de seguridad y restauraciones.

PgAdmin trabaja directamente sobre la base de datos utilizada por Odoo, por lo que cualquier cambio tiene impacto inmediato en la aplicación.

---

## 2. La conexión en PgAdmin
La conexión de PgAdmin a la base de datos de Odoo se basa en los parámetros definidos en el archivo de configuración **`odoo.conf`**.

Los parámetros principales son:
- **Host**: ubicación del servidor PostgreSQL.
- **Puerto**: puerto de conexión (habitualmente 5432).
- **Usuario**: usuario de base de datos.
- **Contraseña**: credencial asociada al usuario.
- **Nombre de la base de datos**: base de datos concreta de Odoo.

Al establecer la conexión:
- PgAdmin se conecta al mismo servidor PostgreSQL que usa Odoo.
- Se puede comprobar la estructura completa de la base de datos.
- Se confirma que ambos sistemas trabajan sobre la misma información.

---

## 3. Tablas, vistas y campos de la base de datos
La información de Odoo se almacena en **tablas** dentro de PostgreSQL.

Elementos principales:
- **Tablas**: estructuras que almacenan los registros del sistema.
- **Campos (columnas)**: atributos de cada tabla.
- **Registros (filas)**: instancias concretas de datos.
- **Vistas**: consultas almacenadas que presentan datos combinados o filtrados.

Desde PgAdmin es posible:
- Explorar el árbol de tablas y vistas.
- Consultar la definición de campos y tipos de datos.
- Analizar restricciones, índices y claves.
- Ver estadísticas de uso y tamaño de las tablas.

Esta información permite entender la organización interna de los datos empresariales.

---

## 4. Tablas, vistas y campos en Odoo
Para acceder a información técnica desde Odoo es necesario activar el **modo desarrollador**.

Una vez activado:
- Se muestran opciones técnicas adicionales.
- Es posible identificar:
  - El nombre real de las tablas en la base de datos.
  - El nombre técnico de los campos.
  - El tipo de dato asociado a cada campo.
- Se puede relacionar la interfaz gráfica con la estructura de PostgreSQL.

El modo desarrollador es fundamental para:
- Comprender cómo se almacenan los datos.
- Analizar problemas de información.
- Realizar tareas avanzadas de gestión y mantenimiento.

---

## 5. Usos de PgAdmin: conexión Odoo y base de datos
PgAdmin permite localizar y analizar información concreta utilizada por Odoo.

Usos habituales:
- Identificar la tabla asociada a un modelo de Odoo.
- Consultar registros concretos mediante su **id**.
- Ejecutar consultas SQL para obtener información específica.
- Ver en tiempo real cómo los datos consultados afectan a la aplicación.

Este uso facilita la comprensión del flujo de datos entre Odoo y la base de datos.

---

## 6. Usos de PgAdmin: modificación de valores
PgAdmin permite modificar directamente los valores almacenados en la base de datos.

Formas de modificación:
- Edición manual de registros desde la vista de tabla.
- Uso de sentencias SQL de actualización.

Aspectos importantes:
- Los cambios se reflejan inmediatamente en Odoo.
- Es una herramienta potente para tareas administrativas.
- Debe usarse con precaución para evitar inconsistencias.

La modificación directa es útil para mantenimiento, correcciones puntuales o análisis, pero no para el uso habitual.

---

## 7. Otras consideraciones con la base de datos

### Relaciones entre tablas
Odoo utiliza distintos tipos de relaciones:
- **many2one**
- **one2many**
- **many2many**

Estas relaciones se implementan mediante:
- Campos relacionales en Odoo.
- **Claves foráneas (foreign keys)** en PostgreSQL.

Las relaciones garantizan la **integridad referencial** de los datos.

### Copias de seguridad y restauración
La protección de la información se realiza mediante **copias de seguridad** y **restauraciones**.

Pueden realizarse:
- Desde la interfaz de gestión de bases de datos de Odoo.
- Mediante herramientas de PostgreSQL.
- De forma manual o automatizada.

Estas operaciones son esenciales para:
- Proteger la información empresarial.
- Recuperar el sistema ante fallos.
- Garantizar la continuidad del servicio.

# Glosario — Tema 9: Organización de la información. Bases de datos  
**Sistemas de Gestión Empresarial**

## Conceptos generales
- **Sistema de gestión empresarial (SGE)**: Aplicación que integra y centraliza la información de una empresa para gestionar procesos como ventas, contabilidad, inventario o recursos humanos.
- **Información empresarial**: Conjunto de datos estructurados que describen la actividad y el estado de una organización.
- **Persistencia de datos**: Capacidad de almacenar información de forma permanente para su posterior recuperación.

## Bases de datos
- **Base de datos**: Conjunto organizado de datos almacenados de forma estructurada y accesible electrónicamente.
- **Sistema gestor de bases de datos (SGBD)**: Software encargado de crear, gestionar y mantener bases de datos.
- **PostgreSQL**: SGBD objeto-relacional de código abierto utilizado por Odoo para almacenar la información.
- **SQL (Structured Query Language)**: Lenguaje estándar para definir, consultar y modificar bases de datos relacionales.

## PgAdmin
- **PgAdmin**: Herramienta gráfica de administración y desarrollo para PostgreSQL.
- **Servidor de base de datos**: Servicio que aloja el SGBD y gestiona las conexiones a las bases de datos.
- **Conexión a base de datos**: Proceso mediante el cual una aplicación o herramienta accede a una base de datos usando parámetros de red y autenticación.
- **Rol / Usuario**: Identidad definida en PostgreSQL que determina permisos de acceso y operaciones sobre la base de datos.

## Estructura de la base de datos
- **Tabla**: Estructura que almacena datos organizados en filas y columnas.
- **Campo (columna)**: Atributo de una tabla que define el tipo de información almacenada.
- **Registro (fila)**: Conjunto de valores que representan una entrada completa en una tabla.
- **Vista**: Consulta almacenada que presenta datos de una o varias tablas de forma estructurada.
- **Índice**: Estructura que mejora la velocidad de acceso a los datos.
- **Restricción (constraint)**: Regla que limita los valores permitidos en una tabla para garantizar la integridad.

## Odoo y base de datos
- **Odoo**: Sistema de gestión empresarial modular que utiliza PostgreSQL como base de datos.
- **Modo desarrollador**: Modo especial de Odoo que permite acceder a información técnica del sistema.
- **Modelo**: Representación lógica de una entidad de negocio en Odoo, asociada a una tabla de la base de datos.
- **Campo técnico**: Nombre interno del campo utilizado en la base de datos y en el código de Odoo.

## Relaciones entre tablas
- **Relación many2one**: Relación en la que varios registros se asocian a uno solo.
- **Relación one2many**: Relación en la que un registro se asocia a varios registros relacionados.
- **Relación many2many**: Relación en la que varios registros se asocian entre sí mediante una tabla intermedia.
- **Clave foránea (foreign key)**: Campo que establece una relación entre dos tablas y garantiza la integridad referencial.
- **Integridad referencial**: Propiedad que asegura la coherencia entre tablas relacionadas.

## Gestión y mantenimiento
- **Consulta de datos**: Operación que permite obtener información almacenada en la base de datos.
- **Modificación de datos**: Cambio directo de valores almacenados en la base de datos.
- **Copia de seguridad (backup)**: Duplicado de la base de datos para proteger la información.
- **Restauración**: Proceso de recuperación de una base de datos a partir de una copia de seguridad.
- **Mantenimiento de base de datos**: Conjunto de tareas destinadas a garantizar el correcto funcionamiento y la integridad de los datos.