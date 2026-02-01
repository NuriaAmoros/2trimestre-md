# TEMA 14: La criptografía  
**Programación de Servicios y Procesos**

## Objetivo del tema
Comprender el concepto de **criptografía** como pilar de la seguridad de la información, identificando los **procesos de cifrado y descifrado**, los **modelos criptográficos más utilizados (simétrico y asimétrico)** y la aplicación práctica de la criptografía mediante **funciones HASH, firmas digitales y certificados digitales** en el desarrollo de aplicaciones.

## Índice
1. Concepto de criptografía  
2. Aplicaciones de la criptografía  
3. Encriptación de la información  
4. Criptografía de clave privada o simétrica  
5. Criptografía de clave pública o asimétrica  
6. Firma digital y certificados digitales  

---

## 1. Concepto de criptografía
La **criptografía** es la disciplina que se encarga de proteger la información mediante técnicas que permiten **ocultar el contenido de los mensajes**, de forma que solo puedan ser comprendidos por los destinatarios autorizados.

El proceso criptográfico básico consta de las siguientes fases:
1. El emisor genera el **mensaje en texto plano**.
2. Se aplica un **algoritmo de cifrado** junto con una **clave**.
3. El mensaje cifrado se transmite por un canal seguro o no seguro.
4. El receptor aplica el proceso inverso de **descifrado** para recuperar el mensaje original.

Asociado a la criptografía se encuentra el **criptoanálisis**, que estudia la robustez de los sistemas criptográficos y permite mejorar su seguridad frente a ataques.

---

## 2. Aplicaciones de la criptografía
La criptografía tiene aplicaciones directas en múltiples ámbitos tecnológicos:

- **Internet y navegación web segura**:  
  Los sitios web que utilizan HTTPS cifran los datos intercambiados entre cliente y servidor mediante algoritmos criptográficos.
- **Sistemas financieros y pagos electrónicos**:  
  Plataformas como banca online o sistemas de pago virtual utilizan criptografía para proteger transacciones.
- **Blockchain y criptomonedas**:  
  Emplean funciones HASH y criptografía de clave pública para garantizar la integridad y autenticidad de las transacciones.
- **Protección de datos en aplicaciones**:  
  Contraseñas y datos sensibles se almacenan cifrados para evitar accesos no autorizados.

En la práctica diaria, la criptografía es invisible para el usuario, pero fundamental para la seguridad de la información.

---

## 3. Encriptación de la información
La **encriptación** o **cifrado** es el proceso mediante el cual un mensaje legible se transforma en un texto aparentemente aleatorio para proteger su contenido.

Conceptos fundamentales:
- **Texto plano**: mensaje original sin cifrar.
- **Texto cifrado**: resultado del proceso de cifrado.
- **Algoritmo criptográfico**: procedimiento matemático que transforma el texto plano en texto cifrado.
- **Clave**: dato utilizado por el algoritmo para cifrar y descifrar la información.

El proceso de cifrado puede representarse como:  
**C = Fₖ(M)**  
donde:
- *M* es el mensaje,
- *F* es el algoritmo,
- *K* es la clave,
- *C* es el texto cifrado.

La seguridad del cifrado depende de la robustez del algoritmo y de la gestión adecuada de las claves.

---

## 4. Criptografía de clave privada o simétrica
La **criptografía simétrica** utiliza **una única clave secreta**, compartida por emisor y receptor, para cifrar y descifrar la información.

Características principales:
- La misma clave se usa para cifrar y descifrar.
- Los algoritmos son **rápidos**.
- Adecuada para cifrar grandes volúmenes de datos.
- Garantiza la confidencialidad de la información.

Inconvenientes:
- Problemas en la **distribución segura de la clave**.
- Necesidad de gestionar muchas claves cuando hay múltiples usuarios.

Este modelo fue utilizado históricamente en sistemas como la máquina **Enigma**.

---

## 5. Criptografía de clave pública o asimétrica
La **criptografía asimétrica** utiliza **dos claves diferentes pero relacionadas**:
- **Clave pública**, conocida por cualquiera.
- **Clave privada**, conocida solo por su propietario.

Características principales:
- Lo cifrado con la clave pública solo puede descifrarse con la clave privada correspondiente.
- Resuelve el problema de distribución de claves.
- Permite identificar al emisor del mensaje.
- Es más lenta que la criptografía simétrica.

Debido a sus ventajas e inconvenientes, en la práctica se utiliza junto con criptografía simétrica en lo que se denomina **criptografía híbrida**.

---

## 6. Firma digital y certificados digitales
La **firma digital** permite garantizar:
- La **identidad del emisor**.
- La **integridad del mensaje**.
- El **no repudio**.

