# TEMA 10: Los servicios en red. Sockets I  
**Asignatura: Programación de Servicios y Procesos**

## Objetivo del tema
Comprender el uso de los **sockets** como mecanismo de comunicación entre aplicaciones en red, diferenciando entre comunicaciones **TCP y UDP**, e identificando las clases Java implicadas, el flujo básico cliente/servidor y el tratamiento de datos y excepciones en cada caso.

## Índice
1. Definición de Sockets  
2. Sockets TCP y Sockets UDP  
3. Programación de un servidor TCP  
4. Programación de un cliente TCP  
5. Clases `DatagramPacket` y `DatagramSocket`  
6. Programación de un servidor UDP  
7. Programación de un cliente UDP  

---

## 1. Definición de Sockets
Un **socket** es un mecanismo de comunicación entre aplicaciones utilizado principalmente en redes. Puede entenderse como **uno de los extremos de una conexión bidireccional** entre dos programas que se ejecutan en red.

Cada socket queda identificado por:
- Una **dirección IP**.
- Un **puerto**.

Los sockets representan los extremos del canal de comunicación necesario para que dos aplicaciones puedan intercambiar información.

En Java se distinguen dos grandes tipos de sockets en función del protocolo de transporte utilizado:
- **Sockets TCP** (orientados a conexión).
- **Sockets UDP** (no orientados a conexión).

---

## 2. Sockets TCP y Sockets UDP

### Sockets TCP
Los sockets TCP utilizan el protocolo **TCP**, que es un protocolo **orientado a conexión**. Esto implica que la comunicación no comienza hasta que ambos extremos han establecido la conexión.

Características principales:
- Garantizan la **entrega de los datos**.
- Los datos llegan **en orden**.
- La información se transmite en forma de **bytes**.
- Son más seguros y fiables, aunque más lentos que UDP.

Clases Java asociadas:
- `Socket`: representa el socket del cliente.
- `ServerSocket`: representa el socket del servidor, cuya función es esperar conexiones entrantes.

### Sockets UDP
Los sockets UDP utilizan el protocolo **UDP**, que es un protocolo **no orientado a conexión**.

Características principales:
- No existe una conexión previa entre cliente y servidor.
- Los datos se envían en forma de **datagramas**.
- Son más rápidos que TCP.
- No garantizan la entrega ni el orden de los mensajes.
- Ofrecen menor seguridad y fiabilidad.

Clases Java asociadas:
- `DatagramSocket`
- `DatagramPacket`

---

## 3. Programación de un servidor TCP
Un **servidor TCP** es el encargado de esperar conexiones de clientes y comunicarse con ellos una vez establecida la conexión.

Pasos generales para programar un servidor TCP en Java:
1. Crear un objeto `ServerSocket` asociado a un **puerto**.
2. Esperar conexiones de clientes mediante el método `accept()`.
3. Obtener los **flujos de entrada y salida** del socket del cliente.
4. Enviar y recibir información mediante dichos flujos.
5. Cerrar los flujos y el socket una vez finalizada la comunicación.
6. Controlar posibles errores mediante bloques `try-catch`.

La comunicación suele realizarse mediante métodos como `readUTF()` y `writeUTF()` para el intercambio de mensajes.

---

## 4. Programación de un cliente TCP
El **cliente TCP** es la aplicación que inicia la conexión con el servidor.

Pasos generales para programar un cliente TCP en Java:
1. Crear un objeto `Socket` indicando la **dirección IP o host** y el **puerto** del servidor.
2. Crear los flujos de entrada y salida asociados al socket.
3. Enviar datos al servidor y recibir la respuesta.
4. Cerrar los flujos y el socket al finalizar la comunicación.
5. Gestionar excepciones mediante `try-catch`.

El cliente y el servidor deben utilizar el mismo protocolo de comunicación y el mismo puerto para poder intercambiar información correctamente.

---

## 5. Clases `DatagramPacket` y `DatagramSocket`
En las comunicaciones UDP se utilizan **datagramas**, que son paquetes de datos independientes enviados a una dirección IP y un puerto concretos.

### Clase `DatagramPacket`
Representa un datagrama que puede enviarse o recibirse.

Un datagrama está compuesto por:
- Un **array de bytes** (datos).
- La **longitud** del mensaje.
- La **dirección IP de destino**.
- El **puerto de destino**.

Métodos principales:
- `getData()`: devuelve el array de bytes.
- `getLength()`: devuelve la longitud del mensaje.
- `getPort()`: devuelve el puerto.
- `getAddress()`: devuelve la dirección IP remota.

### Clase `DatagramSocket`
Representa el socket UDP encargado de enviar y recibir datagramas.

Métodos principales:
- `send(DatagramPacket)`: envía un datagrama.
- `receive(DatagramPacket)`: recibe un datagrama.
- `close()`: cierra el socket.
- `getLocalPort()`: devuelve el puerto local del socket.

---

