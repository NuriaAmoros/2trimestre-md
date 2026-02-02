# Tema 11 — Distribución de aplicaciones (ENFOQUE PRÁCTICO REAL)

## Objetivo del tema
Comprender **cómo distribuir una aplicación Java de forma profesional**, centrándose en:
- Generación de **JAR**
- Conversión a **EXE**
- Creación de **instaladores**
- **Firma digital**
Todo **tal y como se ha hecho en clase y en tus prácticas**, evitando teoría innecesaria.

---

## Índice
1. Paquetes en Linux (Apartado 3)
2. Generación de un JAR ejecutable
3. Conversión de JAR a EXE (Launch4j)
4. Creación de instalador EXE (Inno Setup)
5. Interacción con el usuario en el instalador
6. Firma digital de ficheros JAR
7. Ideas clave tipo examen / test

---

## 1. Paquetes en Linux (Apartado 3)

En Linux, las aplicaciones se distribuyen mediante **paquetes**, no instaladores gráficos como en Windows.

Formatos principales:
- **DEB** → Distribuciones basadas en Debian (Ubuntu)
- **RPM** → RedHat
- **TAR / TGZ** → Paquetes comprimidos

Herramienta usada:
- `checkinstall`

Flujo práctico:
- Se empaqueta la aplicación
- Se genera un `.deb`
- El usuario instala con `dpkg`

Esto **entra como concepto**, no como práctica profunda.

---

## 2. Generación de un JAR ejecutable

El **JAR** es el formato base de distribución en Java.

### Pasos prácticos (Eclipse)
1. Botón derecho sobre el proyecto
2. `Export`
3. `Java → JAR File`
4. Seleccionar todos los recursos del proyecto
5. Indicar la **Main Class**
6. Generar el `.jar`

Aspectos clave:
- Los recursos deben estar en `res`
- El JAR contiene **código + recursos**
- Sin JAR **no hay EXE ni instalador**

---

## 3. Conversión de JAR a EXE — Launch4j (muy importante)

Launch4j permite convertir un `.jar` en un **.exe nativo de Windows**.

### Qué se configura en Launch4j
- `Output file` → nombre del `.exe`
- `Jar` → ruta del `.jar`
- `Icon` → icono `.ico`
- `Header` → **GUI**
- `JRE` → versión mínima de Java
- `Splash` → imagen inicial (opcional)

Resultado:
- Ejecutable nativo
- No se abre consola
- Icono propio
- Mejora experiencia de usuario

Esto **sale seguro en examen práctico**.

---

## 4. Creación de instalador EXE — Inno Setup (clave del tema)

Inno Setup permite crear un **instalador profesional**.

### Elementos configurados en el script
- Nombre de la app
- Versión
- Editor
- Carpeta destino (`Program Files`)
- Ejecutable principal
- Archivos incluidos (exe, jar, libs, docs)

### Elementos visuales importantes
- **Imagen lateral (banner)**
- **Icono del instalador**
- **Pantalla final personalizada**

---

## 5. Interacción con el usuario (MUY preguntable)

Durante la instalación se incluyen:

- Selección de idioma
- Aceptación de **licencia / EULA**
- Elección de tareas adicionales:
  - Crear acceso directo
- Pantalla final:
  - Ejecutar aplicación
  - Abrir manual de usuario

Elementos destacados de tus prácticas:
- Idiomas: español, inglés, catalán
- Licencia cargada desde archivo `.txt`
- Apertura automática de manual tras instalación

---

## 6. Firma digital de ficheros JAR (Apartado 9)

La firma digital garantiza:
- **Autenticidad**
- **Integridad**
- Confianza del usuario

### Herramienta usada
- `jarsigner`

### Conceptos clave
- **Keystore** → almacén de claves
- **Alias** → identificador de la clave
- Clave pública / privada

### Flujo real
1. Crear keystore
2. Firmar JAR
3. Verificar firma (`jarsigner -verify`)

Resultado:
- El JAR firmado no puede modificarse
- Si se altera → la firma deja de ser válida

Esto **entra mucho en tipo test**.

---

## 7. Ideas clave para examen

- JAR → empaqueta aplicación Java
- Launch4j → convierte JAR en EXE
- Inno Setup → crea instalador completo
- Instalador:
  - Idiomas
  - Licencia
  - Rutas
  - Accesos directos
- Firma digital:
  - Garantiza autenticidad
  - Detecta modificaciones
- EXE es preferible a JAR para usuario final

---

## Resumen mental rápido
- **JAR** → base
- **Launch4j** → EXE
- **Inno Setup** → instalador
- **JarSigner** → seguridad

## 8. Apartados 10 y 11 — Proceso del instalador (según el profesor)

Los **apartados 10 y 11** del tema se corresponden **exclusivamente con el proceso del instalador**, tal y como se ha trabajado en las prácticas y señalado en clase.

Incluyen el **flujo completo de instalación**, desde que el usuario ejecuta el instalador hasta la finalización.

### Proceso del instalador (pasos)

1. **Pantalla inicial**
   - Inicio del asistente de instalación.
   - Información básica de la aplicación.

2. **Selección de idioma**
   - El usuario elige el idioma del instalador.
   - Determina el idioma de todas las pantallas posteriores.

3. **Licencia / EULA**
   - Mostrar condiciones y términos de uso.
   - Obligatorio aceptar la licencia para continuar.

4. **Selección de carpeta de instalación**
   - Ruta por defecto (normalmente `Program Files`).
   - Posibilidad de cambiarla.

5. **Selección de tareas adicionales**
   - Crear acceso directo en el escritorio.
   - Otras opciones configurables.

6. **Proceso de instalación**
   - Copia de archivos:
     - `.exe`
     - recursos
     - librerías necesarias
   - Configuración interna del sistema.

7. **Pantalla final**
   - Mensaje de instalación completada.
   - Opción de:
     - Ejecutar la aplicación
     - Cerrar el instalador

### Idea clave de examen
- Los **puntos 10 y 11** **NO añaden herramientas nuevas**.  
- Evalúan que se entienda **el flujo completo del instalador**, sus pantallas y su función.
- Totalmente ligado a **Inno Setup** y a la experiencia de usuario.



Incluyen el **flujo completo de instalación**, desde que el usuario ejecuta el instalador hasta la finalización.


### Idea clave de examen
- Los **puntos 10 y 11** **NO añaden herramientas nuevas**.  
- Evalúan que se entienda **el flujo completo del instalador**, sus pantallas y su función.
- Totalmente ligado a **Inno Setup** y a la experiencia de usuario.
