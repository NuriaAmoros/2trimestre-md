# TEMA 9: Servicios en red II (Android)

## Objetivo del tema
Comprender cómo se comunican las aplicaciones Android con servidores remotos mediante conexiones HTTP/HTTPS, identificando el modelo cliente/servidor, la gestión de permisos de red y el consumo de servicios web que devuelven datos en formato JSON para su posterior procesamiento en la aplicación.

---

## Índice
1. Conexiones HTTP y HTTPS  
2. Esquema cliente/servidor en aplicaciones Android  
3. Permisos de red en Android  
4. Obtención de datos JSON desde Android vía HTTP/HTTPS  
5. Paso de parámetros en una petición HTTP  
6. Integración Android / JSON / Base de datos remota  

---

## 1. Conexiones HTTP y HTTPS

HTTP (HyperText Transfer Protocol) es el protocolo básico utilizado para la transferencia de información entre un cliente y un servidor en la web. Funciona mediante un modelo de petición–respuesta: el cliente solicita un recurso y el servidor responde con los datos solicitados o con un código de estado.

HTTPS es la versión segura de HTTP. Incorpora una capa de cifrado mediante TLS/SSL que garantiza:
- Confidencialidad de los datos transmitidos.
- Integridad de la información.
- Autenticación del servidor.

En el contexto de Android, el uso de HTTPS es obligatorio por motivos de seguridad. Desde versiones recientes del sistema operativo, las conexiones HTTP sin cifrar están restringidas por defecto, ya que exponen la información del usuario y de la aplicación a ataques de intermediarios.

---

## 2. Esquema cliente/servidor en aplicaciones Android

Las aplicaciones Android actúan habitualmente como **clientes** que consumen servicios ofrecidos por un **servidor remoto**. Este servidor puede estar implementado con distintas tecnologías backend y suele encargarse de:
- Acceder a bases de datos.
- Procesar lógica de negocio.
- Devolver información estructurada al cliente.

El flujo general es el siguiente:
1. La aplicación Android realiza una petición HTTP/HTTPS al servidor.
2. El servidor procesa la solicitud.
3. El servidor devuelve una respuesta, normalmente en formato JSON.
4. La aplicación interpreta los datos recibidos y los utiliza en la interfaz o la lógica interna.

Este modelo permite separar claramente la lógica de presentación (Android) de la lógica de negocio y persistencia (backend), mejorando la escalabilidad y el mantenimiento del sistema.

---

## 3. Permisos de red en Android

Para que una aplicación Android pueda realizar conexiones a Internet, es obligatorio declarar el permiso correspondiente en el archivo `AndroidManifest.xml`.

El permiso principal es:
- `INTERNET`: permite abrir sockets de red y realizar peticiones HTTP/HTTPS.

Sin este permiso, cualquier intento de conexión a un servidor remoto fallará, independientemente de que el código esté correctamente implementado. La gestión de permisos es un aspecto crítico de seguridad en Android y el sistema impide explícitamente el acceso a recursos sensibles si no han sido declarados.

---

## 4. Obtención de datos JSON desde Android vía HTTP/HTTPS

JSON (JavaScript Object Notation) es el formato más habitual para el intercambio de datos entre aplicaciones cliente y servidores web. Se caracteriza por ser:
- Ligero.
- Legible.
- Fácil de procesar.

En Android, el proceso general para obtener datos JSON es:
- Establecer una conexión HTTP/HTTPS con una URL remota.
- Leer la respuesta del servidor.
- Convertir el flujo de datos recibido en una estructura JSON.
- Extraer los valores necesarios para su uso en la aplicación.

El uso de JSON permite desacoplar completamente la aplicación Android de la implementación interna del servidor, siempre que se respete el contrato de datos definido.

---

## 5. Paso de parámetros en una petición HTTP

Las peticiones HTTP pueden incluir parámetros que modifican la respuesta del servidor. Estos parámetros suelen enviarse:
- En la URL (método GET).
- En el cuerpo de la petición (método POST).

El paso de parámetros permite:
- Filtrar datos.
- Enviar identificadores.
- Transmitir información introducida por el usuario.

Desde Android, estos parámetros se construyen antes de realizar la conexión y forman parte esencial de la comunicación cliente/servidor, ya que permiten personalizar la respuesta obtenida según las necesidades de la aplicación.

---

## 6. Integración Android / JSON / Base de datos remota

En una arquitectura completa, la aplicación Android no accede directamente a la base de datos. En su lugar:
- Android se comunica con un servidor mediante HTTP/HTTPS.
- El servidor accede a la base de datos remota.
- El servidor transforma los datos en JSON.
- Android recibe y procesa el JSON.

Este enfoque aporta varias ventajas:
- Mayor seguridad, ya que la base de datos no es accesible directamente.
- Centralización de la lógica de negocio.
- Posibilidad de reutilizar el mismo backend para distintas aplicaciones cliente.

La correcta integración entre Android, servicios web y bases de datos remotas es un pilar fundamental en el desarrollo de aplicaciones móviles modernas.

## ¿Hay código necesario que se deba saber en este tema?

