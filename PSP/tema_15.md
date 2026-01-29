# TEMA 15: Comunicaciones seguras  
**Programación de Servicios y Procesos**

## Objetivo del tema
Comprender la necesidad de **asegurar las comunicaciones en red**, identificando los **protocolos criptográficos** más utilizados, el funcionamiento de **SSL/TLS**, y la implementación básica de **comunicaciones seguras mediante sockets SSL en Java**, garantizando autenticación, confidencialidad e integridad.

## Índice
1. Protocolos seguros de comunicaciones  
2. SSL/TLS: propiedades y funcionamiento  
3. Encriptación de datos en comunicaciones  
4. Certificados digitales para comunicaciones seguras  
5. Sockets seguros en Java: servidor  
6. Sockets seguros en Java: cliente  

---

## 1. Protocolos seguros de comunicaciones
Las comunicaciones en red pueden ser **interceptadas** y **manipuladas** si no se protegen adecuadamente.  
Al combinar **criptografía** con protocolos de red surgen los **protocolos seguros de comunicación**.

Protocolos más relevantes:
- **SSL (Secure Sockets Layer)**: primer protocolo ampliamente usado para comunicaciones seguras cliente/servidor.
- **TLS (Transport Layer Security)**: evolución de SSL, más robusto y seguro.

Estos protocolos se sitúan **entre la capa de aplicación y la de transporte**, permitiendo cifrar protocolos tradicionales.

Ejemplos de protocolos seguros:
- **HTTPS** = HTTP + SSL/TLS  
- **FTPS** = FTP + SSL/TLS  
- **SSH** = versión segura de Telnet  

---

## 2. SSL/TLS: propiedades y funcionamiento
SSL/TLS proporciona las **propiedades básicas de seguridad**:

- **Autenticación**: verifica la identidad de las partes.
- **Confidencialidad**: los datos viajan cifrados.
- **Integridad**: los datos no pueden ser alterados sin ser detectados.

### Handshake SSL/TLS
Antes de iniciar la comunicación segura se realiza una **negociación**:
1. Selección de algoritmos criptográficos.
2. Autenticación mediante certificados digitales.
3. Generación de claves de sesión.
4. Verificación del canal seguro.
5. Inicio de la comunicación cifrada.

Si la negociación falla, **la comunicación no se establece**.

Algoritmos utilizados:
- Clave simétrica: AES, DES.
- Clave pública: RSA.
- Resúmenes HASH: SHA.
- Certificados digitales.

---

## 3. Encriptación de datos en comunicaciones
Además de usar protocolos seguros, los **datos transmitidos pueden cifrarse adicionalmente**.

En Java, el cifrado se realiza mediante la clase:
- **`Cipher`**

Algoritmo destacado:
- **AES (Advanced Encryption Standard)**  
  - Cifrado por bloques de 128 bits.
  - Claves de 128, 192 o 256 bits.
  - Rápido y seguro.

Este cifrado se puede aplicar **antes de enviar los datos por la red**, añadiendo una capa extra de seguridad.

---

## 4. Certificados digitales para comunicaciones seguras
Los **certificados digitales** permiten identificar de forma fiable a las partes que se comunican.

En Java:
- Se utilizan **almacenes de claves (keystore)** y **almacenes de confianza (truststore)**.
- Los certificados se generan con la herramienta **`keytool`**.

Funciones principales de los certificados:
- Identificar al servidor y/o cliente.
- Permitir el intercambio seguro de claves.
- Evitar ataques de tipo *man-in-the-middle*.

Sin certificados, **no es posible establecer sockets SSL**.

---

## 5. Sockets seguros en Java: servidor
Java permite crear **servidores seguros** mediante:
- `SSLServerSocketFactory`
- `SSLServerSocket`

Aspectos clave:
- El servidor usa su **certificado digital** para identificarse.
- Se configuran propiedades del sistema:
  - `javax.net.ssl.keyStore`
  - `javax.net.ssl.keyStorePassword`
  - `javax.net.ssl.trustStore`
  - `javax.net.ssl.trustStorePassword`

