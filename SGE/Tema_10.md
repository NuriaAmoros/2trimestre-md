# TEMA 10: Adecuación de un sistema ERP-CRM a una empresa  
**Sistemas de Gestión Empresarial**

## Objetivo del tema
Comprender cómo **adaptar y personalizar un sistema ERP-CRM (Odoo)** a las necesidades concretas de una empresa, identificando los **procesos de actualización**, la **parametrización sin programación**, el uso de **Odoo Studio** y la **creación y modificación de módulos, vistas e informes**, sin intervención directa sobre el código.

## Índice
1. Actualización de Odoo  
2. Adaptación básica de Odoo a la empresa  
3. Modificación de módulos del sistema con Odoo Studio  
4. Personalización de informes con Odoo Studio  
5. Creación de módulos propios: creación y diseño  
6. Creación de módulos propios: gestión y vistas  
7. Creación de informes estadísticos  

---

## 1. Actualización de Odoo
La actualización de Odoo es un proceso recomendado para beneficiarse de:
- Nuevas funcionalidades.
- Correcciones de errores.
- Mejoras de seguridad.
- Mejor rendimiento del sistema.

En **Odoo Cloud**, las actualizaciones son automáticas.  
En instalaciones propias, la actualización debe realizarse manualmente y **no implica la actualización de la base de datos**, que es un proceso independiente y más complejo.

Antes de actualizar es imprescindible:
- Realizar una **copia de seguridad** de la base de datos.
- Verificar el método de instalación original.

Principales métodos de actualización:
- **Instalador**: se ejecuta el nuevo instalador sobre la versión existente.
- **Código fuente (GitHub)**: actualización mediante comandos de control de versiones.
- **Docker**: despliegue de una nueva versión conservando los datos necesarios.

La actualización finaliza reiniciando el servidor y el servicio de Odoo.

---

## 2. Adaptación básica de Odoo a la empresa
Odoo permite adaptarse a una empresa mediante **parametrización**, sin necesidad de programar.

Principales adaptaciones:
- **Plantillas de documentos** (facturas, presupuestos).
- **Datos de la empresa** (nombre, logo, información corporativa).
- **Plantillas de correos electrónicos** enviados automáticamente.

Estas modificaciones se realizan desde:
- Ajustes generales.
- Opciones de compañía.
- Menús técnicos relacionados con documentos y correos.

Este nivel de adaptación permite personalizar la imagen corporativa y los flujos básicos de comunicación.

---

## 3. Modificación de módulos del sistema con Odoo Studio
**Odoo Studio** es un módulo oficial que permite:
- Modificar módulos existentes.
- Crear nuevos módulos.
- Personalizar formularios, listas, kanban, gráficos e informes.
- Realizar automatizaciones básicas.

Características principales:
- No requiere programación.
- Utiliza un **editor visual de arrastrar y soltar**.
- Modifica internamente las vistas XML del sistema.
- Disponible únicamente en la **versión Enterprise**.

Al activarse, Odoo Studio añade un icono accesible desde todas las pantallas, desde el cual se pueden editar vistas, automatizaciones y aplicaciones completas.

---

## 4. Personalización de informes con Odoo Studio
Odoo Studio permite modificar **informes existentes** del sistema.

Las acciones habituales incluyen:
- Añadir nuevos campos.
- Cambiar estilos visuales.
- Ocultar o mostrar información bajo condiciones.
- Eliminar elementos por defecto.

La personalización se realiza:
- Accediendo al módulo correspondiente.
- Abriendo Odoo Studio.
- Seleccionando la opción de edición de informes.
- Ajustando los campos y sus condiciones de visibilidad.

Este proceso permite adaptar los informes a las necesidades reales de la empresa sin tocar código.

---

## 5. Creación de módulos propios: creación y diseño
Odoo Studio permite crear **módulos completamente nuevos**, adaptados a una actividad empresarial concreta.

Proceso general:
- Acceder al gestor de aplicaciones.
- Abrir Odoo Studio.
- Crear un nuevo módulo.
- Definir:
  - Nombre del módulo.
  - Icono.
  - Primer objeto de negocio.

Al crear el módulo:
- Odoo genera automáticamente las tablas necesarias en la base de datos.
- Las tablas personalizadas se identifican con el prefijo `x_`.

El diseño del formulario se realiza añadiendo campos como:
- Texto.
- Imagen.
- Campos monetarios.
- Campos numéricos.

---

## 6. Creación de módulos propios: gestión y vistas
Una vez creado el módulo, se pueden gestionar:
- **Estados del proceso** mediante una barra de estado.
- **Vistas de lista**, mejorando la visualización de datos.
- **Vistas kanban**, para una representación visual por estados.

Estas vistas permiten:
- Controlar el flujo de trabajo.
- Visualizar rápidamente la situación de los registros.
- Facilitar la gestión operativa diaria.

Todo se realiza desde Odoo Studio, sin programación, mediante configuración visual.

---

## 7. Creación de informes estadísticos
Odoo Studio permite crear **informes estadísticos gráficos** a partir de los datos del sistema.

Características:
- Uso de vistas gráficas.
- Posibilidad de aplicar filtros.
- Agrupación de datos por criterios.
- Visualización clara de información relevante.

Además, es posible:
- Crear informes personalizados.
- Diseñar plantillas de informes.
- Seleccionar los campos que se desean mostrar.

Estos informes facilitan el análisis de la información empresarial y la toma de decisiones.

---

## Idea clave para examen
- La adaptación de Odoo puede realizarse **sin programar**, mediante parametrización y Odoo Studio.
- Odoo Studio permite modificar y crear módulos, vistas e informes.
- La actualización de Odoo **no implica actualizar la base de datos**.
- La flexibilidad del ERP es una de sus principales ventajas competitivas.
- El objetivo es **ajustar el sistema a la empresa**, no la empresa al sistema.

