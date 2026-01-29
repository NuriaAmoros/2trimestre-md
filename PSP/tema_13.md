# TEMA 13: La programación segura  
**Programación de Servicios y Procesos**

## Objetivo del tema
Comprender el concepto de **seguridad en los sistemas informáticos**, identificando las **amenazas, ataques y vulnerabilidades** más comunes, así como los **mecanismos básicos de protección** en aplicaciones software, con especial atención a la **validación de entradas de datos** como medida preventiva.

## Índice
1. Introducción a la seguridad  
2. Amenazas de seguridad  
3. Ataques a un sistema informático  
4. Vulnerabilidades en el software  
5. Mecanismos de control de acceso  
6. Validación de entradas  

---

## 1. Introducción a la seguridad
En informática, la **seguridad absoluta no existe**. Ningún sistema puede considerarse 100 % seguro debido a la aparición constante de nuevas amenazas y riesgos desconocidos.

Aun así, un sistema puede considerarse **seguro** si cumple las siguientes características fundamentales:

- **Confidencialidad**: solo las personas autorizadas pueden acceder a la información.
- **Integridad**: solo los usuarios autorizados pueden modificar los datos (lectura, escritura, modificación, creación y envío).
- **No repudio**: un usuario no puede negar haber realizado una acción, como el envío de un mensaje. Se apoya en mecanismos como certificados y firmas digitales.
- **Disponibilidad**: los recursos del sistema deben estar accesibles para los usuarios autorizados cuando los necesiten.

Para garantizar estas propiedades, las organizaciones deben disponer de una **política de seguridad**, que define responsabilidades, normas y procedimientos para prevenir incidentes.

---

## 2. Amenazas de seguridad
Una **amenaza de seguridad** es una condición del entorno que, al darse la oportunidad, puede provocar una violación de la seguridad del sistema.

Las amenazas pueden clasificarse según distintos criterios:

### Según su origen
- Se producen al conectar un sistema a cualquier entorno.
- No estar conectado a Internet no implica estar a salvo.
- La amenaza puede provenir de cualquier punto de la red.

### Según su efecto
- Robo de información.
- Anulación de sistemas.
- Suplantación de identidad.
- Robo de dinero.
- Venta de datos personales.
- Destrucción de información.
- Estafas.

### Según el medio utilizado
- Virus.
- Ingeniería social.
- Ataques de denegación de servicio.
- Phishing.

Además, las amenazas se agrupan en cuatro grandes categorías:

1. **Interrupción**: destruyen recursos del sistema, dejándolo inutilizable.
2. **Intercepción**: acceso no autorizado a recursos ajenos.
3. **Modificación**: alteración de información existente.
4. **Fabricación**: inserción de datos falsos que afectan a la autenticidad.

---

## 3. Ataques a un sistema informático
Un **ataque informático** o ciberataque es cualquier acción destinada a comprometer la seguridad de un sistema.

Se distinguen dos grandes tipos:

### Ataques pasivos
- El atacante no modifica la información.
- Se limita a escuchar o monitorizar el tráfico de red.
- Permite obtener credenciales, datos sensibles o información de uso.
- Ejemplo: sniffing de red.

### Ataques activos
- El atacante modifica, inserta o altera datos.
- Puede generar tráfico falso.
- Objetivos habituales:
  - Suplantación de identidad.
  - Repetición de mensajes (replay).
  - Denegación de servicio (DoS).

---

## 4. Vulnerabilidades en el software
Una **vulnerabilidad** es un fallo o debilidad en un sistema que puede ser explotado para acceder de forma no autorizada o realizar acciones indeseadas.

Características principales:
- Surgen desde la aparición de Internet.
- Son difíciles de detectar.
- Requieren auditorías especializadas.
- Deben revisarse antes y después de la puesta en producción.

En Java, la seguridad se apoya principalmente en dos pilares:

1. **Seguridad interna de la aplicación**  
   - Tratamiento de errores mediante bloques `try-catch-finally`.
   - Control de excepciones para evitar ejecuciones no deseadas.

2. **Políticas de acceso**  
   - Definen qué recursos del sistema puede utilizar una aplicación.
   - Limitan el acceso a funciones sensibles.

---

## 5. Mecanismos de control de acceso
Los **mecanismos de control de acceso** se basan en políticas de seguridad que establecen:

- Qué usuarios pueden acceder al sistema.
- Qué acciones pueden realizar.
- Qué recursos pueden utilizar.

Estas políticas:
- Deben estar documentadas.
- Han de ser conocidas por todo el personal.
- No son suficientes por sí solas y deben complementarse con procesos y controles técnicos.

