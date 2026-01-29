# TEMA 9: Protocolos a nivel de aplicación  
**Asignatura: Programación de Servicios y Procesos**

## Objetivo del tema
Comprender la capa de aplicación del modelo TCP/IP y los principales protocolos que operan en ella, identificando su finalidad, funcionamiento básico y el papel que desempeñan en la comunicación entre aplicaciones cliente y servidor dentro de los servicios en red.

## Índice
1. Introducción a los servicios en red  
2. Protocolos a nivel de aplicación  
3. El protocolo DNS  
4. El protocolo FTP  
5. Los protocolos SMTP, POP3 e IMAP  
6. El protocolo HTTP  

---

## 1. Introducción a los servicios en red
Para que las aplicaciones puedan comunicarse mediante el envío y recepción de mensajes, es necesario disponer de una red de ordenadores interconectados. Una red informática se define como un sistema de telecomunicaciones cuyo objetivo es compartir información y recursos entre distintos dispositivos.

La utilización de servicios en red permite mejorar el rendimiento y la eficacia del sistema, ya que los datos y recursos pueden ser utilizados por múltiples usuarios de forma distribuida. Entre las principales ventajas de las redes destacan la reducción de costes, la mejora en la administración de sistemas, el aumento de la integridad y seguridad de los datos y la facilitación de la comunicación entre usuarios.

Los servicios en red se pueden clasificar en distintas categorías:  
- Servicios de administración y configuración, como DNS o DHCP.  
- Servicios de acceso remoto, como Telnet o SSH.  
- Servicios de ficheros, como FTP.  
- Servicios de impresión.  
- Servicios de información, como HTTP.  
- Servicios de comunicación, como SMTP.  

Estos servicios se apoyan en protocolos que definen cómo se realiza la comunicación entre aplicaciones.

---

## 2. Protocolos a nivel de aplicación
Los protocolos más utilizados en la actualidad se engloban dentro del modelo TCP/IP. La capa de aplicación es la capa superior de este modelo y contiene todos los protocolos relacionados con los servicios en red que utilizan directamente las aplicaciones.

En esta capa se definen las normas que deben seguir las aplicaciones para intercambiar datos entre sí. El número de protocolos en la capa de aplicación es muy amplio y crece constantemente debido a la aparición de nuevos servicios.

Entre los protocolos más relevantes de esta capa se encuentran: FTP, Telnet, SMTP, HTTP, SSH, DNS, entre otros. Estos protocolos no suelen implementarse desde cero, ya que existen bibliotecas y herramientas que facilitan su uso, especialmente en lenguajes como Java.

---

## 3. El protocolo DNS
Todos los dispositivos conectados a una red TCP/IP se identifican mediante una dirección IP. Estas direcciones son fáciles de manejar para los sistemas, pero difíciles de recordar para las personas.

El protocolo DNS (Domain Name System) surge para resolver este problema, permitiendo asociar nombres de dominio legibles por humanos a direcciones IP numéricas. De este modo, es posible acceder a un servidor utilizando un nombre como un dominio web en lugar de una IP.

El servicio DNS se encarga de traducir nombres de dominio a direcciones IP y viceversa. Utiliza una base de datos distribuida que almacena la información necesaria para resolver estos nombres en redes como Internet. Gracias a DNS, un mismo servidor puede responder a varios dominios y un dominio puede cambiar de nombre sin modificar su dirección IP.

---

## 4. El protocolo FTP
El protocolo FTP (File Transfer Protocol) se utiliza para la transferencia de ficheros entre ordenadores conectados a una red, ya sea local o a través de Internet. Proporciona un estándar que permite intercambiar archivos de cualquier tamaño entre sistemas remotos.

FTP se caracteriza por permitir una transferencia rápida de datos, pero presenta una desventaja importante: transmite la información en texto plano, lo que implica una baja seguridad, ya que los datos pueden ser interceptados durante la transmisión.

Para solucionar este problema de seguridad se utiliza SFTP, que combina la transferencia de ficheros con el protocolo SSH para cifrar la información. FTP utiliza habitualmente el puerto 21 para el control de la conexión y el puerto 20 para la transferencia de datos. Además, admite distintos modos de conexión, como el modo activo y el modo pasivo.

