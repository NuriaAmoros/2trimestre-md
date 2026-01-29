# TEMA 12: El servicio web  
**Programación de Servicios y Procesos**

## Objetivo del tema
Comprender qué es un **servicio web**, los **estándares y especificaciones** que lo definen, la **arquitectura orientada a servicios (SOA)** y el proceso general de **creación y consumo de servicios web SOAP** utilizando Java, desde un enfoque conceptual y estructural.

## Índice
1. ¿Qué es un servicio web?  
2. Estándares y especificaciones web  
3. Arquitectura orientada a servicios (SOA)  
4. Servicios web SOAP  
5. Creación y consumo de servicios web SOAP en Java  

---

## 1. ¿Qué es un servicio web?
Un **servicio web** es un programa accesible a través de la red que permite la **comunicación entre aplicaciones** que pueden estar desarrolladas en distintos lenguajes y ejecutarse en diferentes plataformas.

Características fundamentales:
- Accesibles a través de la **web**.
- Utilizan protocolos estándar, principalmente **HTTP**.
- Emplean **XML** como formato de intercambio de datos.
- Ofrecen funcionalidades **bien definidas**.
- Incluyen una **descripción del servicio**, que permite conocer qué hace y cómo usarlo.
- Son **localizables**, es decir, pueden encontrarse mediante mecanismos de descubrimiento.
- Son **independientes y reutilizables**.
- Garantizan la **interoperabilidad** entre sistemas heterogéneos.

El uso de estándares abiertos permite que un cliente pueda consumir un servicio web sin conocer su implementación interna.

---

## 2. Estándares y especificaciones web
Los servicios web se basan en estándares definidos por organismos internacionales que garantizan la interoperabilidad y la compatibilidad entre sistemas.

Organizaciones principales:
- **W3C (World Wide Web Consortium)**  
  Define estándares fundamentales de la web como HTTP, XML, SOAP y otros protocolos relacionados con los servicios web.
- **OASIS**  
  Promueve estándares abiertos relacionados con servicios web, arquitectura SOA, seguridad, calidad del servicio y cloud computing.
- **JCP (Java Community Process)**  
  Define especificaciones Java mediante las **JSR (Java Specification Request)**, entre ellas:
  - JAX-RS (servicios REST).
  - JAX-WS (servicios web SOAP).
  - Especificaciones Java EE.

Estos estándares aseguran que los servicios web puedan ser implementados y consumidos de forma consistente.

---

## 3. Arquitectura orientada a servicios (SOA)
La **arquitectura orientada a servicios (SOA)** es un modelo de diseño en el que las aplicaciones se construyen a partir de **servicios independientes** que se comunican entre sí.

Principios básicos:
- Servicios **reutilizables**.
- Servicios **independientes del lenguaje**.
- Comunicación mediante protocolos estándar.
- Separación entre proveedor del servicio y consumidor.

Tipos de arquitecturas SOA:
1. **SOA tradicional**  
   - Utiliza SOAP como protocolo de comunicación.
   - Emplea WSDL para describir los servicios.
   - Puede usar UDDI para su publicación.
   - Carece de características avanzadas como seguridad o transacciones.
2. **SOA de segunda generación**  
   - Incorpora estándares WS para mejorar la calidad del servicio.
   - Añade seguridad, gestión de transacciones y control del servicio.

SOA es el **modelo arquitectónico**, mientras que **SOAP** es uno de los protocolos de comunicación utilizados dentro de SOA.

---

## 4. Servicios web SOAP
SOAP (Simple Object Access Protocol) es un protocolo basado en **XML** que define cómo se intercambian mensajes entre un cliente y un servicio web.

Características de SOAP:
- Independiente de la plataforma y del lenguaje.
- Basado en mensajes XML.
- Funciona sobre protocolos como HTTP.
- Define una estructura estricta de mensajes.
- Facilita la interoperabilidad en entornos empresariales.

Un servicio SOAP describe sus operaciones y parámetros mediante **WSDL**, permitiendo que los clientes conozcan cómo interactuar con él.

---