Una vez configurado, el servidor acepta conexiones **cifradas automáticamente**.

El funcionamiento lógico del servidor es el mismo que un servidor TCP, pero con **canal seguro**.

---

## 6. Sockets seguros en Java: cliente
El cliente seguro se implementa mediante:
- `SSLSocketFactory`
- `SSLSocket`

Características:
- El cliente confía en los certificados definidos en su truststore.
- La conexión se establece con el servidor seguro mediante IP y puerto.
- Tras la conexión, el intercambio de datos se realiza igual que con sockets normales.

Limitación importante:
- La configuración SSL afecta **a toda la aplicación Java**.
- Para múltiples certificados se requiere configuración avanzada.

---

## Idea clave para examen
- SSL/TLS **no es un protocolo de aplicación**, es un **protocolo de seguridad**.
- HTTPS, FTPS o SSH existen porque **SSL/TLS cifra protocolos existentes**.
- Los sockets seguros funcionan igual que los normales, pero **con cifrado, autenticación e integridad**.
- La seguridad real se logra combinando:
  - Protocolo seguro (SSL/TLS).
  - Cifrado de datos.
  - Certificados digitales.
# Glosario — Tema 15: Comunicaciones seguras  
**Programación de Servicios y Procesos**

## Conceptos generales
- **Comunicaciones seguras**: Intercambio de información a través de la red garantizando confidencialidad, integridad y autenticación.
- **Canal seguro**: Canal de comunicación cifrado que protege los datos frente a escuchas o modificaciones.
- **Intercepción**: Captura no autorizada de datos durante una comunicación.
- **Man-in-the-middle**: Ataque en el que un tercero intercepta y modifica la comunicación entre dos partes sin que estas lo detecten.

## Protocolos seguros
- **SSL (Secure Sockets Layer)**: Protocolo criptográfico diseñado para asegurar comunicaciones en red; actualmente obsoleto.
- **TLS (Transport Layer Security)**: Evolución de SSL, considerado el estándar actual para comunicaciones seguras.
- **HTTPS**: Protocolo HTTP protegido mediante SSL/TLS.
- **FTPS**: Versión segura del protocolo FTP que utiliza SSL/TLS.
- **SSH**: Protocolo seguro que sustituye a Telnet y permite conexiones remotas cifradas.

## Propiedades de seguridad
- **Autenticación**: Verificación de la identidad de las partes que se comunican.
- **Confidencialidad**: Protección de la información para que solo sea accesible por usuarios autorizados.
- **Integridad**: Garantía de que los datos no han sido modificados durante la transmisión.
- **No repudio**: Imposibilidad de negar la autoría de una comunicación o acción.

## SSL/TLS
- **Handshake SSL/TLS**: Proceso inicial de negociación entre cliente y servidor para establecer una conexión segura.
- **Clave de sesión**: Clave simétrica generada durante el handshake para cifrar la comunicación.
- **Algoritmos criptográficos**: Métodos matemáticos utilizados para cifrar, descifrar y firmar datos.
- **Criptografía híbrida**: Uso combinado de criptografía simétrica y asimétrica en una misma comunicación.

## Certificados digitales
- **Certificado digital**: Documento electrónico que vincula una identidad con una clave pública.
- **Entidad certificadora (CA)**: Organización de confianza que emite y valida certificados digitales.
- **KeyStore**: Almacén que contiene claves privadas y certificados propios de una aplicación Java.
- **TrustStore**: Almacén que contiene certificados de confianza en Java.
- **keytool**: Herramienta de Java para gestionar certificados y almacenes de claves.

## Comunicaciones seguras en Java
- **SSLServerSocket**: Clase Java que permite crear servidores con comunicaciones seguras.
- **SSLSocket**: Clase Java utilizada por el cliente para establecer conexiones seguras.
- **SSLServerSocketFactory**: Fábrica de sockets seguros para servidores.
- **SSLSocketFactory**: Fábrica de sockets seguros para clientes.
- **javax.net.ssl**: Paquete Java que contiene las clases necesarias para implementar SSL/TLS.

