# Tema 10 — Documentación de aplicaciones  


## Objetivo del tema
Identificar **herramientas de generación de ayuda** y **generar un sistema de ayuda con JavaHelp**, dominando **sus ficheros, estructura y uso**, y conocer **MkDocs a nivel práctico**.

---

## Índice
1. Apartado 3. Herramientas de generación de ayuda  
2. Apartado 7. Generación de un sistema de ayuda con JavaHelp  
   7.1. Qué es JavaHelp  
   7.2. Pasos para crear un sistema de ayuda con JavaHelp  
   7.3. Ficheros de JavaHelp (MUY IMPORTANTE)  
   7.4. Incorporación de la ayuda en una aplicación Java  
3. MkDocs — pasos prácticos

---

## 1. Apartado 3. Herramientas de generación de ayuda

Según los apuntes, las herramientas de generación de ayuda permiten **crear ficheros de ayuda digitales** para documentar aplicaciones.

### Herramientas vistas en el tema
- **Help Workshop**
  - Herramienta para crear ficheros de ayuda en Windows.
  - Incluye editor de imágenes, gestor de proyectos y compilador.
  - Permite reducir el tamaño final del fichero de ayuda.
- **Help Maker**
  - Herramienta gratuita.
  - Permite crear ficheros de ayuda mediante editor de texto.
  - Posibilita exportar toda la ayuda a un único PDF.
- **Shalom Help Maker**
  - Herramienta gratuita.
  - Permite crear índices, enlaces entre páginas y gráficos.
- **JavaHelp**
  - Sistema de ayuda para aplicaciones desarrolladas en Java.
  - Es el sistema que se desarrolla en profundidad en el tema.
  - Permite crear ayudas con:
    - Tabla de contenidos
    - Índice
    - Búsqueda
    - Ayuda sensible al contexto

👉 El profesor ha indicado que **JavaHelp es lo más importante del tema**.

---

## 2. Apartado 7. Generación de un sistema de ayuda con JavaHelp

### 2.1. Qué es JavaHelp
JavaHelp es una herramienta que permite crear **sistemas de ayuda integrables en aplicaciones Java**.

Permite:
- Ayuda genérica.
- Ayuda sensible al contexto.
- Navegación mediante índice y tabla de contenidos.

---

### 2.2. Pasos para crear un sistema de ayuda con JavaHelp

Según los apuntes, el proceso es **secuencial**:

1. Dar forma a la ayuda  
   - Especificar la organización.
   - Diseñar los temas.
2. Descargar e instalar JavaHelp.
3. Crear los ficheros JavaHelp necesarios según la organización.
4. Construir un fichero **JAR** con todos los ficheros.
5. Añadir la ayuda a la aplicación Java.

---

### 2.3. Ficheros de JavaHelp (PARTE CLAVE DE EXAMEN)

JavaHelp requiere varios ficheros, cada uno con una función concreta.

#### map_file.jhm (Map)
- Asocia cada **HTML de ayuda** con un **identificador**.
- Permite localizar cada tema de ayuda.

Función:
- Mapeo entre identificadores y páginas HTML.

---

#### toc.xml (Tabla de contenidos)
- Define la **estructura jerárquica** de la ayuda.
- Se organiza mediante `tocitem`.

Función:
- Mostrar el árbol de contenidos de la ayuda.

---

#### index.xml (Índice)
- Define el **índice alfabético** de la ayuda.
- Se organiza mediante `indexitem`.

Función:
- Acceso rápido a los temas por índice.

---

#### help_set.hs (HelpSet)
- Archivo **principal** del sistema de ayuda.
- Contiene:
  - Referencia al map.
  - Definición de vistas (índice, tabla de contenidos).
- Relaciona todos los ficheros anteriores.

👉 Es el fichero que se **carga desde Java**.

---

#### Ficheros HTML
- Contienen el **contenido real** de la ayuda.
- Se crea un fichero HTML por cada tema.
- Deben estar dentro del directorio `./help`.

---

#### Base de datos de búsqueda
- Se genera con la herramienta `jhindexer`.
- Permite el motor de búsqueda de JavaHelp.

---

### 2.4. Incorporación de la ayuda en una aplicación Java

Para usar JavaHelp en una aplicación Java:

- Se importan los paquetes:
  - `java.net.*`
  - `javax.help.*`

Clases principales:
- **HelpSet**
  - Localiza y carga el sistema de ayuda.
- **HelpBroker**
  - Permite mostrar la ayuda en la aplicación.

Funcionalidades:
- Asociar ayuda a:
  - Menús
  - Botones
  - Tecla F1
- Permitir ayuda sensible al contexto.

---

## 3. MkDocs — pasos prácticos

MkDocs es una herramienta para generar **documentación estática** a partir de Markdown.

### Pasos prácticos (según lo indicado en clase)

1. Instalar MkDocs (requiere Python).
2. Crear un proyecto MkDocs.
3. Escribir la documentación en archivos `.md`.
4. Configurar el archivo `mkdocs.yml`.
5. Previsualizar la documentación en local.
6. Generar el sitio web final de documentación.