## 5. Creación y consumo de servicios web SOAP en Java
El proceso general para trabajar con servicios web SOAP en Java incluye:
- Creación de un **proyecto web** en Java.
- Definición de un **servicio web SOAP** con métodos públicos.
- Publicación del servicio en un **servidor de aplicaciones**.
- Generación de un **cliente** que consuma el servicio.
- Comunicación cliente–servicio mediante mensajes SOAP.

Desde el punto de vista del temario, lo importante es:
- Comprender el **flujo cliente/servidor**.
- Saber distinguir entre **servicio** y **cliente**.
- Identificar el papel de SOAP y XML en la comunicación.
- Entender que el cliente consume el servicio sin conocer su implementación interna.

El enfoque del tema es **conceptual y estructural**, no la memorización de implementaciones completas.

# Glosario — Tema 12: El servicio web  
**Programación de Servicios y Procesos**

## Términos generales
- **Servicio web**: Programa accesible a través de la red que permite la comunicación entre aplicaciones heterogéneas mediante estándares abiertos.
- **Interoperabilidad**: Capacidad de distintos sistemas, lenguajes y plataformas para comunicarse y trabajar conjuntamente.
- **Plataforma**: Entorno tecnológico (hardware, sistema operativo, middleware) donde se ejecuta una aplicación.
- **Cliente**: Aplicación que consume un servicio web solicitando sus operaciones.
- **Proveedor del servicio**: Aplicación que ofrece un servicio web y atiende las peticiones de los clientes.

## Estándares y organismos
- **Estándares abiertos**: Especificaciones públicas que garantizan compatibilidad y reutilización entre sistemas.
- **W3C (World Wide Web Consortium)**: Organismo que define estándares fundamentales de la web como XML, SOAP y HTTP.
- **OASIS**: Organización que promueve estándares abiertos relacionados con servicios web, SOA y seguridad.
- **JCP (Java Community Process)**: Proceso encargado de definir las especificaciones oficiales del lenguaje y la plataforma Java.
- **JSR (Java Specification Request)**: Documento que describe una especificación Java concreta.

## Arquitectura SOA
- **SOA (Service-Oriented Architecture)**: Arquitectura basada en servicios independientes que se comunican mediante protocolos estándar.
- **Servicio reutilizable**: Servicio diseñado para ser usado por múltiples aplicaciones sin modificaciones.
- **Desacoplamiento**: Principio por el cual cliente y servicio son independientes entre sí.
- **SOA tradicional**: Arquitectura SOA basada principalmente en SOAP y WSDL, sin características avanzadas.
- **SOA de segunda generación**: Evolución de SOA que incorpora estándares adicionales para seguridad, transacciones y calidad del servicio.

## Servicios web SOAP
- **SOAP (Simple Object Access Protocol)**: Protocolo basado en XML que define la estructura de los mensajes intercambiados entre cliente y servicio.
- **Mensaje SOAP**: Documento XML que contiene la petición o respuesta entre cliente y servicio web.
- **XML (eXtensible Markup Language)**: Lenguaje de marcado utilizado para estructurar datos intercambiados en servicios web.
- **HTTP**: Protocolo de transporte utilizado habitualmente para enviar mensajes SOAP.

## Descripción y consumo del servicio
- **WSDL (Web Services Description Language)**: Lenguaje basado en XML que describe las operaciones, parámetros y localización de un servicio web.
- **Contrato del servicio**: Conjunto de reglas definidas en el WSDL que indican cómo debe consumirse el servicio.
- **UDDI (Universal Description, Discovery and Integration)**: Sistema de publicación y localización de servicios web.
- **Publicación del servicio**: Proceso por el cual un servicio web se pone a disposición de los clientes.
- **Consumo del servicio**: Proceso mediante el cual un cliente invoca las operaciones de un servicio web.

## Servicios web en Java
- **JAX-WS**: Especificación Java para la creación y consumo de servicios web SOAP.
- **Servidor de aplicaciones**: Entorno que permite desplegar y ejecutar servicios web Java.
- **Cliente SOAP**: Aplicación Java que consume un servicio web SOAP mediante las clases generadas a partir del WSDL.