## Cifrado de datos
- **Cifrado de datos**: Proceso de transformación de información legible en información cifrada antes de su transmisión.
- **AES**: Algoritmo de cifrado simétrico utilizado habitualmente para proteger datos en comunicaciones seguras.
- **RSA**: Algoritmo de cifrado asimétrico usado para intercambio de claves y autenticación.
- **SHA**: Familia de funciones HASH empleadas para garantizar integridad.

## Claves para examen
- **SSL/TLS no sustituye al protocolo**, lo protege.
- **Sin certificados no hay comunicación segura**.
- **Los sockets seguros funcionan como los normales**, pero con cifrado.
- **HTTPS = HTTP + SSL/TLS**.

# TEMA 15 — Código (Comunicaciones seguras)

## Índice del bloque de código
1. Generación de certificado y almacenes con `keytool` (comandos mínimos)  
2. Configuración SSL en Java (propiedades: `keyStore` y `trustStore`)  
3. Servidor SSL en Java (`SSLServerSocket`)  
4. Cliente SSL en Java (`SSLSocket`)  
5. Flujo típico de examen: qué reconocer y qué te pueden pedir interpretar  

## 1. Generación de certificados y almacenes con `keytool` (comandos mínimos)

Para establecer **comunicaciones seguras SSL/TLS en Java** es obligatorio disponer de **certificados digitales**.  
Estos certificados se gestionan mediante **almacenes** y se crean con la herramienta **`keytool`** (incluida en el JDK).

### Tipos de almacenes
- **KeyStore**  
  Contiene:
  - Clave privada.
  - Certificado propio del servidor.
- **TrustStore**  
  Contiene:
  - Certificados de confianza (CA o certificados de servidores).

---

### 1.1. Crear un KeyStore (servidor)

```bash
keytool -genkeypair \
-alias servidorSSL \
-keyalg RSA \
-keysize 2048 \
-validity 365 \
-keystore servidor.keystore

```

## 2. Configuración SSL en Java (propiedades del sistema)

Antes de crear **sockets SSL**, la aplicación Java debe conocer **dónde están los certificados** y **sus contraseñas**.  
Esto se hace mediante **propiedades del sistema**.

### Propiedades SSL principales

```java
System.setProperty("javax.net.ssl.keyStore", "servidor.keystore");
System.setProperty("javax.net.ssl.keyStorePassword", "password");

System.setProperty("javax.net.ssl.trustStore", "cliente.truststore");
System.setProperty("javax.net.ssl.trustStorePassword", "password");
```

## 3. Servidor SSL en Java (`SSLServerSocket`)

El **servidor SSL** acepta conexiones **cifradas** utilizando certificados definidos en su **KeyStore**.  
El flujo es equivalente a un servidor TCP, pero el canal es **seguro (SSL/TLS)**.

### Ejemplo mínimo de servidor SSL

```java
import javax.net.ssl.SSLServerSocket;
import javax.net.ssl.SSLServerSocketFactory;
import javax.net.ssl.SSLSocket;
import java.io.DataInputStream;
import java.io.DataOutputStream;

public class ServidorSSL {

    private static final int PUERTO = 8443;

    public static void main(String[] args) {
        try {
            // Crear fábrica de sockets SSL
            SSLServerSocketFactory factory =
                    (SSLServerSocketFactory) SSLServerSocketFactory.getDefault();

            // Crear servidor SSL
            SSLServerSocket servidor =
                    (SSLServerSocket) factory.createServerSocket(PUERTO);

            // Aceptar conexión segura
            SSLSocket cliente = (SSLSocket) servidor.accept();

            DataInputStream entrada = new DataInputStream(cliente.getInputStream());
            DataOutputStream salida = new DataOutputStream(cliente.getOutputStream());

            String mensaje = entrada.readUTF();
            salida.writeUTF("Servidor SSL recibió: " + mensaje);

            cliente.close();
            servidor.close();

        } catch (Exception e) {
            System.out.println("Error servidor SSL: " + e.getMessage());
        }
    }
}
```