**Sí, pero de forma muy controlada.**  
En el **Tema 9 (Servicios en red II – Android)** no se evalúa la implementación completa ni el dominio de librerías externas, pero **sí es imprescindible reconocer y comprender cierto código básico**, a nivel **conceptual y estructural**, porque forma parte del funcionamiento real de las conexiones en red.

### Código que ES necesario conocer (a nivel de comprensión)

#### 1. Declaración del permiso de red
Es obligatorio saber que **sin este permiso la app no puede conectarse a Internet**, aunque el código esté bien.

- Archivo implicado: `AndroidManifest.xml`
- Concepto clave: permisos de sistema

No se exige memorizar sintaxis avanzada, pero **sí identificar su función y necesidad**.

---

#### 2. Apertura de una conexión HTTP/HTTPS
Es importante **reconocer el flujo básico** de una conexión:

1. Crear una URL.
2. Abrir una conexión.
3. Leer la respuesta del servidor.
4. Cerrar la conexión.

No se pide optimización ni uso de librerías modernas, pero **sí entender qué ocurre en cada paso** y qué papel juega Android como cliente.

---

#### 3. Lectura y tratamiento de JSON
Debes saber:
- Que el servidor devuelve JSON.
- Que Android lo recibe como texto.
- Que ese texto se transforma en objetos JSON.
- Que se accede a los datos mediante claves.

No es necesario memorizar métodos concretos, pero **sí comprender el proceso completo de transformación de datos**.

---

#### 4. Paso de parámetros en peticiones
Es clave distinguir:
- Parámetros enviados por URL (GET).
- Parámetros enviados en el cuerpo (POST).

Y entender **para qué se usan**: filtrar, identificar, personalizar respuestas.

---

### Código que NO es necesario dominar en este tema

- Librerías modernas (Retrofit, Volley, OkHttp).
- Programación asíncrona avanzada.
- Gestión de errores compleja.
- Arquitecturas (MVC, MVVM).
- Seguridad avanzada (tokens, OAuth).

---

### Idea clave para examen y apuntes

> En este tema **el código no se memoriza, se interpreta**.  
> Debes saber **qué hace**, **por qué se usa** y **en qué parte del proceso interviene**, no escribir soluciones completas desde cero.

Esto encaja exactamente con el enfoque del temario: **comprensión del modelo cliente/servidor aplicado a Android**, no desarrollo profesional completo.

## Glosario de términos

**Android**  
Sistema operativo móvil desarrollado por Google basado en el kernel de Linux, orientado principalmente a dispositivos móviles y que utiliza un modelo de aplicaciones cliente que consumen servicios locales o remotos.

**Base de datos remota**  
Sistema de almacenamiento de datos ubicado en un servidor externo al dispositivo Android, accesible a través de un backend y no directamente desde la aplicación cliente.

**Backend**  
Parte del sistema encargada de la lógica de negocio, acceso a bases de datos y procesamiento de peticiones recibidas desde clientes como aplicaciones Android.

**Cliente**  
Aplicación que realiza peticiones a un servidor para solicitar recursos o servicios. En este contexto, una app Android que consume servicios web.

**Cliente/Servidor**  
Modelo de arquitectura en el que un cliente solicita información o servicios a un servidor remoto, que procesa la petición y devuelve una respuesta.

**HTTP (HyperText Transfer Protocol)**  
Protocolo de comunicación utilizado para la transferencia de información en la web mediante un modelo de petición–respuesta entre cliente y servidor.

**HTTPS (HTTP Secure)**  
Versión segura de HTTP que utiliza cifrado TLS/SSL para proteger la confidencialidad e integridad de los datos transmitidos.

**INTERNET (permiso)**  
Permiso de Android que habilita a una aplicación para abrir conexiones de red y comunicarse con servidores remotos mediante HTTP o HTTPS.

**JSON (JavaScript Object Notation)**  
Formato ligero de intercambio de datos basado en texto, estructurado en pares clave–valor y ampliamente utilizado en servicios web.

**Método GET**  
Tipo de petición HTTP que envía los parámetros en la URL y se utiliza habitualmente para solicitar información al servidor.

**Método POST**  
Tipo de petición HTTP que envía los parámetros en el cuerpo de la petición y se emplea para enviar datos al servidor de forma más segura.

**Modelo petición–respuesta**  
Esquema de comunicación en el que el cliente envía una petición al servidor y este devuelve una respuesta con datos o códigos de estado.

**Permisos de Android**  
Mecanismo de seguridad que controla el acceso de las aplicaciones a recursos sensibles del sistema, como la red o el almacenamiento.

**Servidor**  
Sistema remoto que recibe peticiones de los clientes, ejecuta lógica de negocio, accede a bases de datos y devuelve respuestas estructuradas.

**Servicios web**  
Conjunto de servicios accesibles a través de la red que permiten la comunicación entre aplicaciones mediante protocolos como HTTP/HTTPS y formatos como JSON.

**TLS/SSL**  
Protocolos criptográficos utilizados por HTTPS para cifrar las comunicaciones entre cliente y servidor, garantizando seguridad en la transmisión de datos.