Se basa en:
- Criptografía de clave pública.
- **Funciones HASH**, que generan un resumen único de un mensaje.

Los **certificados digitales** son documentos electrónicos emitidos por una **entidad certificadora**, que garantizan la autenticidad de una clave pública y la identidad de su propietario.

En Java, las funciones HASH se implementan mediante la clase `MessageDigest`, utilizando algoritmos como:
- MD5
- SHA-1
- SHA-256
- SHA-384
- SHA-512

Estos mecanismos permiten aplicar criptografía de forma práctica y segura en aplicaciones reales.

# Glosario — Tema 14: La criptografía  
**Programación de Servicios y Procesos**

## Conceptos generales
- **Criptografía**: Disciplina encargada de proteger la información mediante técnicas de cifrado que impiden el acceso a personas no autorizadas.
- **Criptoanálisis**: Estudio de los sistemas criptográficos con el objetivo de encontrar debilidades y evaluar su seguridad.
- **Seguridad de la información**: Conjunto de técnicas destinadas a garantizar la confidencialidad, integridad y autenticidad de los datos.

## Cifrado y descifrado
- **Cifrado (encriptación)**: Proceso que transforma un mensaje legible en un texto cifrado mediante un algoritmo y una clave.
- **Descifrado (desencriptación)**: Proceso inverso al cifrado que permite recuperar el mensaje original.
- **Texto plano**: Información original antes de aplicar el cifrado.
- **Texto cifrado**: Resultado del proceso de cifrado; información ilegible sin la clave adecuada.
- **Algoritmo criptográfico**: Procedimiento matemático utilizado para cifrar y descifrar información.
- **Clave criptográfica**: Dato secreto utilizado por un algoritmo para realizar el cifrado o descifrado.

## Criptografía simétrica
- **Criptografía simétrica**: Sistema de cifrado que utiliza una única clave compartida para cifrar y descifrar la información.
- **Clave secreta**: Clave que debe mantenerse confidencial y ser conocida solo por los participantes en la comunicación.
- **Distribución de claves**: Problema de seguridad derivado de compartir la clave secreta entre emisor y receptor.
- **Enigma**: Máquina histórica que utilizaba criptografía simétrica para cifrar mensajes.

## Criptografía asimétrica
- **Criptografía asimétrica**: Sistema de cifrado que utiliza un par de claves relacionadas matemáticamente.
- **Clave pública**: Clave que puede ser compartida libremente y se usa para cifrar información o verificar firmas.
- **Clave privada**: Clave secreta asociada a la clave pública, utilizada para descifrar información o firmar digitalmente.
- **Criptografía híbrida**: Uso combinado de criptografía simétrica y asimétrica para aprovechar las ventajas de ambos sistemas.

## Funciones HASH
- **Función HASH**: Función matemática que genera un resumen de tamaño fijo a partir de un mensaje de cualquier longitud.
- **Resumen criptográfico**: Resultado de aplicar una función HASH a un mensaje.
- **Colisión**: Situación en la que dos mensajes distintos generan el mismo valor HASH.
- **Integridad**: Propiedad que garantiza que un mensaje no ha sido alterado.

## Firma digital
- **Firma digital**: Mecanismo criptográfico que garantiza la autenticidad del emisor, la integridad del mensaje y el no repudio.
- **No repudio**: Imposibilidad de que el emisor niegue haber enviado un mensaje firmado digitalmente.
- **Autenticidad**: Garantía de que el mensaje procede realmente del emisor indicado.

## Certificados digitales
- **Certificado digital**: Documento electrónico que vincula una identidad con una clave pública.
- **Entidad certificadora (CA)**: Organismo de confianza que emite certificados digitales y verifica identidades.
- **HTTPS**: Protocolo seguro que utiliza criptografía para proteger la comunicación entre cliente y servidor.

## Criptografía en Java
- **MessageDigest**: Clase de Java utilizada para generar funciones HASH.
- **MD5**: Algoritmo HASH obsoleto por debilidades de seguridad.
- **SHA-1**: Algoritmo HASH considerado inseguro en la actualidad.
- **SHA-256 / SHA-384 / SHA-512**: Algoritmos HASH seguros y ampliamente utilizados en aplicaciones modernas.

# TEMA 14 — Código (Criptografía)  

## Índice del bloque de código
1. Generación de HASH con `MessageDigest` (SHA-256)  
2. Conversión del HASH a hexadecimal (representación legible)  
3. Comparación de integridad (recalcular y comparar HASH)  
4. Ejemplo de “almacenamiento” de contraseña: HASH + SALT (concepto)  
5. Firma digital (estructura mínima: generar par de claves, firmar y verificar)  
6. Cifrado simétrico AES (estructura mínima)  
7. Cifrado asimétrico RSA (estructura mínima)



