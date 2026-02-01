# TEMA 12: Desarrollo de videojuegos (2D y nociones 3D)

## Objetivo del tema
Comprender el **proceso técnico de desarrollo de un videojuego 2D en Android**, identificando los **componentes clave (interfaz, motor, sprites, movimiento, fondo y enemigos)** y asimilando **conceptos esenciales de videojuegos 3D** relevantes para el desarrollo.

---

## Índice
1. Desarrollo de un juego 2D: interfaz y motor  
2. Gestión de sprites y estructura eficiente  
3. Movimiento del personaje y control  
4. Fondo del videojuego (render por capas)  
5. Enemigos y comportamiento básico  
6. Rendimiento y dependencia del dispositivo  
7. Nociones clave de animación y estructura en 3D  
8. Preguntas esenciales del tema  
9. Glosario de términos  
10. Bloque de código clave (estructura base)

---

## 1. Desarrollo de un juego 2D: interfaz y motor
El desarrollo comienza con una **interfaz gráfica** y un **motor básico** que permita ejecutar el bucle del juego.  
En Android, la pantalla de juego se implementa mediante una clase que **hereda de `SurfaceView`**, lo que permite dibujar directamente sobre un lienzo.

**Puntos técnicos clave:**
- `SurfaceView` actúa como **lienzo (Canvas)** de dibujo.
- Se sobrescribe `onDraw(Canvas)` para renderizar los elementos.
- La pantalla se integra como vista en el layout.

El **motor del juego** se implementa como un **hilo (`Thread`)**, responsable del ciclo de ejecución.

**Atributos esenciales del motor:**
- **FPS**: control de frames por segundo.
- **Referencia a la pantalla** (`PantallaVideojuego`).
- **Estado de ejecución** (`running`).
- **Canvas** para el renderizado.
- Control de **pulsaciones** y tiempos entre eventos.


---

## 2. Gestión de sprites y estructura eficiente
Los **sprites** contienen las imágenes y animaciones de los personajes.  
En un desarrollo eficiente **no se utilizan imágenes separadas por movimiento**, sino **una única imagen (spritesheet)** con todos los estados.

**Ventajas del spritesheet único:**
- Menor consumo de memoria.
- Menos carga inicial de recursos.
- Mayor fluidez de ejecución.

**Implicaciones técnicas:**
- Es necesario conocer la **posición exacta** de cada animación dentro del sprite.
- Se recortan fragmentos del sprite en memoria para representar cada frame.

Componentes habituales:
- `enum Direccion` (arriba, abajo, izquierda, derecha).
- Clase `Sprite` con métodos de:
  - Posición aleatoria.
  - Cambio de dirección.
  - Dibujo.
  - Carga del sprite.

 

---

## 3. Movimiento del personaje y control
El movimiento se gestiona desde el **motor**, dentro del método `run()` del hilo:
- Se **bloquea el Canvas** para evitar accesos concurrentes.
- Se solicita a la pantalla que dibuje el sprite.

**Control de entrada:**
- Botones de dirección llaman a métodos de cambio de dirección.
- Botón **pausa** → pausa pantalla → pausa motor.
- Botón **reset** → cambio de sprite si existen varios.

Durante las primeras fases aparece una **estela** visual, que se corrige más adelante limpiando el lienzo.

 

---

## 4. Fondo del videojuego (render por capas)
El fondo es una imagen o color **dibujado antes que los personajes**.

**Tipos de fondo:**
- **Color sólido**.
- **Imagen** preparada previamente.

**Orden de dibujo (crítico):**
1. Fondo  
2. Personajes  
3. Enemigos  
4. UI  

Si el fondo no cubre toda la pantalla:
- Se repite usando `Bitmap` y `BitmapDrawable`.
- Uso de `setBounds`, `setTileModeX`, `setTileModeY`.

 

---

## 5. Enemigos y comportamiento básico
Los enemigos son **sprites adicionales** con:
- Imagen diferente.
- Movimiento **aleatorio**.

Implementación:
- Nuevo objeto `Sprite` para el enemigo.
- Dibujo tras el fondo.
- Carga y lógica en métodos funcionales.

A nivel de código, **personaje y enemigo son intercambiables**, lo que evidencia reutilización de estructura.


---

## 6. Rendimiento y dependencia del dispositivo
El mismo código puede comportarse de forma distinta según el dispositivo:
- CPU.
- Memoria RAM.
- Capacidad gráfica.

**Conclusión técnica:**
- Los videojuegos consumen **muchos recursos**.
- Dispositivos menos potentes → menor fluidez.
- Optimización y pruebas en múltiples dispositivos son necesarias.


---

## 7. Nociones clave de animación y estructura en 3D
El desarrollo 3D añade la **profundidad**, aumentando la complejidad.

**Conceptos fundamentales:**
- **Mundo**: espacio donde ocurre el juego.
- **Sistema de coordenadas 3D**: ejes X, Y, Z.
- **Vectores**: posición exacta de un objeto.
- **Componentes 3D**: vértices, polígonos y mallas.
- **Grafo de escena**: estructura en árbol que organiza todos los elementos.

En 3D no se usan sprites, sino **modelos tridimensionales**.


---

## 8. Preguntas esenciales del tema
1. ¿Por qué `SurfaceView` es adecuada para videojuegos 2D en Android?  
2. ¿Qué responsabilidades tiene el motor del juego y por qué se implementa como hilo?  
3. ¿Por qué es más eficiente usar un único spritesheet que múltiples imágenes?  
4. ¿Qué problemas de rendimiento se evitan con una buena gestión de sprites?  
5. ¿Por qué el orden de dibujado es crítico en el renderizado 2D?  
6. ¿Cómo se gestiona el movimiento del personaje desde el motor?  
7. ¿Por qué dos dispositivos ejecutan el mismo juego con distinto rendimiento?  
8. ¿Qué añade la tercera dimensión al desarrollo de videojuegos?  
9. ¿Qué es un grafo de escena y qué función cumple?  