## 6. Programación de un servidor UDP
En UDP no existe una conexión previa, por lo que la distinción entre cliente y servidor es menos estricta. Se considera **servidor UDP** al que espera recibir un mensaje y responde a él.

Pasos generales para programar un servidor UDP en Java:
1. Crear un objeto `DatagramSocket` asociado a un **puerto**.
2. Crear un array de bytes para almacenar los datos.
3. Crear un objeto `DatagramPacket` para recibir mensajes.
4. Esperar la recepción de un datagrama mediante `receive()`.
5. Procesar el mensaje recibido.
6. Enviar una respuesta usando `send()`.
7. Controlar excepciones con `try-catch`.

En UDP no es necesario cerrar una conexión como en TCP, ya que no existe una conexión persistente.

---

## 7. Programación de un cliente UDP
El **cliente UDP** es el que inicia la comunicación enviando un datagrama al servidor.

Pasos generales para programar un cliente UDP en Java:
1. Crear un objeto `DatagramSocket`.
2. Preparar los datos a enviar en un array de bytes.
3. Crear un `DatagramPacket` con los datos, la IP y el puerto del servidor.
4. Enviar el datagrama mediante `send()`.
5. Crear un nuevo `DatagramPacket` para recibir la respuesta.
6. Recibir la respuesta con `receive()`.
7. Procesar el mensaje recibido.
8. Cerrar el socket al finalizar.

Este modelo permite comunicaciones rápidas y sencillas, a costa de no garantizar la entrega ni el orden de los mensajes.

---

# Glosario — Tema 10: Los servicios en red. Sockets I  
**Programación de Servicios y Procesos**

## Términos generales
- **Socket**: Mecanismo de comunicación entre aplicaciones en red que representa uno de los extremos de una conexión bidireccional entre dos programas que se ejecutan en red. Se identifica por una dirección IP y un puerto.  
- **Comunicación en red**: Intercambio de información entre aplicaciones que se ejecutan en distintos dispositivos conectados a una red.  
- **Dirección IP**: Identificador numérico que permite localizar un dispositivo dentro de una red.  
- **Puerto**: Número lógico que identifica un servicio o proceso concreto dentro de un dispositivo y permite dirigir la comunicación al destino correcto.  

## Protocolos de transporte
- **TCP (Transmission Control Protocol)**: Protocolo de transporte orientado a conexión que garantiza la entrega de los datos y su orden correcto. Es más fiable pero más lento que UDP.  
- **UDP (User Datagram Protocol)**: Protocolo de transporte no orientado a conexión que envía los datos en forma de datagramas. Es más rápido que TCP, pero no garantiza la entrega ni el orden de los mensajes.  

## Sockets TCP
- **Socket TCP**: Socket que utiliza el protocolo TCP para establecer una comunicación orientada a conexión entre cliente y servidor. La transmisión de datos se realiza en bytes.  
- **ServerSocket**: Clase de Java utilizada para implementar un servidor TCP. Su función principal es esperar conexiones de clientes mediante el método `accept()`.  
- **Cliente TCP**: Aplicación que inicia la conexión con un servidor TCP utilizando un socket asociado a una IP y un puerto.  
- **Servidor TCP**: Aplicación que permanece a la espera de conexiones de clientes y gestiona la comunicación una vez establecida la conexión.  
- **Flujos de entrada y salida**: Canales de comunicación asociados a un socket TCP que permiten leer y escribir datos entre cliente y servidor.  

## Sockets UDP
- **Socket UDP**: Socket que utiliza el protocolo UDP y no requiere establecer una conexión previa entre cliente y servidor.  
- **Datagrama**: Paquete de datos independiente enviado a una dirección IP y un puerto concretos en una comunicación UDP.  
- **DatagramPacket**: Clase de Java que representa un datagrama, permitiendo enviar o recibir paquetes de datos en una comunicación UDP.  
- **DatagramSocket**: Clase de Java que permite crear un socket UDP para enviar y recibir datagramas.  
- **Servidor UDP**: Aplicación que espera recibir un datagrama de un cliente y responde enviando otro datagrama. No existe conexión persistente.  
- **Cliente UDP**: Aplicación que inicia la comunicación enviando un datagrama al servidor UDP.  

## Conceptos de programación
- **Orientado a conexión**: Característica de los sockets TCP por la que la comunicación solo comienza cuando cliente y servidor han establecido una conexión.  
- **No orientado a conexión**: Característica de los sockets UDP por la que no existe una conexión previa y los mensajes se envían de forma independiente.  
- **Bytes**: Forma en la que se transmiten los datos en una comunicación mediante sockets TCP.  
- **Control de excepciones**: Gestión de errores que pueden producirse durante la comunicación en red mediante bloques `try-catch`.  
- **Cliente/Servidor**: Modelo de comunicación en el que un cliente solicita un servicio y un servidor lo ofrece y responde a la petición.  


---
# TEMA 10 — Código Java (Sockets I) explicado punto por punto

