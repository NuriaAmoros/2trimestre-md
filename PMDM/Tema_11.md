# TEMA 11: Introducción a los videojuegos

## Objetivo del tema
- Definir con precisión qué es un videojuego y cómo se clasifica.
- Identificar los bloques funcionales de la arquitectura global de un videojuego.
- Comprender qué es un motor de videojuego, qué abstrae y qué ventajas aporta.
- Distinguir motores 2D y 3D (dimensiones, elementos técnicos y flujo de renderizado).

## Índice
1. Concepto de videojuego y clasificación por plataformas  
2. Arquitectura global de un videojuego: bloques funcionales  
3. Motores de videojuegos: definición, papel y abstracción del hardware  
4. Ventajas de usar motor vs desarrollo “desde cero”  
5. Motores 2D: capas, sprites y operaciones típicas  
6. Motores 3D: renderizado, geometría (vértices/polígonos), texturas, escena y herramientas  

---

## 1. Concepto de videojuego y clasificación por plataformas
### 1.1. Definición operativa
Un **videojuego** es un **mecanismo electrónico interactivo** que responde a las acciones de uno o varios jugadores para alcanzar **objetivos/misiones**, proporcionando **feedback** a cada acción.

### 1.2. Clasificación por plataforma (sistema de ejecución)
Clasificación por **plataformas** (entorno donde se ejecuta el software):  
- **PC**  
- **Consolas** (PlayStation, Xbox, Nintendo, etc.)  
- **Dispositivos móviles**  
- **Máquinas recreativas**

**Distribución por plataforma**:
- **Multiplataforma**: mismo juego disponible en varias plataformas.
- **Exclusivo**: disponible en una única plataforma.

### 1.3. Clasificación por género (visión funcional)
Clasificaciones destacadas:  
- **Acción**: movimientos y combate rápidos.  
- **Aventura**: historia compleja + progresión + puzles frecuentes.  
- **Lucha**: enfrentamiento contra NPC u otros jugadores.  
- **Plataformas**: desplazamiento/salto sobre plataformas para progresar.  
- **Estrategia**: planificación alta; victoria condicionada por decisiones.  
- **Puzles**: resolución de rompecabezas como núcleo de avance.  
- **Simulación**: tareas del mundo real (vuelo, negocios, etc.).

---

## 2. Arquitectura global de un videojuego: bloques funcionales
La **arquitectura global** se entiende como una construcción por **bloques funcionales**. Elementos clave:  
- **Historia**: hilo conductor, mundo y progresión narrativa de personajes.  
- **Arte conceptual**: aspecto general/visual del juego (dirección artística).  
- **Sonido**: voces, ambiente, efectos y música.  
- **Mecánica de juego**: reglas y funcionamiento general (interacciones, objetivos, estados).  
- **Diseño de programación**: implementación en una máquina/plataforma mediante lenguaje y metodología.

**Idea técnica clave**: este bloque “diseño de programación” fija el **cómo** se materializa la mecánica en software ejecutable (estructura, módulos, orden de desarrollo, decisiones técnicas).

---

## 3. Motores de videojuegos: definición, papel y abstracción del hardware
### 3.1. Tres grandes partes de un videojuego
1. **Código del juego**: lógica del juego (reglas, estados, IA de gameplay, interacción).  
2. **Motor del juego**: capa de soporte y funcionalidad base sobre la que se apoya el juego.  
3. **Recursos**: assets (banda sonora, SFX, imágenes, modelos, etc.).

### 3.2. Qué aporta el motor (abstracción)
El motor proporciona una **abstracción sobre el hardware** del dispositivo, permitiendo programar sin conocer la arquitectura concreta donde se ejecutará el juego.

Implicaciones técnicas directas:
- Reduce dependencia de hardware/plataforma.
- Facilita **multiplataforma** si el motor soporta el target.
- Muchos motores se construyen sobre APIs ya existentes (p. ej., **OpenGL, DirectX, SDL**).