## 1. Generación de HASH con `MessageDigest` (SHA-256)

La **función HASH** permite obtener un **resumen criptográfico** de un mensaje.  
Este resumen:
- Tiene **longitud fija**.
- Cambia completamente si el mensaje cambia.
- No permite recuperar el mensaje original.

En Java se implementa mediante la clase **`MessageDigest`**.

### Ejemplo básico de generación de HASH (SHA-256)

```java
import java.security.MessageDigest;

public class HashSHA256 {

    public static void main(String[] args) {
        try {
            String mensaje = "Texto a proteger";

            MessageDigest md = MessageDigest.getInstance("SHA-256");
            byte[] hash = md.digest(mensaje.getBytes());

            System.out.println("HASH generado");

        } catch (Exception e) {
            System.out.println("Error al generar HASH");
        }
    }
}

```
## 2. Conversión del HASH a hexadecimal (representación legible)

El resultado de una función HASH en Java es un **array de bytes**, que no es legible directamente.  
Para poder **mostrarlo, almacenarlo o compararlo**, es habitual convertirlo a **formato hexadecimal**.

### Ejemplo de conversión de HASH a hexadecimal

```java
import java.security.MessageDigest;

public class HashHexadecimal {

    public static void main(String[] args) {
        try {
            String mensaje = "Texto a proteger";

            MessageDigest md = MessageDigest.getInstance("SHA-256");
            byte[] hash = md.digest(mensaje.getBytes());

            StringBuilder hex = new StringBuilder();
            for (byte b : hash) {
                String hexByte = Integer.toHexString(0xff & b);
                if (hexByte.length() == 1) {
                    hex.append('0');
                }
                hex.append(hexByte);
            }

            System.out.println("HASH en hexadecimal: " + hex.toString());

        } catch (Exception e) {
            System.out.println("Error al convertir HASH");
        }
    }
}
```
## 3. Comparación de integridad (recalcular y comparar HASH)

La **verificación de integridad** consiste en comprobar que un mensaje **no ha sido modificado**.  
Para ello se vuelve a calcular su HASH y se **compara** con el HASH original.

### Ejemplo de comprobación de integridad

```java
import java.security.MessageDigest;

public class VerificacionIntegridad {

    public static void main(String[] args) {
        try {
            String mensajeOriginal = "Mensaje original";
            String mensajeRecibido = "Mensaje original";

            MessageDigest md = MessageDigest.getInstance("SHA-256");

            byte[] hashOriginal = md.digest(mensajeOriginal.getBytes());
            byte[] hashRecibido = md.digest(mensajeRecibido.getBytes());

            boolean iguales = MessageDigest.isEqual(hashOriginal, hashRecibido);

            if (iguales) {
                System.out.println("El mensaje es íntegro");
            } else {
                System.out.println("El mensaje ha sido modificado");
            }

        } catch (Exception e) {
            System.out.println("Error en la verificación de integridad");
        }
    }
}
```
## 4. Ejemplo de “almacenamiento” de contraseña: HASH + SALT (concepto)

Para almacenar contraseñas de forma segura **no se deben guardar en texto plano**.  
La práctica correcta es almacenar el **HASH de la contraseña**, junto con un **SALT**.

### Conceptos clave
- **Contraseña**: dato secreto introducido por el usuario.
- **SALT**: valor aleatorio que se añade a la contraseña antes de generar el HASH.
- **HASH + SALT**: evita ataques por tablas arcoíris y contraseñas repetidas.

### Ejemplo conceptual en Java (SHA-256 + SALT)

```java
import java.security.MessageDigest;
import java.security.SecureRandom;

public class PasswordHash {

    public static void main(String[] args) {
        try {
            String password = "miPasswordSegura";

            // Generar SALT aleatorio
            SecureRandom random = new SecureRandom();
            byte[] salt = new byte[16];
            random.nextBytes(salt);

            MessageDigest md = MessageDigest.getInstance("SHA-256");
            md.update(salt); // añadir SALT
            byte[] hashPassword = md.digest(password.getBytes());

            System.out.println("Contraseña protegida con HASH + SALT");

        } catch (Exception e) {
            System.out.println("Error al proteger la contraseña");
        }
    }
}
```
## 5. Firma digital (estructura mínima: generar, firmar y verificar)

La **firma digital** permite garantizar simultáneamente:
- **Autenticidad** del emisor.
- **Integridad** del mensaje.
- **No repudio**.