## Objetivo del bloque
Reconocer, escribir y explicar el **código mínimo** para:
- Servidor TCP (`ServerSocket`) y Cliente TCP (`Socket`)
- Servidor UDP y Cliente UDP (`DatagramSocket`, `DatagramPacket`)
- Flujos (TCP), datagramas (UDP) y control básico de excepciones

## Índice
1. Servidor TCP (estructura mínima)
2. Cliente TCP (estructura mínima)
3. UDP: `DatagramPacket` y `DatagramSocket` (estructura del datagrama)
4. Servidor UDP (estructura mínima)
5. Cliente UDP (estructura mínima)

---

## 1. Servidor TCP (estructura mínima)

```java
import java.io.DataInputStream;
import java.io.DataOutputStream;
import java.net.ServerSocket;
import java.net.Socket;

public class ServidorTCP {
    private static final int PUERTO = 6000;

    public static void main(String[] args) {
        try (ServerSocket servidor = new ServerSocket(PUERTO)) {

            while (true) {
                Socket cliente = servidor.accept();

                DataInputStream entrada = new DataInputStream(cliente.getInputStream());
                DataOutputStream salida = new DataOutputStream(cliente.getOutputStream());

                String mensaje = entrada.readUTF();
                salida.writeUTF("Servidor recibió: " + mensaje);

                cliente.close();
            }

        } catch (Exception e) {
            System.out.println("Error servidor TCP: " + e.getMessage());
        }
    }
}

´´´
## 2. Cliente TCP (estructura mínima)

```java
import java.io.DataInputStream;
import java.io.DataOutputStream;
import java.net.Socket;

public class ClienteTCP {
    private static final String HOST = "localhost";
    private static final int PUERTO = 6000;

    public static void main(String[] args) {
        try (Socket socket = new Socket(HOST, PUERTO)) {

            DataOutputStream salida = new DataOutputStream(socket.getOutputStream());
            DataInputStream entrada = new DataInputStream(socket.getInputStream());

            salida.writeUTF("Hola servidor");
            String respuesta = entrada.readUTF();

            System.out.println("Respuesta del servidor: " + respuesta);

        } catch (Exception e) {
            System.out.println("Error cliente TCP: " + e.getMessage());
        }
    }
}

´´´
## 3. UDP — `DatagramPacket` y `DatagramSocket` (estructura mínima)

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;

public class UdpBasico {
    public static void main(String[] args) {
        try {
            // Crear socket UDP (sin conexión)
            DatagramSocket socket = new DatagramSocket();

            // Datos a enviar
            byte[] datos = "Mensaje UDP".getBytes();

            // Crear datagrama (datos + destino)
            InetAddress destino = InetAddress.getByName("localhost");
            int puertoDestino = 6789;
            DatagramPacket paquete = new DatagramPacket(
                    datos, datos.length, destino, puertoDestino
            );

            // Enviar datagrama
            socket.send(paquete);

            // Preparar recepción
            byte[] buffer = new byte[1024];
            DatagramPacket recibido = new DatagramPacket(buffer, buffer.length);

            // Recibir datagrama
            socket.receive(recibido);

            // Cerrar socket
            socket.close();

        } catch (Exception e) {
            System.out.println("Error UDP: " + e.getMessage());
        }
    }
}
´´´
## 4. Servidor UDP (estructura mínima)

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;

public class ServidorUDP {
    private static final int PUERTO = 6789;

    public static void main(String[] args) {
        try {
            DatagramSocket socket = new DatagramSocket(PUERTO);

            byte[] buffer = new byte[1024];
            DatagramPacket recibido = new DatagramPacket(buffer, buffer.length);

            socket.receive(recibido);

            String mensaje = new String(
                    recibido.getData(), 0, recibido.getLength()
            );

            InetAddress clienteIP = recibido.getAddress();
            int clientePuerto = recibido.getPort();

            byte[] respuesta = ("Recibido: " + mensaje).getBytes();
            DatagramPacket envio = new DatagramPacket(
                    respuesta, respuesta.length, clienteIP, clientePuerto
            );

            socket.send(envio);
            socket.close();

        } catch (Exception e) {
            System.out.println("Error servidor UDP: " + e.getMessage());
        }
    }
}

´´´

## 5. Cliente UDP (estructura mínima)

```java
import java.net.DatagramPacket;
import java.net.DatagramSocket;
import java.net.InetAddress;

public class ClienteUDP {
    private static final String HOST = "localhost";
    private static final int PUERTO = 6789;

    public static void main(String[] args) {
        try {
            DatagramSocket socket = new DatagramSocket();

            byte[] datos = "Hola servidor UDP".getBytes();
            InetAddress servidorIP = InetAddress.getByName(HOST);

            DatagramPacket envio = new DatagramPacket(
                    datos, datos.length, servidorIP, PUERTO
            );

            socket.send(envio);

            byte[] buffer = new byte[1024];
            DatagramPacket recibido = new DatagramPacket(buffer, buffer.length);

            socket.receive(recibido);

            socket.close();

        } catch (Exception e) {
            System.out.println("Error cliente UDP: " + e.getMessage());
        }
    }
}
´´´