---

## 6. Validación de entradas
La **validación de entradas** es una técnica fundamental para evitar fallos de seguridad provocados por datos introducidos por los usuarios.

Problemas comunes asociados a entradas no validadas:
- Inconsistencia de datos.
- **Desbordamientos de memoria (buffer overflow)**.
- Ejecución de comportamientos no deseados.

Para prevenir estos problemas se utilizan **expresiones regulares**, que permiten:
- Verificar el formato de los datos.
- Limitar la longitud de los campos.
- Asegurar que los valores cumplen requisitos predefinidos.

En Java, la validación se realiza mediante la biblioteca `java.util.regex`, que permite definir y aplicar patrones de comprobación sobre las entradas del usuario.

Este enfoque reduce significativamente el riesgo de ataques y errores en las aplicaciones.

# Glosario — Tema 13: La programación segura  
**Programación de Servicios y Procesos**

## Conceptos fundamentales de seguridad
- **Seguridad informática**: Conjunto de medidas técnicas y organizativas destinadas a proteger sistemas, aplicaciones y datos frente a accesos no autorizados, usos indebidos o daños.
- **Confidencialidad**: Propiedad que garantiza que la información solo sea accesible por usuarios o sistemas autorizados.
- **Integridad**: Propiedad que asegura que los datos no han sido alterados de forma no autorizada.
- **Disponibilidad**: Garantía de que los recursos del sistema están accesibles para los usuarios autorizados cuando los necesiten.
- **No repudio**: Mecanismo que impide que un usuario niegue haber realizado una acción, como el envío de un mensaje o una transacción.

## Amenazas y riesgos
- **Amenaza de seguridad**: Circunstancia o evento potencial que puede explotar una vulnerabilidad y causar un incidente de seguridad.
- **Riesgo**: Probabilidad de que una amenaza aproveche una vulnerabilidad y provoque un daño.
- **Ingeniería social**: Técnica de ataque basada en engañar a las personas para que revelen información sensible.
- **Phishing**: Tipo de ataque que suplanta la identidad de una entidad legítima para obtener credenciales o datos personales.
- **Denegación de servicio (DoS)**: Ataque que busca inutilizar un sistema o servicio saturándolo de peticiones.

## Tipos de amenazas según su efecto
- **Interrupción**: Amenaza que provoca la destrucción o inutilización de recursos del sistema.
- **Intercepción**: Acceso no autorizado a información o recursos ajenos.
- **Modificación**: Alteración no autorizada de datos existentes.
- **Fabricación**: Inserción de datos falsos en el sistema para comprometer su autenticidad.

## Ataques informáticos
- **Ataque informático**: Acción deliberada destinada a comprometer la seguridad de un sistema.
- **Ataque pasivo**: Ataque en el que el atacante observa o intercepta información sin modificarla.
- **Ataque activo**: Ataque en el que se modifican, insertan o eliminan datos del sistema.
- **Sniffing**: Técnica de ataque pasivo que consiste en capturar tráfico de red para obtener información.

## Vulnerabilidades
- **Vulnerabilidad**: Fallo o debilidad en un sistema o aplicación que puede ser explotado por un atacante.
- **Auditoría de seguridad**: Proceso de revisión y análisis de un sistema para detectar vulnerabilidades.
- **Política de seguridad**: Conjunto de normas y directrices que regulan el uso seguro de los recursos de una organización.

## Seguridad en Java
- **Control de excepciones**: Uso de mecanismos como `try-catch-finally` para gestionar errores y evitar comportamientos inseguros.
- **Políticas de acceso**: Restricciones que determinan qué recursos del sistema puede utilizar una aplicación.
- **Ejecución no deseada**: Comportamiento del programa provocado por entradas maliciosas o errores no controlados.

## Validación de entradas
- **Validación de datos**: Proceso de comprobación de los datos introducidos por el usuario antes de ser procesados.
- **Entrada no válida**: Dato que no cumple los requisitos de formato, tipo o longitud esperados.
- **Desbordamiento de memoria (Buffer overflow)**: Error que ocurre cuando se supera la capacidad asignada a un buffer.
- **Expresión regular**: Patrón utilizado para verificar y validar el formato de cadenas de texto.
- **java.util.regex**: Biblioteca de Java utilizada para trabajar con expresiones regulares y validar entradas.

## Control de acceso
- **Control de acceso**: Mecanismo que limita el uso de recursos a usuarios o procesos autorizados.
- **Autorización**: Proceso que determina qué acciones puede realizar un usuario una vez autenticado.
- **Autenticación**: Proceso de verificación de la identidad de un usuario o sistema.