### 3.3. Contexto de uso (2D vs 3D)
- Motores “como tales” surgen en los **años 90**, impulsados por la necesidad de cálculo en **3D**.  
- También se usan en **2D**, siendo normalmente más simples que en 3D.

---

## 4. Ventajas de usar motor vs desarrollo “desde cero”
Ventajas observables (impacto en mantenimiento, equipo y portabilidad):  
- **Migración a otra plataforma**: si el motor soporta la plataforma, suele bastar con **recompilar** el proyecto; sin motor implica revisar código y recursos para adaptaciones.  
- **Incorporación de programadores**: con motor, formación focalizada en el motor; sin motor, explicación completa de arquitectura propia y decisiones internas.  
- **Nuevos efectos/características**: con motor es frecuente que existan herramientas/implementaciones ya disponibles; sin motor exige investigación, implementación y pruebas por plataforma.  
- **Segundas partes/reutilización**: con motor, el código del juego queda separado del motor; sin motor se revisa qué se puede reutilizar y qué no.

Punto de examen: “hacerlo todo desde cero” es posible, pero **no recomendable** por coste/tiempo; un motor ya implementa bases de elementos recurrentes (movimiento, soporte de elementos, etc.).

---

## 5. Motores 2D: capas, sprites y operaciones típicas
### 5.1. Videojuego 2D (dimensiones y movimiento)
- Usa **alto** y **ancho** (sin profundidad).  
- Elementos “planos” se desplazan lateralmente y verticalmente.

### 5.2. Qué facilita un motor 2D
- Dibujo de **figuras geométricas** base (círculos, rectángulos, etc.) sobre las que se apoyan componentes/acciones.  
- Gestión por **capas** (layers): en cada capa se representa una parte del juego (fondo, personaje, enemigos, interactuables, UI).

### 5.3. Sprites (definición y rol)
- **Sprite**: representación visual de elementos del juego (personajes, enemigos, etc.) en las capas.  
- Los sprites reproducen movimientos/animaciones de los elementos.

Operaciones típicas que el motor 2D soporta sobre sprites:
- **Escalado**
- **Rotación**
- **Recorte** (seleccionar fragmento/área a mostrar)

### 5.4. Orden de composición (render en 2D por capas)
Orden típico de dibujado:
1) fondo → 2) personaje jugable → 3) enemigos + mapeado/interactuables → 4) UI (vidas, tiempo, puntuación, etc.).

---

## 6. Motores 3D: renderizado, geometría, texturas y escena
### 6.1. Videojuego 3D (dimensiones)
- Usa **alto, ancho y profundidad**.  
- Permite movimiento con libertad espacial por uso de las tres dimensiones.

### 6.2. Renderizado (transformación 3D → 2D)
- **Renderizado**: procesamiento de imágenes 3D para transformarlas a **imágenes 2D** visualizables (adaptación al ojo humano / pantalla).

### 6.3. Modelado geométrico: vértices y polígonos
- Objetos 3D formados por **vértices** que componen **polígonos**.  
- Más vértices/polígonos ⇒ más realismo, pero mayor coste de procesamiento.

### 6.4. Texturas, luces, cámara y escena
- A los polígonos se les aplican **texturas** para realismo.  
- Con modelos + transformaciones (mover/rotar/escalar) + **luces** + **cámara** se construye una **escena**, que es el videojuego 3D en ejecución.

### 6.5. Diferencia clave frente a 2D
- En 3D no se trabaja “por sprites” como núcleo; se requieren **modelos 3D** creados con herramientas de modelado (ej.: **Blender**).

---