## Conceptos clave de examen
- **Independencia de implementación**: El cliente puede usar un servicio sin conocer cómo está implementado internamente.
- **Comunicación cliente/servidor**: Modelo en el que el cliente solicita operaciones y el servidor responde.
- **Enfoque conceptual**: En este tema se evalúa la comprensión del modelo y los componentes, no la implementación completa.

# Código básico del tema

En el **Tema 12 (Servicios web SOAP)** el bloque de **código** se divide en **4 puntos**:

1. **Servicio web SOAP en Java**  
2. **Publicación del servicio web**  
3. **Cliente SOAP en Java**  
4. **Relación código ↔ WSDL (interpretación para examen)**

---

## 1. Servicio web SOAP en Java (estructura mínima)

Ejemplo de **servicio web SOAP** definido en Java.  
Se crea una clase pública que expone operaciones accesibles desde la red.

```java
import javax.jws.WebMethod;
import javax.jws.WebService;

@WebService
public class ServicioEjemplo {

    @WebMethod
    public String saludar(String nombre) {
        return "Hola " + nombre;
    }
}

```

## 2. Publicación del servicio web SOAP

Para que un servicio web SOAP pueda ser consumido por clientes, debe ser **publicado** en una dirección accesible a través de la red.

```java
import javax.xml.ws.Endpoint;

public class PublicadorServicio {

    public static void main(String[] args) {

        Endpoint.publish(
                "http://localhost:8080/ServicioEjemplo",
                new ServicioEjemplo()
        );

        System.out.println("Servicio publicado");
    }
}

```
## 3. Cliente SOAP en Java (estructura mínima)

El **cliente SOAP** es la aplicación que **consume** el servicio web publicado, invocando sus operaciones a partir del **WSDL**.  
En Java, el cliente se apoya en clases **generadas automáticamente** desde el WSDL (no se escriben a mano).

```java
public class ClienteSOAP {

    public static void main(String[] args) {

        ServicioEjemplo_Service servicio = new ServicioEjemplo_Service();
        ServicioEjemplo puerto = servicio.getServicioEjemploPort();

        String respuesta = puerto.saludar("Nuria");
        System.out.println(respuesta);
    }
}
```

## 4. Relación código ↔ WSDL (interpretación para examen)

El **WSDL (Web Services Description Language)** es el **contrato** que describe formalmente un servicio web SOAP.  
No se programa manualmente en este tema, pero **es imprescindible saber interpretarlo** y relacionarlo con el código Java.

### Qué describe el WSDL
- **Operaciones** disponibles del servicio.
- **Parámetros** de entrada y salida de cada operación.
- **Tipos de datos** intercambiados (basados en XML).
- **Puerto** y **endpoint** (URL) donde está publicado el servicio.
- **Protocolo** y formato de comunicación (SOAP sobre HTTP).

### Relación directa con el código Java
- La clase anotada con `@WebService` → **define el servicio**.
- Cada método anotado con `@WebMethod` → **una operación del WSDL**.
- Los parámetros del método → **mensajes de entrada (request)**.
- El valor de retorno → **mensaje de salida (response)**.
- `Endpoint.publish(URL, servicio)` → **endpoint** que aparece en el WSDL.

### Qué ocurre al publicar el servicio
- Java **genera automáticamente** el WSDL.
- El WSDL queda accesible en una URL asociada al servicio.
- A partir del WSDL se **generan las clases cliente** (proxies).

### Qué ocurre en el cliente
- El cliente **no conoce la implementación** del servicio.
- Usa clases generadas desde el WSDL:
  - Clase `*_Service` → acceso al servicio.
  - Puerto (`get...Port()`) → canal de comunicación.
- Las llamadas a métodos Java se traducen internamente en **mensajes SOAP (XML)**.

### Claves típicas de examen
- El **WSDL es el contrato**, no el código Java.
- Cliente y servidor están **desacoplados**.
- SOAP usa **XML** para el intercambio de mensajes.
- El programador **no escribe SOAP ni WSDL a mano** en Java.
- Cambios en la implementación **no afectan al cliente** si el WSDL no cambia.

Este punto cierra el tema desde el enfoque exigido:  
**comprender el papel del WSDL como nexo entre servicio y cliente**, no implementarlo manualmente.