# TEMA 13 — Código (Programación segura)

## Índice del bloque de código

1. Manejo seguro de excepciones en Java (`try-catch-finally`)  
2. Validación de entradas con expresiones regulares  
3. Control básico de errores para evitar ejecuciones no deseadas  
4. Ejemplo de validación de datos de usuario  
5. Relación código ↔ seguridad (interpretación para examen)

## 1. Manejo seguro de excepciones en Java (`try-catch-finally`)

El **manejo de excepciones** es un mecanismo básico de seguridad que permite **controlar errores** durante la ejecución de una aplicación y evitar comportamientos no deseados o fallos críticos del sistema.

### Estructura básica

```java
public class ControlExcepciones {

    public static void main(String[] args) {

        try {
            int resultado = 10 / 0;
            System.out.println(resultado);

        } catch (ArithmeticException e) {
            System.out.println("Error: división por cero");

        } finally {
            System.out.println("Bloque finally ejecutado");
        }
    }
}
```
## 2. Validación de entradas con expresiones regulares

La **validación de entradas** es una medida esencial de seguridad para evitar que datos mal formados o maliciosos provoquen fallos, inconsistencias o comportamientos no deseados en la aplicación.

En Java se realiza mediante la biblioteca **`java.util.regex`**, que permite comprobar si una cadena cumple un **patrón** determinado.

### Ejemplo básico de validación con expresión regular

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class ValidacionRegex {

    public static void main(String[] args) {

        String email = "usuario@email.com";

        String patronEmail = "^[A-Za-z0-9+_.-]+@[A-Za-z0-9.-]+$";

        Pattern pattern = Pattern.compile(patronEmail);
        Matcher matcher = pattern.matcher(email);

        if (matcher.matches()) {
            System.out.println("Email válido");
        } else {
            System.out.println("Email no válido");
        }
    }
}
```

## 3. Control básico de errores para evitar ejecuciones no deseadas

El **control de errores** permite impedir que una aplicación ejecute acciones no previstas cuando recibe datos incorrectos o se producen situaciones inesperadas.

Este tipo de control se basa en:
- Comprobaciones previas de los datos.
- Uso de condiciones lógicas.
- Lanzamiento controlado de excepciones.

### Ejemplo de control básico de errores

```java
public class ControlErrores {

    public static void main(String[] args) {

        int edad = -5;

        if (edad < 0 || edad > 120) {
            System.out.println("Edad no válida");
            return;
        }

        System.out.println("Edad válida: " + edad);
    }
}
```
## 4. Ejemplo de validación completa de datos de usuario

Este ejemplo combina **validación de entradas**, **control de errores** y **manejo de excepciones**, mostrando un enfoque básico de **programación segura** aplicado a datos introducidos por el usuario.

### Ejemplo integrado

```java
import java.util.regex.Pattern;

public class ValidacionUsuario {

    public static void main(String[] args) {

        String nombreUsuario = "user_01";
        String patronUsuario = "^[a-zA-Z0-9_]{3,15}$";

        if (!Pattern.matches(patronUsuario, nombreUsuario)) {
            System.out.println("Nombre de usuario no válido");
            return;
        }

        try {
            int edad = Integer.parseInt("25");

            if (edad < 0 || edad > 120) {
                throw new IllegalArgumentException("Edad fuera de rango");
            }

            System.out.println("Usuario válido");

        } catch (NumberFormatException e) {
            System.out.println("Edad no numérica");

        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

## 4. Ejemplo de validación completa de datos de usuario

Este ejemplo combina **validación de entradas**, **control de errores** y **manejo de excepciones**, mostrando un enfoque básico de **programación segura** aplicado a datos introducidos por el usuario.

### Ejemplo integrado

```java
import java.util.regex.Pattern;

public class ValidacionUsuario {

    public static void main(String[] args) {

        String nombreUsuario = "user_01";
        String patronUsuario = "^[a-zA-Z0-9_]{3,15}$";

        if (!Pattern.matches(patronUsuario, nombreUsuario)) {
            System.out.println("Nombre de usuario no válido");
            return;
        }

        try {
            int edad = Integer.parseInt("25");

            if (edad < 0 || edad > 120) {
                throw new IllegalArgumentException("Edad fuera de rango");
            }

            System.out.println("Usuario válido");

        } catch (NumberFormatException e) {
            System.out.println("Edad no numérica");

        } catch (IllegalArgumentException e) {
            System.out.println(e.getMessage());
        }
    }
}
```