---

## 5. Los protocolos SMTP, POP3 e IMAP
El correo electrónico es uno de los servicios más utilizados en la actualidad y se basa en varios protocolos de la capa de aplicación. El protocolo SMTP (Simple Mail Transfer Protocol) se encarga del envío de correos electrónicos desde el cliente al servidor y entre servidores de correo.

El sistema de correo electrónico sigue un modelo cliente/servidor, en el que el servidor almacena los mensajes en buzones asociados a cada usuario. Para acceder a estos mensajes, el destinatario puede utilizar dos protocolos distintos.

POP3 permite descargar los correos del servidor al equipo local del usuario, mientras que IMAP permite consultar los mensajes directamente en el servidor sin necesidad de descargarlos completamente. Estos protocolos hacen posible la gestión del correo electrónico y el envío de mensajes con contenido y archivos adjuntos.

---

## 6. El protocolo HTTP
El protocolo HTTP (HyperText Transfer Protocol) es el encargado de permitir la navegación por Internet. Define un conjunto de normas que regulan la comunicación entre un cliente y un servidor para la transferencia de información, principalmente páginas HTML.

HTTP sigue un modelo de petición–respuesta, en el que el cliente solicita un recurso identificado por una URL y el servidor responde enviando el contenido correspondiente. El protocolo utiliza por defecto el puerto 80 y considera toda la información transmitida como recursos, que pueden ser documentos, resultados de consultas o datos generados por programas.

Una característica fundamental de HTTP es que es un protocolo sin estado, lo que significa que no mantiene información sobre conexiones anteriores. Cada petición se procesa de forma independiente, lo que simplifica la comunicación pero requiere mecanismos adicionales cuando es necesario mantener información entre peticiones.

---

# Glosario — Tema 9: Protocolos a nivel de aplicación (PSP)
*(Definiciones alineadas con el contenido del PDF)* 

## Términos base
- **Red de ordenadores**: Conjunto de equipos interconectados (sistema de telecomunicaciones) cuyo fin es compartir información o recursos. 

- **Servicio en red**: Funcionalidad ofrecida a través de la red que permite administración, acceso remoto, transferencia de ficheros, información o comunicación entre usuarios/aplicaciones. 

- **Protocolo**: Conjunto de normas que definen la sintaxis y reglas de comunicación que deben seguir cliente y servidor para intercambiar información. 

- **Modelo TCP/IP**: Conjunto de protocolos base de las comunicaciones actuales; su **capa de aplicación** agrupa protocolos usados por aplicaciones para intercambiar datos. 

- **Capa de aplicación (TCP/IP)**: Capa superior del modelo TCP/IP que contiene los protocolos relacionados con servicios en red utilizados por las aplicaciones. 

## Conceptos de identificación y nombres
- **Dirección IP (IPv4)**: Identificador numérico de un dispositivo en una red TCP/IP, típicamente con formato de cuatro números entre 0 y 255 separados por puntos (ej. 192.168.1.1). 

- **Nombre de dominio**: Identificador legible por humanos asociado a un nodo (ej. un dominio web), usado para facilitar el acceso sin memorizar IP. 

- **DNS (Domain Name System)**: Servicio/protocolo que traduce **nombres de dominio ↔ direcciones IP**, apoyándose en una base de datos distribuida. 

- **Servidor DNS**: Sistema que consulta/gestiona la información de resolución de nombres mediante una base de datos distribuida para proporcionar traducciones dominio↔IP. 

## Transferencia de ficheros
- **FTP (File Transfer Protocol)**: Protocolo de transferencia de ficheros en redes TCP/IP que permite intercambio de archivos entre sistemas remotos y transferencias rápidas. 

- **FTP en texto plano**: Característica de FTP por la que la información viaja sin cifrado (legible si es interceptada), lo que supone baja seguridad. 

- **SFTP**: Protocolo de transferencia de ficheros seguro que usa cifrado mediante SSH para solucionar la falta de seguridad de FTP. 