Se basa en:
- Criptografía **asimétrica** (clave pública / privada).
- Funciones **HASH**.

### Ejemplo básico de firma y verificación en Java

```java
import java.security.KeyPair;
import java.security.KeyPairGenerator;
import java.security.PrivateKey;
import java.security.PublicKey;
import java.security.Signature;

public class FirmaDigital {

    public static void main(String[] args) {
        try {
            // Generar par de claves
            KeyPairGenerator keyGen = KeyPairGenerator.getInstance("RSA");
            keyGen.initialize(2048);
            KeyPair parClaves = keyGen.generateKeyPair();

            PrivateKey clavePrivada = parClaves.getPrivate();
            PublicKey clavePublica = parClaves.getPublic();

            // Mensaje a firmar
            String mensaje = "Mensaje importante";

            // Crear firma digital
            Signature firma = Signature.getInstance("SHA256withRSA");
            firma.initSign(clavePrivada);
            firma.update(mensaje.getBytes());
            byte[] firmaDigital = firma.sign();

            // Verificar firma
            Signature verificador = Signature.getInstance("SHA256withRSA");
            verificador.initVerify(clavePublica);
            verificador.update(mensaje.getBytes());
            boolean valida = verificador.verify(firmaDigital);

            System.out.println("Firma válida: " + valida);

        } catch (Exception e) {
            System.out.println("Error en firma digital");
        }
    }
}
```

## 6. Cifrado simétrico AES (estructura mínima)

El **cifrado simétrico** utiliza **una única clave secreta** para cifrar y descifrar la información.  
AES es el algoritmo simétrico más utilizado por su **rapidez y seguridad**.

### Ejemplo básico de cifrado y descifrado con AES en Java

```java
import javax.crypto.Cipher;
import javax.crypto.KeyGenerator;
import javax.crypto.SecretKey;

public class CifradoAES {

    public static void main(String[] args) {
        try {
            // Generar clave secreta AES
            KeyGenerator keyGen = KeyGenerator.getInstance("AES");
            keyGen.init(128);
            SecretKey clave = keyGen.generateKey();

            // Mensaje a cifrar
            String mensaje = "Mensaje secreto";

            // Cifrado
            Cipher cifrador = Cipher.getInstance("AES");
            cifrador.init(Cipher.ENCRYPT_MODE, clave);
            byte[] mensajeCifrado = cifrador.doFinal(mensaje.getBytes());

            // Descifrado
            Cipher descifrador = Cipher.getInstance("AES");
            descifrador.init(Cipher.DECRYPT_MODE, clave);
            byte[] mensajeDescifrado = descifrador.doFinal(mensajeCifrado);

            System.out.println(new String(mensajeDescifrado));

        } catch (Exception e) {
            System.out.println("Error en cifrado AES");
        }
    }
}
```
## 7. Cifrado asimétrico RSA (estructura mínima)

El **cifrado asimétrico** utiliza un **par de claves**:
- **Clave pública**: se puede compartir.
- **Clave privada**: se mantiene en secreto.

Lo cifrado con una clave **solo puede descifrarse con la otra**.  
RSA es el algoritmo asimétrico más representativo en este tema.

### Ejemplo básico de cifrado y descifrado con RSA en Java

```java
import java.security.KeyPair;
import java.security.KeyPairGenerator;
import java.security.PrivateKey;
import java.security.PublicKey;
import javax.crypto.Cipher;

public class CifradoRSA {

    public static void main(String[] args) {
        try {
            // Generar par de claves RSA
            KeyPairGenerator keyGen = KeyPairGenerator.getInstance("RSA");
            keyGen.initialize(2048);
            KeyPair parClaves = keyGen.generateKeyPair();

            PublicKey clavePublica = parClaves.getPublic();
            PrivateKey clavePrivada = parClaves.getPrivate();

            // Mensaje a cifrar
            String mensaje = "Mensaje confidencial";

            // Cifrado con clave pública
            Cipher cifrador = Cipher.getInstance("RSA");
            cifrador.init(Cipher.ENCRYPT_MODE, clavePublica);
            byte[] mensajeCifrado = cifrador.doFinal(mensaje.getBytes());

            // Descifrado con clave privada
            Cipher descifrador = Cipher.getInstance("RSA");
            descifrador.init(Cipher.DECRYPT_MODE, clavePrivada);
            byte[] mensajeDescifrado = descifrador.doFinal(mensajeCifrado);

            System.out.println(new String(mensajeDescifrado));

        } catch (Exception e) {
            System.out.println("Error en cifrado RSA");
        }
    }
}
```
