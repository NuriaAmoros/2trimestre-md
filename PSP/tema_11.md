# TEMA 11: Los servicios en red. Sockets II  
**Asignatura: Programación de Servicios y Procesos**

## Objetivo del tema
Comprender cómo implementar **clientes de distintos servicios en red** (HTTP, FTP, Telnet y SMTP) utilizando Java, así como introducir el uso de **hilos (hebras)** en servidores con sockets para permitir la **atención concurrente de múltiples clientes**.

## Índice
1. Programación de un cliente HTTP  
2. Programación de un cliente FTP  
3. Programación de un cliente Telnet  
4. Programación de un cliente SMTP  
5. Sockets e hilos: concurrencia en servidores  
6. Arquitectura cliente/servidor concurrente con TCP  

---

## 1. Programación de un cliente HTTP
La comunicación HTTP se basa en un **modelo petición–respuesta** entre cliente y servidor. El cliente establece una conexión, envía una solicitud y el servidor responde con el resultado correspondiente.

En Java, la implementación de clientes HTTP se realiza a **alto nivel**, sin necesidad de trabajar directamente con sockets, mediante las siguientes clases:
- **URL**: representa una dirección web y permite manipularla desde el programa.
- **URLConnection**: permite abrir una conexión con la URL y realizar operaciones como peticiones GET.

El uso de estas clases abstrae los detalles internos del protocolo HTTP, facilitando la implementación de clientes web y ocultando la complejidad de la comunicación de bajo nivel.

---

## 2. Programación de un cliente FTP
FTP (File Transfer Protocol) se utiliza para la **transferencia de ficheros** entre un cliente y un servidor.

El proceso general para crear un cliente FTP es:
- Establecer conexión con el servidor.
- Comprobar que la conexión se ha realizado correctamente.
- Validar el usuario FTP.
- Realizar las operaciones solicitadas (subir, descargar, listar ficheros).
- Cerrar la conexión al finalizar.

Java no dispone de clases nativas específicas para FTP, por lo que se emplean **librerías externas**, destacando la API `org.apache.commons.net.ftp`, que proporciona:
- **FTP / FTPClient**: clases principales para implementar clientes FTP.
- **FTPReply**: permite interpretar las respuestas del servidor.
- **FTPClientConfig**: configuración del cliente.
- **FTPSClient**: versión segura del protocolo FTP mediante SSL.

Durante este proceso es necesario gestionar excepciones como `SocketException` e `IOException`.

---

## 3. Programación de un cliente Telnet
El protocolo **Telnet** permite la **administración remota de equipos** a través de una conexión en red, funcionando como si el usuario estuviera físicamente frente al sistema remoto.

Características principales:
- Modelo **cliente/servidor**.
- Utiliza el **puerto 23**.
- Comunicación basada en **comandos en texto plano**.

Debido a que toda la información, incluidas credenciales, se transmite sin cifrar, Telnet ofrece **baja seguridad**, motivo por el cual su uso es limitado en entornos profesionales.

Para trabajar con Telnet en Java se utiliza la librería:
- `org.apache.commons.net.telnet`
  - **TelnetClient**: clase que permite implementar un cliente Telnet, heredando de `SocketClient`.

Esta clase proporciona métodos para conectarse al servidor, obtener los flujos de entrada y salida y cerrar la conexión.

---

## 4. Programación de un cliente SMTP
SMTP es el protocolo utilizado para el **envío de correos electrónicos**.

Para implementar clientes SMTP en Java se emplea la API **javax.mail**, que abstrae la complejidad del protocolo y facilita la gestión del correo electrónico. Las clases principales son:
- **Session**: representa una sesión de correo electrónico con la configuración necesaria.
- **Message**: representa un mensaje de correo, permitiendo definir remitente, asunto y contenido.
- **Transport**: gestiona el envío del mensaje al servidor SMTP.

Mediante estas clases es posible crear aplicaciones Java capaces de enviar correos electrónicos utilizando cuentas de servicios reales, como servidores de correo corporativos o proveedores externos.

---

## 5. Sockets e hilos: concurrencia en servidores
Los servidores implementados en temas anteriores presentan una limitación importante: **solo pueden atender a un cliente a la vez**. Esto provoca colas de espera y reduce la eficiencia del servicio.

La solución es introducir **concurrencia** mediante el uso de **hilos (hebras)**:
- Cada vez que el servidor acepta una conexión, crea una hebra para atender a ese cliente.
- El servidor principal queda libre para aceptar nuevas conexiones.
- Cada cliente es atendido de forma independiente.

La concurrencia se implementa **en el servidor**, siendo transparente para el cliente, que no percibe si es atendido por el servidor principal o por una hebra.

---

## 6. Arquitectura cliente/servidor concurrente con TCP
Para crear un sistema cliente/servidor concurrente con TCP se utilizan varias clases:
- **Servidor**: crea un `ServerSocket` y espera conexiones.
- **ServidorHebra**: clase que representa la hebra encargada de atender a un cliente concreto. Puede implementarse heredando de `Thread` o implementando `Runnable`.
- **Cliente**: se conecta al servidor mediante un `Socket` y se comunica de forma normal.