- **Puerto**: Número lógico asociado a un servicio/protocolo para identificar el punto de comunicación en una máquina. (En el tema se asocia a FTP/HTTP/SMTP). 

- **Puertos FTP**: FTP usa **20** para transmisión de datos y **21** para transferencia de órdenes. 

- **Modo activo / modo pasivo (FTP)**: Formas de conexión en FTP; el tema indica que en modo activo habrá dos conexiones distintas, mientras que en modo pasivo no.

## Correo electrónico
- **Servicio de correo electrónico**: Servicio que permite enviar y recibir mensajes con o sin archivos de forma rápida por Internet. 

- **SMTP (Simple Mail Transfer Protocol)**: Protocolo de la capa de aplicación que permite el envío/transporte del correo, siguiendo el modelo cliente/servidor; usa el puerto **25**. 

- **Servidor de correo**: Sistema que gestiona cuentas y buzones de usuarios y almacena los correos para su posterior acceso. 

- **Cliente de correo**: Aplicación que permite redactar/descargar correos y operar contra un servidor de correo. 

- **Buzón**: Espacio asociado a una cuenta en el servidor donde se almacenan los correos del usuario. 

- **POP3**: Protocolo para acceder a los mensajes descargándolos a la máquina local del usuario. 

- **IMAP**: Protocolo para consultar los mensajes directamente en el servidor sin necesidad de descargarlos en local como enfoque principal. 

- **Comandos SMTP (ejemplos del tema)**:
  - **HELO**: Comando para abrir sesión con el servidor. 

  - **MAIL FROM**: Comando para indicar el emisor del correo. 


## Web y navegación
- **HTTP (HyperText Transfer Protocol)**: Protocolo que habilita la navegación por Internet; define normas de comunicación y transferencia de información entre cliente y servidor; transfiere páginas HTML. 

- **Modelo petición–respuesta (HTTP)**: Esquema donde el cliente solicita un recurso y el servidor responde con la información solicitada. 

- **Puerto HTTP**: HTTP utiliza el puerto **80** por defecto (con posibilidad de cambiarlo). 

- **User agent (agente de usuario)**: Nombre que recibe el cliente en HTTP. 

- **Recurso (HTTP)**: Cualquier información transmitida (páginas, ficheros, consultas a BD, resultados de operaciones, etc.) identificada mediante una URL.

- **URL**: Identificador del recurso en la web, por ejemplo con forma http://www.google.es, que puede incluir puerto. 

- **HTTP sin estado (stateless)**: Propiedad por la que HTTP no recuerda conexiones anteriores; cada petición se trata de forma independiente. 

## Arquitectura de comunicación
- **Modelo cliente/servidor**: Arquitectura en la que un cliente solicita servicios a un servidor, que procesa la petición y devuelve una respuesta. (Aplicable a SMTP y a la navegación HTTP según el tema). 

- **Bibliotecas predefinidas (Java/JDK)**: Implementaciones ya disponibles que permiten trabajar con protocolos sin tener que programarlos desde cero usando sockets, reduciendo esfuerzo y complejidad. 

- **Sockets (mención contextual del tema)**: Mecanismo de comunicación de red con el que podría implementarse un protocolo desde cero, aunque sería una tarea compleja y ardua. 

---

## 1. Principios de “código mínimo” en PSP
En este tema **no se exige** programar un servidor completo ni una implementación desde cero con sockets (eso sería “arduo” y fuera del enfoque principal). Lo que sí corresponde es **reconocer**:
- Uso de **clases estándar** para consumir servicios/protocolos (bibliotecas ya hechas en Java).   
- Dónde aparecen **URL, puertos, IP**, modelo **cliente/servidor** y **petición–respuesta**. 

- Qué significa que HTTP sea **sin estado** (stateless): el código hace una petición y termina; no “recuerda” anteriores. 

---

## 2. DNS en Java (resolución nombre ↔ IP)
DNS se encarga de traducir **nombres de dominio ↔ direcciones IP**. 

Código típico (cliente hace consulta de resolución):