Uso:
- Documentación técnica.
- Manuales y guías accesibles vía web.

---

## Idea clave para examen

- **JavaHelp**:
  - Es el sistema de ayuda más importante del tema.
  - Ficheros clave:
    - `map_file.jhm`
    - `toc.xml`
    - `index.xml`
    - `help_set.hs`
- **HelpSet** → archivo principal.
- **toc** → estructura.
- **index** → índice alfabético.
- **MkDocs** → documentación estática con Markdown.


## Anexo — Parte práctica (extraída de TUS prácticas del Tema 10)

> Este apartado **NO sustituye ni reescribe la teoría**.  
> Sirve únicamente para **entender mejor lo que se pide** a partir de lo que has hecho en las prácticas.

---

### 1. Estructura real del sistema de ayuda (JavaHelp)

En las prácticas se ha trabajado con la siguiente estructura:

- Carpeta `help/`
  - `helpset.hs` → núcleo del sistema de ayuda
  - `map.jhm` → asociación identificador ↔ HTML
  - `toc.xml` → tabla de contenidos jerárquica
  - `index.xml` → índice alfabético
- Carpeta `help/html/`
  - Archivos HTML de cada sección:
    - `introduccion.html`
    - `alta_socios.html`
    - `reservas.html`
    - `tipos_tarifas.html`
    - `administracion.html`
    - etc.

Esto refleja **cómo JavaHelp separa estructura (XML) de contenido (HTML)**.

---

### 2. HelpSet como núcleo del sistema

En la práctica, `helpset.hs`:
- Centraliza todo el sistema de ayuda.
- Declara:
  - El **mapa** (`map.jhm`)
  - La **tabla de contenidos** (`toc.xml`)
  - El **índice** (`index.xml`)
- Permite que todo se cargue desde un único punto en Java.

Es el archivo que se localiza y carga desde el código Java.

---

### 3. Tabla de contenidos jerárquica (toc.xml)

En `toc.xml`:
- Los temas están organizados de forma **anidada**, no plana.
- Se agrupan secciones como:
  - Manual de Usuario
    - Alta de Socios
    - Reservas
    - Tipos de Tarifa
  - Administración

Esto permite:
- Navegación clara.
- Escalabilidad del sistema de ayuda.
- Mejor experiencia de usuario.

---

### 4. Índice alfabético funcional (index.xml)

En `index.xml`:
- Se definen entradas alfabéticas (`indexitem`).
- Cada término apunta a un identificador del `map.jhm`.

Resultado práctico:
- El usuario puede buscar conceptos concretos (DNI, Edad, Tarifa, etc.)
- Accede directamente al HTML correspondiente.

---

### 5. Ayuda general desde menú

En la práctica:
- Se añade un menú **Ayuda → Ver ayuda**.
- Al pulsarlo:
  - Se abre el visor de JavaHelp.
  - Se carga el `helpset.hs`.
  - Se muestra la ayuda general (inicio).

Esto se implementa con:
- `enableHelpOnButton(...)`

---

### 6. Ayuda contextual con F1 (MUY IMPORTANTE)

En las prácticas se implementa **ayuda contextual real**:

- El usuario sitúa el foco en un componente (campo, botón, desplegable).
- Al pulsar **F1**, se abre la ayuda específica de ese elemento.

Ejemplos prácticos:
- Foco en **Tipo de Tarifa** → F1 abre ayuda de *Tipos de Tarifas*.
- Foco en botón **Resetear Sistema** → F1 muestra ayuda de advertencia.
- Foco en **Monitor personal** → F1 abre ayuda específica de monitores.

Esto se hace con:
- `enableHelpKey(...)`

---

### 7. Diferencia práctica entre enableHelpOnButton y enableHelpKey

Según las prácticas:

- **enableHelpOnButton**
  - La ayuda se abre al hacer clic.
  - El usuario decide explícitamente consultar ayuda.
  - Ejemplo: menú “Ayuda”.

- **enableHelpKey**
  - La ayuda se abre al pulsar F1.
  - Depende del componente que tenga el foco.
  - Es **ayuda contextual** y más precisa.

---

### 8. Ayuda contextual de granularidad fina

Las prácticas muestran:
- Ayuda asociada no solo a ventanas, sino a:
  - Campos concretos
  - Botones
  - Desplegables
- Cada componente tiene su propio identificador en `map.jhm`.

Esto demuestra:
- Uso correcto del **mapa de identificadores**.
- Coherencia entre:
  - `map.jhm`
  - `toc.xml`
  - `index.xml`
  - Código Java

---

### 9. Punto clave que refuerza el examen

Las prácticas dejan claro que:
- JavaHelp **no es solo mostrar un manual**.
- Lo importante es:
  - HelpSet bien estructurado
  - TOC jerárquico
  - Índice funcional
  - Ayuda contextual con F1
  - Uso correcto de `enableHelpKey`

Esto es exactamente **lo que el profesor suele recalcar y preguntar**.