El flujo general es:
- El servidor acepta una conexión.
- Crea una instancia de `ServidorHebra`, pasándole los flujos de entrada y salida del cliente.
- Lanza la hebra para atender la petición.
- El servidor vuelve a escuchar nuevas conexiones.

Este modelo permite atender a múltiples clientes simultáneamente y constituye la base de los **servidores concurrentes** en Java.


---

# Glosario — Tema 11: Los servicios en red. Sockets II  
**Programación de Servicios y Procesos**

## Términos generales
- **Servicio en red**: Funcionalidad ofrecida por una aplicación que permite la comunicación entre clientes y servidores a través de una red.
- **Socket**: Punto final de una comunicación entre dos aplicaciones que se ejecutan en red, identificado por una dirección IP y un puerto.
- **Cliente**: Aplicación que inicia una conexión para solicitar un servicio a un servidor.
- **Servidor**: Aplicación que espera conexiones de clientes y ofrece uno o varios servicios.
- **Modelo cliente/servidor**: Arquitectura en la que un cliente solicita un servicio y un servidor procesa la petición y devuelve una respuesta.

## Cliente HTTP
- **HTTP (HyperText Transfer Protocol)**: Protocolo de la capa de aplicación basado en un modelo petición–respuesta para la transferencia de información en la web.
- **Petición HTTP**: Mensaje enviado por el cliente solicitando un recurso al servidor.
- **Respuesta HTTP**: Mensaje enviado por el servidor con el resultado de la petición.
- **URL (Uniform Resource Locator)**: Dirección que identifica un recurso en la web.
- **URLConnection**: Clase de Java que permite abrir una conexión con una URL y realizar operaciones HTTP de alto nivel.

## Cliente FTP
- **FTP (File Transfer Protocol)**: Protocolo utilizado para la transferencia de ficheros entre un cliente y un servidor.
- **Cliente FTP**: Aplicación que se conecta a un servidor FTP para subir, descargar o gestionar archivos.
- **Apache Commons Net**: Biblioteca externa de Java que proporciona clases para trabajar con protocolos como FTP y Telnet.
- **FTPClient**: Clase principal para implementar clientes FTP en Java.
- **FTPReply**: Clase que permite interpretar las respuestas devueltas por un servidor FTP.
- **FTPS**: Versión segura del protocolo FTP que utiliza cifrado SSL.

## Cliente Telnet
- **Telnet**: Protocolo que permite la administración remota de equipos mediante comandos en modo texto.
- **Puerto 23**: Puerto utilizado por defecto por el protocolo Telnet.
- **Texto plano**: Forma de transmisión de datos sin cifrado, característica del protocolo Telnet.
- **TelnetClient**: Clase de la biblioteca Apache Commons Net que permite implementar clientes Telnet en Java.

## Cliente SMTP
- **SMTP (Simple Mail Transfer Protocol)**: Protocolo utilizado para el envío de correos electrónicos.
- **Correo electrónico**: Servicio que permite enviar y recibir mensajes a través de la red.
- **javax.mail**: API de Java utilizada para la gestión y envío de correos electrónicos.
- **Session**: Clase que representa una sesión de correo con su configuración asociada.
- **Message**: Clase que representa un mensaje de correo electrónico.
- **Transport**: Clase encargada de enviar los mensajes mediante el protocolo SMTP.

## Concurrencia y hilos
- **Concurrencia**: Capacidad de un sistema para atender varias tareas o clientes de forma simultánea.
- **Hebra (hilo)**: Unidad de ejecución que permite realizar tareas concurrentes dentro de una aplicación.
- **Servidor concurrente**: Servidor capaz de atender a varios clientes al mismo tiempo mediante el uso de hilos.
- **Thread**: Clase de Java que permite crear una hebra heredando de ella.
- **Runnable**: Interfaz de Java que permite definir una tarea que será ejecutada por una hebra.
- **ServidorHebra**: Clase que representa la hebra encargada de atender a un cliente concreto en un servidor concurrente.
- **Flujos de entrada y salida**: Canales de comunicación asociados a un socket que permiten recibir y enviar información entre cliente y servidor.

# TEMA 11 — Código Java (Sockets II)  
**Código mínimo y reconocible, orientado a examen**

---

## 1. Cliente HTTP (estructura mínima)

```java
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.net.URL;
import java.net.URLConnection;

public class ClienteHTTP {
    public static void main(String[] args) {
        try {
            URL url = new URL("https://www.google.es");
            URLConnection conexion = url.openConnection();

            BufferedReader lector = new BufferedReader(
                    new InputStreamReader(conexion.getInputStream())
            );

            String linea;
            while ((linea = lector.readLine()) != null) {
                System.out.println(linea);
            }

            lector.close();

        } catch (Exception e) {
            System.out.println("Error HTTP: " + e.getMessage());
        }
    }
}


