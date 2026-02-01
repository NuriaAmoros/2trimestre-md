# TEMA 10: Servicios en red III (Android)

## Objetivo del tema
Comprender el uso de **servicios de terceros en aplicaciones Android**, en particular los servicios de **Google**, identificando el funcionamiento de **Google Maps**, el uso de **APIs externas**, la necesidad de **registro y credenciales**, y el proceso general para **integrar mapas, marcadores y servicios remotos**, así como los conceptos básicos para la **publicación de aplicaciones en Google Play**.

---

## Índice
1. Servicios de terceros en aplicaciones Android  
2. Google Maps: concepto y características generales  
3. API de Google Maps y claves de acceso  
4. Configuración de Google Maps en un proyecto Android  
5. Visualización de mapas en una aplicación Android  
6. Uso de coordenadas geográficas  
7. Marcadores e interacción con el mapa  
8. Servicios adicionales de Google para aplicaciones móviles  
9. Publicación de aplicaciones en Google Play  

---

## 1. Servicios de terceros en aplicaciones Android

Un **servicio de terceros** es una funcionalidad proporcionada por una empresa externa que puede integrarse en una aplicación sin necesidad de desarrollarla desde cero. En Android, este enfoque es habitual para funcionalidades complejas como mapas, mensajería, análisis de uso o autenticación.

El uso de servicios de terceros permite:
- Reducir el tiempo de desarrollo.
- Aumentar la fiabilidad de la aplicación.
- Delegar la gestión de infraestructuras complejas.
- Cumplir requisitos legales y de seguridad ya implementados por el proveedor.

Google ofrece múltiples servicios integrables en Android mediante APIs oficiales, siendo Google Maps uno de los más utilizados.

---

## 2. Google Maps: concepto y características generales

Google Maps es un servicio de mapas que permite la visualización de información geográfica en tiempo real. Se basa en un sistema de **coordenadas geográficas**, definido por:
- **Latitud**: posición norte o sur respecto al ecuador.
- **Longitud**: posición este u oeste respecto al meridiano de Greenwich.

Entre sus funcionalidades principales destacan:
- Visualización de mapas interactivos.
- Localización de puntos concretos.
- Búsqueda de lugares.
- Representación gráfica del entorno geográfico.

Google permite el uso de Google Maps en aplicaciones Android mediante una API oficial.

---

## 3. API de Google Maps y claves de acceso

Para utilizar Google Maps en una aplicación Android es obligatorio usar la **API de Google Maps**. El acceso a esta API requiere:
- Disponer de una cuenta de Google.
- Crear un proyecto en la consola de desarrolladores.
- Generar una **clave de API (API Key)** asociada a la aplicación.

La clave de API:
- Identifica de forma única la aplicación.
- Permite a Google controlar el uso del servicio.
- Está vinculada a políticas de seguridad y uso legal.

Este sistema garantiza un uso responsable de los servicios y protege tanto al proveedor como al desarrollador.

---

## 4. Configuración de Google Maps en un proyecto Android

Una vez creada la clave de API, es necesario configurar el proyecto Android para poder usar Google Maps. Esta configuración incluye:
- Instalar los servicios necesarios de Google Play.
- Añadir las dependencias correspondientes al proyecto.
- Declarar información específica en el archivo de configuración de la aplicación.

Esta fase es crítica, ya que una configuración incorrecta impide la visualización del mapa aunque la clave de API sea válida.

---

## 5. Visualización de mapas en una aplicación Android

Para mostrar un mapa en una aplicación Android se utiliza un componente especializado integrado en la interfaz de usuario. Este componente:
- Se incrusta en la vista de la actividad.
- Gestiona la carga y renderizado del mapa.
- Permite interactuar con el contenido geográfico.

El mapa no está disponible de forma inmediata; se carga de manera asíncrona y notifica a la aplicación cuando está listo para ser utilizado.

---

## 6. Uso de coordenadas geográficas

La interacción con Google Maps se basa en el uso de **coordenadas geográficas**. Estas coordenadas permiten:
- Situar el mapa en una posición concreta.
- Definir ubicaciones específicas.
- Representar puntos de interés.

Las coordenadas se expresan mediante pares de valores numéricos que identifican una posición exacta en el mapa, lo que permite una localización precisa y repetible.

---

## 7. Marcadores e interacción con el mapa

Los **marcadores** permiten señalar ubicaciones concretas dentro del mapa. Cada marcador:
- Está asociado a una posición geográfica.
- Puede incluir información descriptiva.
- Permite interacción por parte del usuario.

Además, el mapa puede responder a acciones del usuario, como pulsaciones sobre la superficie del mapa, lo que permite:
- Obtener la posición seleccionada.
- Añadir marcadores dinámicamente.
- Implementar funcionalidades interactivas basadas en la ubicación.

---

## 8. Servicios adicionales de Google para aplicaciones móviles

Además de Google Maps, Google ofrece otros servicios integrables en aplicaciones Android, como:
- Mensajería en tiempo real.
- Bases de datos en la nube.
- Análisis del uso de la aplicación.
- Servicios de localización avanzada.

Estos servicios amplían las capacidades de las aplicaciones móviles y permiten crear soluciones más completas sin desarrollar infraestructuras propias.

---

## 9. Publicación de aplicaciones en Google Play

Para publicar una aplicación Android es necesario:
- Registrarse como desarrollador en la consola de Google Play.
- Pagar una licencia única de desarrollador.
- Firmar digitalmente la aplicación.
- Subir el paquete de instalación para su revisión.

El proceso de publicación garantiza que las aplicaciones cumplan los requisitos técnicos, legales y de seguridad establecidos por Google antes de estar disponibles para los usuarios finales.


## Código necesario que se debe saber (Tema 10)