```java
import java.net.InetAddress;

public class DnsDemo {
    public static void main(String[] args) throws Exception {
        // Resuelve nombre de dominio -> IP (DNS)
        InetAddress addr = InetAddress.getByName("www.google.es");
        System.out.println("IP: " + addr.getHostAddress());

        // Resuelve IP -> nombre (reverse lookup, si hay PTR/configuración)
        InetAddress byIp = InetAddress.getByName("8.8.8.8");
        System.out.println("Host: " + byIp.getHostName());
    }
}
```

## 3. HTTP en Java (petición–respuesta, puerto, URL)

HTTP es un protocolo de la **capa de aplicación** que sigue el modelo **petición–respuesta** entre un cliente (user agent) y un servidor. En Java, este comportamiento se reconoce mediante el uso de clases que representan URLs y conexiones HTTP.

Conceptos clave que se deben identificar en código:
- Uso de una **URL** para identificar un recurso.
- Apertura de una conexión cliente → servidor.
- Envío de una petición (habitualmente GET).
- Recepción de una respuesta (código de estado + datos).
- Cierre de la conexión.
- Puerto por defecto **80** (aunque puede indicarse otro).
- Protocolo **sin estado (stateless)**: cada petición es independiente.

Ejemplo mínimo de código HTTP en Java (lectura conceptual):

```java
URL url = new URL("http://example.com:80/");
HttpURLConnection con = (HttpURLConnection) url.openConnection();

con.setRequestMethod("GET");          // Petición HTTP
int status = con.getResponseCode();   // Respuesta del servidor

BufferedReader br = new BufferedReader(
        new InputStreamReader(con.getInputStream())
);

String linea;
while ((linea = br.readLine()) != null) {
    System.out.println(linea);        // Contenido del recurso (HTML)
}

con.disconnect();

```

## 4. FTP en Java (transferencia y puertos 20/21)

FTP (File Transfer Protocol) es un protocolo de la **capa de aplicación** destinado a la **transferencia de ficheros** entre sistemas conectados a una red. Permite intercambiar archivos de cualquier tamaño entre un cliente y un servidor remoto.

Características esenciales que deben conocerse:
- FTP sigue un modelo **cliente/servidor**.
- Está optimizado para la velocidad de transferencia.
- Transmite la información **en texto plano**, sin cifrado, lo que supone un problema de seguridad.
- Para resolver esta debilidad se utiliza **SFTP**, que cifra la comunicación usando SSH.
- FTP utiliza **dos puertos distintos**:
  - **Puerto 21**: canal de control (órdenes y comandos).
  - **Puerto 20**: canal de datos (transferencia de ficheros).

El uso de dos canales implica que FTP pueda funcionar en distintos modos:
- **Modo activo**: se establecen dos conexiones independientes (control y datos).
- **Modo pasivo**: el servidor espera conexiones iniciadas por el cliente.

En Java, **no se implementa FTP desde cero** para este tema. Lo importante es reconocer que:
- Existen bibliotecas que gestionan FTP automáticamente.
- No es necesario programar la lógica completa con sockets.
- El examen evalúa la **comprensión del protocolo**, no su implementación avanzada.

Ejemplo conceptual mínimo en Java (solo para identificar puertos y canales):

```java
Socket control = new Socket("ftp.servidor.com", 21); // Canal de control
Socket datos   = new Socket("ftp.servidor.com", 20); // Canal de datos
```

## 5. SMTP / POP3 / IMAP en Java  
*(qué se reconoce y por qué no es JDK puro)*

Los protocolos **SMTP, POP3 e IMAP** pertenecen a la **capa de aplicación** y permiten la gestión del **correo electrónico** siguiendo un modelo **cliente/servidor**. En este tema no se exige implementar un sistema de correo completo, sino **reconocer el papel de cada protocolo y su reflejo conceptual en Java**.

### Función de cada protocolo
- **SMTP (Simple Mail Transfer Protocol)**  
  Protocolo encargado del **envío del correo** desde el cliente al servidor y entre servidores de correo.  
  Utiliza el **puerto 25**.  
  Es responsable del transporte del mensaje, no de su lectura posterior.