---




## 09. Bloque de código clave (estructura base)
```java
public class Motor extends Thread {
    private boolean running;
    private PantallaVideojuego pantalla;
    private Canvas canvas;

    @Override
    public void run() {
        while (running) {
            canvas = pantalla.getHolder().lockCanvas();
            if (canvas != null) {
                pantalla.onDraw(canvas);
                pantalla.getHolder().unlockCanvasAndPost(canvas);
            }
        }
    }

    public void pausar() {
        running = false;
    }

    public void reanudar() {
        running = true;
        start();
    }
}


```

---

## Glosario — TEMA 12: Desarrollo de videojuegos (2D y nociones 3D)

---

### 1️⃣ Glosario conceptual — Conceptos generales del videojuego
- **Videojuego**: mecanismo electrónico interactivo que responde a las acciones del jugador para cumplir objetivos, proporcionando feedback.
- **Plataforma**: sistema o entorno donde se ejecuta el videojuego (PC, consola, móvil, recreativa).
- **Multiplataforma**: videojuego disponible en varias plataformas.
- **Exclusivo**: videojuego disponible en una única plataforma.
- **Género**: clasificación del videojuego según el tipo de experiencia y mecánicas predominantes.
- **Arquitectura global**: organización del videojuego por bloques funcionales (historia, arte, sonido, mecánica, programación).
- **Historia**: hilo narrativo y progresión argumental del juego.
- **Arte conceptual**: diseño del aspecto visual y estético del videojuego.
- **Sonido**: conjunto de elementos sonoros integrados en el juego.
- **Mecánica de juego**: reglas e interacciones que determinan cómo se juega.
- **Diseño de programación**: forma en que la mecánica se implementa en software.
- **Código del juego**: lógica propia del gameplay.
- **Recursos (assets)**: materiales usados por el juego (imágenes, sonidos, modelos).
- **Motor de videojuego**: capa de software que soporta el desarrollo y abstrae el hardware.
- **Renderizado**: proceso de dibujar en pantalla el estado del juego.
- **Sprite**: representación visual 2D de un elemento del juego.
- **Spritesheet**: imagen única que contiene múltiples animaciones.
- **Escena**: conjunto de elementos visibles del juego en un momento dado.
- **Grafo de escena**: estructura jerárquica que organiza los elementos de una escena 3D.

---

### 2️⃣ Glosario técnico — Clases y componentes de desarrollo
- **SurfaceView**: vista de Android optimizada para dibujado continuo en videojuegos.
- **Canvas**: superficie sobre la que se dibujan sprites, fondos y elementos gráficos.
- **Motor del juego**: hilo que controla el ciclo de ejecución y renderizado.
- **Thread**: mecanismo de ejecución concurrente usado para el motor.
- **Game loop**: ciclo principal que actualiza la lógica y renderiza el juego.
- **FPS (Frames Per Second)**: número de imágenes renderizadas por segundo.
- **Bitmap**: imagen cargada en memoria para ser dibujada.
- **Frame**: imagen individual dentro de una animación.
- **Dirección**: estado lógico del movimiento de un sprite.
- **Render por capas**: técnica de dibujado ordenado (fondo → sprites → UI).
- **Motor 2D**: conjunto de clases que gestionan lógica y renderizado en dos dimensiones.
- **Vector (3D)**: estructura matemática que define una posición en X, Y, Z.
- **Modelo 3D**: objeto tridimensional formado por vértices y polígonos.

---

### 3️⃣ Glosario técnico — Métodos y responsabilidades de código

#### Métodos del motor del juego
- **run()**: método principal del bucle del juego; ejecuta lógica y renderizado mientras el motor está activo.
- **start()**: inicia el hilo del motor y comienza la ejecución.
- **pause() / pausar()**: detiene temporalmente el bucle del juego.
- **resume() / reanudar()**: reactiva el motor tras una pausa.
- **sleep(ms)**: pausa controlada para regular los FPS.

#### Métodos de renderizado
- **onDraw(Canvas)**: dibuja fondo, sprites, enemigos y UI en cada frame.
- **lockCanvas()**: bloquea el lienzo para dibujar de forma segura.
- **unlockCanvasAndPost(Canvas)**: libera el lienzo y muestra el frame renderizado.

#### Métodos de gestión de sprites
- **draw(Canvas)**: dibuja el sprite en su posición actual.
- **update()**: actualiza estado, posición y animación del sprite.
- **setDirection(Direccion)**: cambia la dirección de movimiento.
- **getX() / getY()**: obtienen la posición del sprite.
- **setX() / setY()**: modifican la posición del sprite.

#### Métodos de animación
- **nextFrame()**: avanza al siguiente frame del spritesheet.
- **resetAnimation()**: reinicia la animación.
- **getFrameRect()**: obtiene el rectángulo del frame a dibujar.

#### Métodos de control del juego
- **onTouchEvent(MotionEvent)**: gestiona la entrada táctil del usuario.
- **setRunning(boolean)**: activa o desactiva el bucle del juego.
- **resetGame()**: restaura el estado inicial del juego.

#### Métodos relacionados con rendimiento
- **calculateFPS()**: calcula los frames por segundo actuales.
- **clearCanvas()**: limpia el lienzo para evitar estelas gráficas.