En el **Tema 10 (Servicios en red III – Android)** el código **sí forma parte del contenido evaluable**, pero **no a nivel profesional**, sino a nivel **estructural y comprensivo**. No se pide creatividad ni arquitecturas complejas, sino **reconocer, entender y justificar el código mínimo imprescindible** para integrar Google Maps en una app Android.

---

### 1. Declaración de permisos y configuración básica

Es obligatorio comprender que Google Maps **no funciona sin configuración previa**. Conceptualmente debes saber que intervienen:

- Permisos de red.
- Metadatos de configuración.
- Clave de API.

El código asociado **no se memoriza**, pero **sí se identifica** y se sabe explicar:
- Para qué sirve.
- Dónde se declara.
- Qué ocurre si falta.

---

### 2. Uso del componente de mapa en la interfaz

Debes reconocer que:
- El mapa se integra como **componente visual** dentro de una actividad.
- No es un `View` genérico, sino un componente específico de Google Maps.
- El mapa **no está disponible inmediatamente**, sino cuando se notifica que está listo.

Es clave entender el **ciclo de carga del mapa**, no solo su presencia visual.

---

### 3. Inicialización del mapa (evento de disponibilidad)

Concepto obligatorio:
- El mapa se obtiene **cuando Google lo ha cargado completamente**.
- La aplicación recibe una notificación y, a partir de ahí, puede operar sobre el mapa.

Debes saber explicar:
- Por qué no se puede usar el mapa antes.
- Qué papel tiene el método de inicialización.
- Qué tipo de objeto representa el mapa.

---

### 4. Uso de coordenadas geográficas en código

Es imprescindible reconocer el uso de:
- Latitud.
- Longitud.
- Objetos que representan una posición geográfica.

Debes saber:
- Que las coordenadas son valores numéricos.
- Que se usan para centrar el mapa.
- Que se usan para colocar marcadores.

No se evalúa cálculo matemático ni geolocalización avanzada.

---

### 5. Añadir marcadores al mapa

Concepto clave:
- Un marcador es un objeto asociado a una posición.
- Puede incluir información descriptiva.
- Se añade **después** de que el mapa esté disponible.

Debes saber identificar:
- Qué datos mínimos necesita un marcador.
- En qué momento del flujo se añade.
- Qué función cumple a nivel de experiencia de usuario.

---

### 6. Interacción básica con el mapa

Es necesario comprender que el mapa:
- Puede responder a eventos del usuario.
- Permite capturar posiciones seleccionadas.
- Puede modificar su contenido dinámicamente.

No se evalúa lógica compleja, solo:
- La existencia de eventos.
- Su finalidad.
- El uso típico en aplicaciones reales.

---

### Código que **NO** entra en este tema

Queda fuera de alcance:
- Geolocalización en tiempo real.
- Uso del GPS del dispositivo.
- Permisos dinámicos avanzados.
- APIs complejas de rutas o navegación.
- Optimización de rendimiento.
- Arquitecturas MVVM/MVC.

---

### Idea clave para examen y apuntes

> En este tema **el código se reconoce y se explica**, no se diseña.  
> Debes saber **qué piezas existen**, **cómo se relacionan** y **por qué son obligatorias**, especialmente en Google Maps.

Este nivel encaja exactamente con el temario: **integración guiada de servicios de Google en Android**, no desarrollo cartográfico profesional.


## Glosario de términos

**API (Application Programming Interface)**  
Conjunto de reglas y herramientas que permiten a una aplicación comunicarse con un servicio externo, como los servicios de Google, de forma controlada y estandarizada.

**API Key (clave de API)**  
Identificador único asociado a una aplicación que permite autenticar y autorizar el uso de una API de Google, controlando su acceso y consumo.

**Aplicación cliente**  
Aplicación Android que consume servicios externos ofrecidos por terceros, como Google Maps, mediante peticiones a APIs remotas.

**Coordenadas geográficas**  
Sistema de referencia basado en latitud y longitud que permite localizar cualquier punto de la superficie terrestre en un mapa.

**Consola de Google Developers**  
Plataforma web donde los desarrolladores gestionan proyectos, habilitan APIs, generan claves de acceso y controlan el uso de los servicios de Google.

**Google Maps**  
Servicio de mapas proporcionado por Google que permite la visualización e interacción con información geográfica en aplicaciones móviles.

**Google Play Services**  
Conjunto de servicios y librerías proporcionados por Google que permiten a las aplicaciones Android integrar funcionalidades avanzadas como mapas, localización o autenticación.

**Latitud**  
Valor numérico que indica la posición de un punto respecto al ecuador, expresado en grados norte o sur.

**Longitud**  
Valor numérico que indica la posición de un punto respecto al meridiano de Greenwich, expresado en grados este u oeste.

**Mapa interactivo**  
Componente visual que permite al usuario desplazarse, hacer zoom e interactuar con la información geográfica mostrada.

**Marcador (Marker)**  
Elemento gráfico que se coloca sobre un mapa para señalar una ubicación concreta y que puede incluir información adicional.

**Permisos de Android**  
Mecanismo de seguridad que regula el acceso de las aplicaciones a recursos sensibles del sistema, como Internet o la ubicación.

**Publicación en Google Play**  
Proceso mediante el cual una aplicación Android se registra, firma y distribuye oficialmente a través de la tienda Google Play.

**Servicios de terceros**  
Funcionalidades ofrecidas por proveedores externos que se integran en una aplicación sin necesidad de desarrollarlas internamente.

**TLS/SSL**  
Protocolos de seguridad utilizados para cifrar las comunicaciones entre aplicaciones y servicios remotos, garantizando confidencialidad e integridad.

**Visualización de mapas**  
Proceso mediante el cual una aplicación Android representa gráficamente información geográfica usando un servicio como Google Maps.