## Preguntas esenciales (5–10) para dominar el tema
1. **¿Cuál es la definición funcional de videojuego y qué elementos deben estar presentes para que lo sea?**  
2. **¿Qué implica clasificar videojuegos por plataforma y qué diferencias técnicas hay entre multiplataforma y exclusivo?**  
3. **¿Cuáles son los bloques funcionales de la arquitectura global y qué aporta cada uno al producto final?**  
4. **¿Cuáles son las tres grandes partes de un videojuego y por qué el motor es clave en el desarrollo?**  
5. **¿Qué significa que un motor abstrae el hardware y qué ventajas aporta en portabilidad y mantenimiento?**  
6. **¿Qué ventajas ofrece un motor frente al desarrollo desde cero?**  
7. **¿Cómo se estructura un motor 2D y qué papel juegan capas y sprites?**  
8. **¿Qué operaciones básicas se realizan sobre sprites en 2D?**  
9. **¿Qué es el renderizado 3D y por qué el número de polígonos afecta al rendimiento?**  
10. **¿Qué elementos componen una escena 3D y en qué se diferencia estructuralmente del 2D?**


---

## Bloque de código clave (Java) para ejercicios de completar
> Objetivo: reflejar lo que el PDF explica como separación **código del juego** vs **motor**, y los conceptos 2D (capas/sprites) y 3D (renderizado/escena) en una estructura mínima típica de examen (rellenar TODO).

```java
import java.util.*;

/**
 * Esqueleto didáctico: separa "código del juego" (Game) del "motor" (Engine).
 * En examen suele pedirse completar métodos (TODO) sin frameworks.
 */
public class GameSkeleton {

    // --- 1) Motor (abstracción): orquesta bucle y renderizado ---
    interface Engine {
        void init();
        void update(double deltaSeconds);
        void render();
        void shutdown();
    }

    // --- 2) Código del juego: reglas/estado del gameplay ---
    static class GameState {
        // TODO: define estados típicos (MENU, PLAYING, PAUSED, GAME_OVER)
        // Sugerencia: enum o constantes.
    }

    // --- 3) 2D: sprite + capas (pipeline por orden de dibujado) ---
    static class Sprite {
        private final String id;
        private int layer; // 0=fondo, 1=player, 2=enemies/map, 3=UI (según el tema)

        public Sprite(String id, int layer) {
            this.id = id;
            this.layer = layer;
        }

        public String getId() { return id; }
        public int getLayer() { return layer; }
        public void setLayer(int layer) { this.layer = layer; }

        // Operaciones típicas en motor 2D: escalar/rotar/recortar
        public void scale(double factor) {
            // TODO: simular escalado (p.ej., guardar factor o aplicar a tamaño)
        }

        public void rotate(double degrees) {
            // TODO: simular rotación
        }

        public void crop(int x, int y, int w, int h) {
            // TODO: simular recorte (sprite sheet / región visible)
        }
    }

    static class LayeredRenderer2D {
        private final List<Sprite> sprites = new ArrayList<>();

        public void add(Sprite s) { sprites.add(s); }

        public void renderByLayer() {
            // TODO: ordenar por layer ASC y "dibujar" en ese orden.
            // Requisito del tema: fondo -> player -> enemigos/mapeado -> UI
        }
    }

    // --- 4) 3D: escena (modelos + cámara + luces) + renderizado ---
    static class Model3D {
        private final int vertices;
        private final int polygons;
        private final boolean hasTexture;

        public Model3D(int vertices, int polygons, boolean hasTexture) {
            this.vertices = vertices;
            this.polygons = polygons;
            this.hasTexture = hasTexture;
        }

        public int getVertices() { return vertices; }
        public int getPolygons() { return polygons; }
        public boolean hasTexture() { return hasTexture; }
    }

    static class Scene3D {
        private final List<Model3D> models = new ArrayList<>();

        public void addModel(Model3D m) { models.add(m); }

        public int totalPolygons() {
            // TODO: devolver suma de polígonos de todos los modelos.
            return 0;
        }

        public void render() {
            // TODO: simular renderizado 3D -> 2D (por ejemplo, imprimir métricas).
            // Clave del tema: renderizado transforma 3D en imagen 2D visualizable.
        }
    }

    // --- 5) Ejemplo de "motor" mínimo que llama a renderers ---
    static class MinimalEngine implements Engine {
        private final LayeredRenderer2D renderer2D = new LayeredRenderer2D();
        private final Scene3D scene3D = new Scene3D();

        @Override public void init() {
            // TODO: cargar recursos (conceptual) y registrar sprites/modelos
            renderer2D.add(new Sprite("background", 0));
            renderer2D.add(new Sprite("player", 1));
            renderer2D.add(new Sprite("enemy_1", 2));
            renderer2D.add(new Sprite("ui_score", 3));

            scene3D.addModel(new Model3D(1200, 800, true));
            scene3D.addModel(new Model3D(600, 400, false));
        }

        @Override public void update(double deltaSeconds) {
            // TODO: aplicar lógica del juego (movimientos/estados) -> "código del juego"
        }

        @Override public void render() {
            // TODO: elegir pipeline 2D o 3D según modo del juego
            renderer2D.renderByLayer();
            scene3D.render();
        }

        @Override public void shutdown() {
            // TODO: liberar recursos
        }
    }

    public static void main(String[] args) {
        Engine engine = new MinimalEngine();
        engine.init();

        // Bucle simplificado (sin tiempo real): típico para ejercicios
        for (int i = 0; i < 3; i++) {
            engine.update(1.0 / 60.0);
            engine.render();
        }

        engine.shutdown();
    }
}

``` 

