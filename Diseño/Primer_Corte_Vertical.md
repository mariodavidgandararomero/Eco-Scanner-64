# Diseño del Primer Corte Vertical (Vertical Slice)

## 1. Ficha Técnica de Recursos Mínimos
Para esta primera escena nuclear, se requiere implementar los siguientes componentes (Assets y Scripts):

* **Modelos 3D:**
  * **Personaje Jugador:** Un robot pequeño y esférico o cilíndrico, estilizado en low-poly.
  * **Terreno Inactivo:** Bloques modulares (Grid) en estilo "wireframe" con materiales translúcidos o líneas grises.
  * **Terreno Activo:** Los mismos bloques modulares pero con texturas vibrantes retro (pasto, piedra, metal pixelado plano).
  * **Coleccionables:** Cristales geométricos rotatorios iluminados.
* **Animaciones y Efectos (VFX):**
  * Animación de personaje de correr/rodar y salto.
  * Animación de "Caída Pesada" (Ground Pound).
  * Shader/VFX de onda expansiva en el suelo (partículas y luz).
  * Transición de material interpolada de "Wireframe" a "Textura a Color".
* **Sistemas/Scripts Básicos:**
  * Controlador de personaje en 3ra persona basado en físicas (inercia sencilla).
  * Sistema de detección de colisión de salto de pulso (ej. Physics.OverlapSphere) para detectar los tiles inactivos.
  * Sistema de elemento de recolección (Triggers).
  * Lógica de sistema de HUD básico (Temporizador y contador de Fragmentos recolectados).

## 2. Plan de la Escena (Escena Nuclear)
**Topología e iteración del Nivel:**
* **Punto A (Inicio):** El jugador comienza en una pequeña plataforma central flotando en un espacio oscuro. El terreno es completamente de líneas wireframe gris.
* **Punto B (La Primera Activación):** El jugador interactúa saltando (ground pound). El suelo se colorea en un radio de metros estandarizado, revelando que detrás de unas líneas opacas hay un cristal oculto.
* **Punto C (El Desafío de Plataformas):** El robot cruza bloques distanciados. Algunas plataformas solo se vuelven sólidas (o identificables) si se pintan con un salto de pulso previo.
* **Punto D (El Meta y Progreso):** Al reunir los primeros "Fragmentos de Textura", se ilumina un portal, antena o monolito central, concluyendo exitosamente la jugabilidad de este corte vertical.

## 3. Descripción de Mecánicas Centrales en Acción
El jugador comenzará entendiendo el movimiento rodante inercial al explorar los límites. Instintivamente (o guiado por una pista natural del diseño visual), probará la caída fuerte y ejecutará el **Salto de Pulso**. Un shader de expansión radial mostrará cómo el área pálida y ambigua se materializa y adquiere color súbitamente.
El jugador notará que pintar el mundo es fundamental, pues es lo único que revela la ubicación de los coleccionables vitales, los **Fragmentos de Textura**. El core loop definitivo de esta escena es: *Moverse y Explorar -> Salto de Pulso -> Identificar Cristal en el entorno coloreado -> Recolectar -> Evaluar nuevas rutas coloreadas*.

Durante la demostración, el HUD mostrará un contador numérico simple y directo (ej. 0/5 Fragmentos) y un temporizador sutil que podrá fomentar el speedrunning natural y dominar el salto para cubrir distancias y áreas eficientemente.