## 4. Cliente SSL en Java (`SSLSocket`)

El **cliente SSL** se conecta a un servidor seguro utilizando un **TrustStore** que contiene los certificados en los que confía.  
El funcionamiento es equivalente a un cliente TCP, pero el canal está **cifrado y autenticado**.

### Ejemplo mínimo de cliente SSL

```java
import javax.net.ssl.SSLSocket;
import javax.net.ssl.SSLSocketFactory;
import java.io.DataInputStream;
import java.io.DataOutputStream;

public class ClienteSSL {

    private static final String HOST = "localhost";
    private static final int PUERTO = 8443;

    public static void main(String[] args) {
        try {
            // Crear fábrica de sockets SSL
            SSLSocketFactory factory =
                    (SSLSocketFactory) SSLSocketFactory.getDefault();

            // Crear socket SSL y conectar
            SSLSocket socket =
                    (SSLSocket) factory.createSocket(HOST, PUERTO);

            DataOutputStream salida = new DataOutputStream(socket.getOutputStream());
            DataInputStream entrada = new DataInputStream(socket.getInputStream());

            salida.writeUTF("Hola servidor SSL");
            String respuesta = entrada.readUTF();

            System.out.println(respuesta);

            socket.close();

        } catch (Exception e) {
            System.out.println("Error cliente SSL: " + e.getMessage());
        }
    }
}
```

## 5. Flujo típico de examen: qué reconocer y qué te pueden pedir interpretar

En el **Tema 15** no se evalúa montar una infraestructura SSL completa, sino **entender el flujo de una comunicación segura** y **reconocer el papel de cada elemento** dentro del código y la configuración.

### Flujo completo de una comunicación SSL/TLS en Java
1. **Generación de certificados** con `keytool`.
2. El **servidor**:
   - Dispone de un **KeyStore** con su certificado y clave privada.
3. El **cliente**:
   - Dispone de un **TrustStore** con el certificado del servidor.
4. La aplicación Java configura las **propiedades SSL**.
5. Se crea el **servidor SSL (`SSLServerSocket`)**.
6. El cliente crea un **`SSLSocket`**.
7. Se realiza automáticamente el **handshake SSL/TLS**.
8. Comienza la comunicación cifrada usando streams normales.

---

### Qué suelen pedir en examen
- Identificar si un código implementa:
  - Socket normal.
  - Socket seguro (SSL).
- Explicar:
  - Para qué sirve el **KeyStore**.
  - Para qué sirve el **TrustStore**.
- Reconocer:
  - Clases `SSLServerSocket` y `SSLSocket`.
  - Propiedades `javax.net.ssl.*`.
- Explicar qué ocurre si:
  - El certificado no es válido.
  - El cliente no confía en el servidor.
  - No se configura correctamente SSL.

---

### Errores típicos que debes saber detectar
- Intentar usar SSL **sin certificados**.
- Confundir **KeyStore** con **TrustStore**.
- Pensar que SSL cifra el protocolo en lugar del **canal**.
- Creer que hay que cifrar manualmente los datos además del SSL.
- Olvidar que la configuración SSL afecta a **toda la JVM**.

---

### Ideas clave para memorizar
- SSL/TLS **protege la comunicación**, no la aplicación.
- Los sockets seguros funcionan **igual que TCP**, pero cifrados.
- El cifrado y la autenticación son **transparentes** al programador.
- **HTTPS = HTTP + SSL/TLS**.
- Sin certificados, **no hay comunicación segura**.

Con este punto queda **cerrado el bloque de código del Tema 15**  
y, con él, **todo el temario de Programación de Servicios y Procesos** 🎯