---

# Glosario — TEMA 11: Introducción a los videojuegos

- **Videojuego**: mecanismo electrónico interactivo que responde a acciones del jugador para cumplir objetivos, proporcionando respuesta (feedback).
- **Plataforma**: sistema/entorno de ejecución del videojuego (PC, consola, móvil, recreativa).
- **Multiplataforma**: videojuego disponible en varias plataformas (mismo producto desplegado en distintos entornos).
- **Exclusivo**: videojuego disponible en una única plataforma.
- **Género**: clasificación del videojuego por tipo de experiencia y mecánicas predominantes (acción, aventura, lucha, plataformas, estrategia, puzles, simulación).
- **Arquitectura global**: organización del videojuego por bloques funcionales (no solo código), que define componentes y responsabilidades del producto.
- **Historia**: hilo narrativo y progresión argumental del juego (personajes, mundo, misiones).
- **Arte conceptual**: diseño del aspecto general (dirección visual/estética) del videojuego.
- **Sonido**: conjunto de elementos sonoros (voces, ambiente, efectos, música) integrados en el juego.
- **Mecánica de juego**: reglas y funcionamiento general que determinan cómo se juega (interacciones, estados, condiciones de victoria/derrota).
- **Diseño de programación**: definición de cómo se implementa la mecánica en software sobre una plataforma concreta, usando un lenguaje y metodología.
- **Código del juego**: parte del software que implementa la lógica propia del gameplay (reglas, estados, comportamiento).
- **Recursos (assets)**: materiales que consume el juego (música, efectos, imágenes, modelos, etc.).
- **Motor de videojuego**: capa de software sobre la que se construye el videojuego; proporciona funcionalidades base y abstrae el hardware.
- **Abstracción del hardware**: aislamiento de los detalles de la arquitectura del dispositivo para programar sin depender del hardware concreto y facilitar portabilidad.
- **API gráfica / multimedia (OpenGL, DirectX, SDL)**: tecnologías base sobre las que se apoyan motores para acceso a capacidades de renderizado y sistema.
- **2D**: representación en dos dimensiones (alto/ancho), sin profundidad; movimiento en plano.
- **3D**: representación en tres dimensiones (alto/ancho/profundidad), con libertad espacial.
- **Capa (layer)**: nivel de composición visual para organizar el orden de dibujado (fondo, personaje, enemigos/mapeado, UI).
- **Sprite**: representación visual 2D de un elemento del juego (personaje, enemigo, objeto), usada en capas y animaciones.
- **Escalado (sprite)**: operación de cambiar el tamaño de un sprite (aumentar/reducir).
- **Rotación (sprite)**: operación de girar un sprite respecto a un eje/centro.
- **Recorte (sprite)**: operación de mostrar solo una región del sprite (por ejemplo, para animación por frames).
- **Renderizado**: proceso por el que una representación 3D se transforma en una imagen 2D visualizable en pantalla.
- **Vértice**: punto de la geometría 3D usado para construir superficies mediante polígonos.
- **Polígono**: superficie formada por varios vértices (unidad básica de un modelo 3D); más polígonos suelen implicar más realismo y mayor coste.
- **Textura**: imagen/material aplicado a polígonos/modelos 3D para aportar detalle visual y realismo.
- **Escena (3D)**: composición completa formada por modelos, transformaciones (mover/rotar/escalar), cámara y luces; lo que se renderiza para mostrar el juego.
- **Herramientas de modelado (Blender)**: software para crear modelos 3D que luego se integran como recursos del juego.