- **POP3 (Post Office Protocol v3)**  
  Protocolo utilizado para **descargar los correos** del servidor al equipo local del usuario.  
  Una vez descargados, los mensajes suelen dejar de estar disponibles en el servidor.

- **IMAP (Internet Message Access Protocol)**  
  Protocolo que permite **consultar y gestionar los correos directamente en el servidor**, manteniéndolos almacenados de forma remota.

### Qué se debe reconocer en Java
En Java **no se trabaja el correo con clases básicas del JDK** como ocurre con HTTP o DNS. Para correo electrónico se utilizan **librerías específicas**, siendo la más habitual **JavaMail / Jakarta Mail**.

Esto encaja con el enfoque del tema:
- No se reinventan protocolos complejos.
- Se utilizan **bibliotecas ya implementadas**.
- El programador se centra en el uso del servicio, no en su implementación interna.

### Por qué no es JDK puro
- SMTP, POP3 e IMAP son protocolos complejos.
- Implementarlos desde cero con sockets sería una tarea extensa y fuera del alcance del tema.
- El JDK estándar no ofrece clases directas para gestionar correo electrónico.
- Se delega esta funcionalidad en librerías externas especializadas.

### Qué puede aparecer en examen
- Identificar **qué protocolo se usa para cada función**:
  - Enviar correo → SMTP.
  - Descargar correo → POP3.
  - Consultar correo en servidor → IMAP.
- Reconocer que todos siguen un modelo **cliente/servidor**.
- Saber que **no se implementan manualmente**, sino mediante bibliotecas.
- Identificar comandos SMTP mencionados en el temario:
  - **HELO**: apertura de sesión con el servidor.
  - **MAIL FROM**: identificación del emisor del correo.

En este tema, el código asociado al correo electrónico **se interpreta a nivel conceptual**, no se memoriza ni se desarrolla de forma completa.

## 6. Qué te pueden preguntar (lectura e interpretación)

En este apartado no se evalúa la escritura de código completo, sino la **capacidad de interpretar fragmentos**, relacionarlos con el protocolo correcto y explicar su función dentro de la comunicación en red.

Preguntas y enfoques habituales de examen:

### Identificación de protocolos
- ¿Qué protocolo se encarga de **resolver nombres de dominio**?  
  → **DNS**.
- ¿Qué protocolo permite la **navegación web**?  
  → **HTTP**.
- ¿Qué protocolo se utiliza para la **transferencia de ficheros**?  
  → **FTP**.
- ¿Qué protocolos intervienen en el **correo electrónico**?  
  → **SMTP, POP3, IMAP**.

### Relación protocolo ↔ función
- **SMTP**: envío de correos desde el cliente al servidor.
- **POP3**: descarga de correos al equipo local.
- **IMAP**: consulta y gestión de correos directamente en el servidor.
- **HTTP**: petición–respuesta de recursos identificados por URL.
- **FTP**: transferencia de ficheros entre sistemas remotos.
- **DNS**: traducción entre nombres de dominio y direcciones IP.

### Interpretación de código Java
Se puede pedir reconocer qué está ocurriendo en un fragmento como:
- Uso de `URL` y `openConnection()` → comunicación **HTTP**.
- Uso de `InetAddress.getByName()` → **resolución DNS**.
- Uso de sockets con puertos **21 o 20** → **FTP**.
- Referencias a librerías de correo → **SMTP / POP3 / IMAP**.

### Puertos y conceptos clave
- HTTP → puerto **80**.
- FTP → puerto **21** (control) y **20** (datos).
- SMTP → puerto **25**.
- Importancia de distinguir **canal de control** y **canal de datos** en FTP.
- Reconocer que **HTTP es un protocolo sin estado**.

### Enfoque del examen
- El código **no se memoriza**, se **razona**.
- Se evalúa la comprensión del **modelo cliente/servidor**.
- Se valora saber **qué protocolo usar según el servicio**.
- No se exige implementación avanzada ni uso de arquitecturas complejas.

Este bloque resume exactamente **cómo leer, entender y justificar código y conceptos** relacionados con los protocolos de la capa de aplicación en Programación de Servicios y Procesos.