---
# Glosario técnico — Términos de código (TEMA 11)

- **Motor (Engine)**: componente software que gestiona el ciclo de vida del juego (inicialización, actualización, renderizado y cierre) y abstrae el hardware y APIs subyacentes.

- **Game Loop (bucle del juego)**: estructura repetitiva que ejecuta de forma continua las fases `update` (lógica) y `render` (dibujado), manteniendo el juego en ejecución.

- **init()**: método de inicialización donde se cargan recursos, se configuran estados iniciales y se preparan estructuras necesarias antes del bucle principal.

- **update(deltaTime)**: método encargado de actualizar el estado del juego (movimientos, físicas, estados) en función del tiempo transcurrido.

- **render()**: método responsable de dibujar el estado actual del juego en pantalla (2D por capas o escena 3D).

- **shutdown()**: método de cierre para liberar recursos y finalizar correctamente la ejecución del juego.

- **Código del juego (Game Logic)**: parte del programa que implementa reglas, estados, decisiones y comportamiento del gameplay, independiente del motor.

- **Estado del juego (GameState)**: representación de la situación actual del juego (menú, jugando, pausa, fin), normalmente implementada mediante constantes o enumeraciones.

- **Sprite**: objeto gráfico 2D que representa visualmente un elemento del juego; suele incluir información de capa y transformaciones.

- **Layer (capa)**: nivel de prioridad visual usado para ordenar el dibujado de sprites (fondo → personaje → enemigos → interfaz).

- **Renderer 2D**: componente encargado de dibujar sprites en pantalla siguiendo el orden de capas definido.

- **Escalado (scale)**: transformación gráfica que modifica el tamaño de un sprite o modelo.

- **Rotación (rotate)**: transformación gráfica que gira un sprite o modelo alrededor de un eje.

- **Recorte (crop)**: técnica que muestra solo una parte de una imagen o sprite (uso típico en animaciones por frames).

- **Modelo 3D (Model3D)**: representación geométrica de un objeto tridimensional compuesta por vértices y polígonos.

- **Vértices**: puntos en el espacio 3D que definen la forma de un modelo.

- **Polígonos**: superficies formadas por vértices; cuanto mayor es su número, mayor es el detalle visual y el coste computacional.

- **Textura**: imagen aplicada a un modelo 3D para aportar detalle visual sin aumentar excesivamente la geometría.

- **Escena 3D (Scene)**: conjunto de modelos, transformaciones, cámara y luces que forman el mundo 3D renderizado.

- **Renderizado 3D**: proceso de transformar una escena 3D en una imagen 2D visible en pantalla.

- **Delta Time (deltaSeconds)**: tiempo transcurrido entre dos iteraciones del bucle del juego; se usa para que el movimiento sea independiente de la velocidad de ejecución.

- **Abstracción**: principio por el cual el motor oculta detalles técnicos (hardware, APIs gráficas) para simplificar el desarrollo del juego.

- **Interfaz (interface)**: contrato que define métodos que una clase debe implementar, usado para desacoplar motor y lógica del juego.

- **Esqueleto de código**: estructura mínima de clases y métodos que sirve como base para completar un ejercicio o desarrollar un sistema más complejo.

---