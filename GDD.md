# Ecos de la Fortaleza - Documento de diseño (GDD)

**Hito:** 1 — Concepto  
**Versión del documento:** 0.1  
**Última actualización:** 18/10/2026  
**Estado:** diseño inicial, mucha de la información concretada como el título puede ser cambiada o alterada duarnate el desarrollo.

## 1. Ficha del juego

| | |
|---|---|
| Título | Ecos de la Fortaleza. |
| Autor/a | Alberto Rodríguez Domínguez. |
| Género | Plataformas de acción y exploración con estructura metroidvania. |
| 2D / 3D | 2D, con desplazamiento lateral. |
| Plataformas | Windows. |
| Versión de Unity y pipeline | Unity 6 - URP, plantilla Universal 2D. |
| Público objetivo y PEGI | Jugadores que disfrutan del combate cuerpo a cuerpo, los retos de plataformas y la exploración con desbloqueo de rutas. PEGI 12 orientativo por combate fantástico. |
| Duración de una partida | Objetivo inicial: 15-20 minutos para completar el recorrido principal, sin contar reintentos. |
| Repositorio | [GitHub](https://github.com/albertorodriguezdam/Ecos-de-la-Fortaleza.git) |
| Página de itch.io | Pendiente de crear y añadir el enlace. |

## 2. Concepto

### Resumen

En este juego para un jugador, un aventurero entra en una fortaleza abandonada que ha sido ocupada por monstruos para derrotar al guardián que mantiene activa una antigua maldición. Durante el recorrido consigue doble salto y dash, habilidades que le permiten alcanzar plataformas, superar obstáculos y regresar a zonas conocidas para abrir nuevas rutas.

### Pilares de diseño

1. **Movimiento preciso:** los saltos y desplazamientos deben responder de forma predecible y permitir que el jugador mejore mediante la práctica.
2. **Exploración mediante habilidades:** el jugador encuentra accesos que todavía no puede superar y regresa a ellos después de conseguir una nueva capacidad de movimiento.
3. **Dificultad progresiva:** cada zona introduce un reto y posteriormente lo combina con mecánicas que el jugador ya conoce.
4. **Coherencia del escenario:** toda la fortaleza se construye con un único pack, Critters — Old Castle Tileset, manteniendo un lenguaje visual común.

### Referencias

- **Hollow Knight:** referencia principal para la exploración de espacios conectados, el combate lateral y la progresión mediante habilidades de movimiento.

### Qué lo hace diferente

La propuesta se concentra en explorar una fortaleza compacta cuyos caminos cambian de utilidad al conseguir nuevas habilidades. Su identidad estará en aprovechar la arquitectura del castillo: el doble salto abre recorridos elevados por las murallas y el dash permite cruzar pasos amplios y llegar a la torre final.

Las tres zonas comparten ambientación, pero se diferencian por su distribución, verticalidad, enemigos y obstáculos. Los atajos reducen los desplazamientos repetidos y conectan los nuevos recorridos con el patio de entrada.

El alcance se limita a tres zonas, 2-3 habilidades desbloqueables a mayoes de las iniciales, una selección reducida de enemigos y un jefe final.

## 3. Historia y ambientación

**Premisa**

En un mundo de fantasía medieval, una fortaleza que protegía los caminos de la región quedó abandonada tras un ritual fallido. Una maldición despertó a sus antiguos guardianes y atrajo a otras criaturas, que ahora ocupan sus murallas, galerías y torres.

La maldición permanece vinculada al guardián que habita en la torre principal. Para acabar con ella es necesario atravesar la fortaleza y derrotarlo.

**Protagonista y motivación**

El protagonista es un aventurero armado con una espada que entra en la fortaleza para eliminar la amenaza que se extiende hacia los caminos cercanos. Al principio dispone de movimiento, salto y ataque.

Su nombre y la identidad concreta del jefe final quedan pendientes de definir.

**Espacios y tono**

La ambientación combinará piedra envejecida, estructuras de madera, decoración medieval y zonas ocupadas por monstruos. El tono será de aventura y peligro en un lugar deteriorado, con contraste suficiente para reconocer plataformas, enemigos y trampas.

**Forma de contar la historia**

- Un texto inicial presenta la fortaleza, la maldición y el objetivo del aventurero.
- La decoración y la presencia de enemigos muestran el abandono y la ocupación del lugar.
- Los mensajes al obtener una reliquia explican su habilidad y sugieren cómo utilizarla.
- Un texto final comunica la ruptura de la maldición al derrotar al guardián.

La narración será breve, sin diálogos extensos.

## 4. Jugabilidad

### Objetivo

Explorar las tres zonas conectadas de la fortaleza, obtener doble salto y dash (tercera habilidad a obtener por definir), superar enemigos y trampas y derrotar al guardián de la torre principal.

### Bucle de juego

El jugador explora, supera combates y obstáculos, consigue una habilidad o abre un atajo y utiliza ese progreso para acceder a nuevos recorridos.

Las habilidades se obtienen en puntos concretos del recorrido, no se conceden por cada enemigo derrotado.

### Condiciones de victoria y derrota

- **Victoria:** derrotar al jefe final. Se muestra una pantalla con las opciones de volver a jugar y regresar al menú principal.
- **Derrota:** perder toda la salud. Se muestra una pantalla con las opciones de reintentar desde el último punto de control (o el inicio) y regresar al menú principal.
- **Caída fuera del recorrido:** resta salud y devuelve al jugador a una posición segura. Si agota su salud, activa la derrota.

No habrá límite de tiempo ni un número limitado de reintentos. La persistencia del progreso entre sesiones se decidirá en un hito posterior.

### Progresión

Se proponen tres niveles diferenciados, cada uno en una escena de juego propia y con conexiones que permitan regresar a zonas anteriores:

| Zona provisional | Distribución y retos | Progresión y conexiones |
|---|---|---|
| 1. Patio y murallas | Recorridos principalmente horizontales, saltos sencillos y primeros enemigos terrestres. Enseña el ataque y la lectura de los peligros. | Se obtiene el doble salto tras superar un primer tramo. |
| 2. Galerías interiores | Recorridos verticales, plataformas elevadas, trampas y primeros enemigos voladores o con ataques a distancia. | Se obtiene el dash y se abre un atajo. |
| 3. Torre del guardián | Ascenso con saltos más exigentes, pasos amplios y combinaciones de enemigos y trampas. Termina en la sala del jefe. | Sus retos combinan las habilidades adquiridas. Derrotar al jefe completa la partida. |

## 5. Mecánicas

Los controles de teclado son provisionales. Los parámetros se ajustarán durante el prototipado.

| Mecánica | Descripción | Control | Nivel en el que aparece |
|---|---|---|---|
| Movimiento horizontal | Desplazamiento a izquierda y derecha, el personaje mira en la dirección del movimiento. | A / D o flechas izquierda / derecha. | Zona 1, desde el inicio. |
| Salto | Impulso vertical desde el suelo, con control horizontal en el aire. | Espacio. | Zona 1, desde el inicio. |
| Ataque con espada | Ataque frontal de corto alcance. Solo causa daño durante la parte activa de la animación. | J. | Zona 1, desde el inicio. |
| Doble salto | Permite realizar un segundo salto en el aire después de obtener su reliquia. Se recupera al tocar suelo. | Espacio durante el salto. | Se desbloquea en la zona 1 y permite acceder a la zona 2. |
| Dash | Desplazamiento horizontal breve en la dirección hacia la que mira el personaje. Se puede realizar en suelo o en el aire. | Mayús izquierda. | Se desbloquea en la zona 2 y permite acceder a la zona 3. |
| Obtención de habilidades | Recoger una reliquia activa permanentemente su habilidad durante la partida. | Contacto con la reliquia. | Zonas 1 y 2. |
| Activación de atajos | Desde el otro lado de un acceso bloqueado se habilita un camino de regreso que permanece abierto durante la partida. | Botones de uso de las diferentes habilidades. | Desde la zona 2. |
| Salud y recepción de daño | Los ataques enemigos y las trampas reducen la salud. | Automático al recibir un impacto, trampa o caída fuera del escenario. | Desde el primer peligro de la zona 1. |
| Puntos de control | Guardan el lugar desde el que se reintentará el tramo tras una derrota. | Contacto con el punto de control. | Zonas 1, 2 y 3. |
| Trampas del castillo | Zonas peligrosas representadas con los recursos del pack de escenario. Causan daño por contacto y obligan a elegir una trayectoria segura. | Se superan con movimiento, salto, doble salto o dash. | Se presentan en la zona 1 y se combinan con otros retos en las zonas 2 y 3. |

**Reglas iniciales de funcionamiento**

| Sistema | Regla propuesta para el prototipo |
|---|---|
| Salud del jugador | 5 puntos. Los impactos ordinarios, las trampas y las caídas restan 1 punto. El jefe final restará dos puntos. |
| Daño de la espada | 1 punto por ataque acertado. Un mismo ataque no golpea varias veces al mismo enemigo. En el caso de implementarse un segundo ataque, este generará 2 puntos de daño. |
| Ritmo de ataque | Es necesario terminar un ataque antes de iniciar el siguiente. |
| Invulnerabilidad tras daño | el personaje será invulnerable tras ser atacado, para evitar daños repetidos por un contacto continuado. |
| Doble salto | Un salto adicional por fase aérea. |
| Dash | Solo se permite uno por fase aérea. Aterrizar lo habilita de nuevo. |
| Protección durante el dash | No concede invulnerabilidad ni atraviesa paredes. Desplaza al personaje fuera del peligro, pero atravesar una trampa activa causa daño. |
| Compatibilidad de ataque y dash | No se puede iniciar un dash mientras el ataque esté activo ni atacar durante el dash. |
| Atajos | Una vez abiertos, permanecen accesibles al cambiar de zona o reintentar durante la misma partida. |
| Puntos de control | Activarlos recupera toda la salud. Habrá uno antes del enfrentamiento final. |

## 6. Controles

Pendiente de desarrollar en el hito 2. Los controles de teclado previstos aparecen en el apartado 5, aunque no son definitivos.

| Acción | Teclado | Mando |
|--------|---------|-------|
| | | |

## 7. Niveles

Pendiente de desarrollar. La progresión inicial entre las tres zonas está descrita en el apartado 4.

## 8. Personajes y enemigos

Pendiente de desarrollar. En siguientes hitos se detallarán las características del protagonista, la selección de enemigos, sus comportamientos y el jefe final.

## 9. Interfaz y flujo de pantallas

Pendiente de desarrollar.

## 10. Dirección de arte

El estilo previsto es pixel art de fantasía medieval, con una fortaleza deteriorada formada por murallas de piedra, galerías y torres. El escenario se construirá con Critters — Old Castle Tileset. La legibilidad de plataformas, ataques y peligros tendrá prioridad.

**Pendiente para el hito 4:** concretar la paleta, las tipografías, el tablero de referencias y los ajustes necesarios para mantener la coherencia visual.

## 11. Sonido y música

Pendiente de desarrollar. En futuros hitos se seleccionarán música y efectos de sonido gratuitos con licencias compatibles.

## 12. Efectos visuales y game feel

Pendiente de desarrollar.

## 13. Recursos de terceros

| Recurso | Tipo | Autor | Licencia | Enlace | Dónde se usa |
|---|---|---|---|---|---|
| Critters — Old Castle Tileset | Tiles, fondos, decoración, objetos animados y trampas. | David (chroma_dave), distribuido por Foozle. | CC0. Descarga gratuita con donación opcional. | [Página del recurso](https://foozlecc.itch.io/critters-old-castle) | Único pack de entorno para las tres zonas de la fortaleza. |
| Animated Pixel Adventurer | Sprites y animaciones. | rvros | Licencia propia: permite uso personal/comercial y modificación; prohíbe revender o redistribuir el asset. | [Página del recurso](https://rvros.itch.io/animated-pixel-hero) | Personaje principal. |
| Fire Worm | Sprites y animaciones. | LuizMelo | CC0. | [Página del recurso](https://luizmelo.itch.io/fire-worm) | Candidato a enemigo con ataque de fuego, presencia limitada a los tramos avanzados. |
| Monsters Creatures Fantasy 2 | Pack de sprites y animaciones. | LuizMelo | CC0. | [Página del recurso](https://luizmelo.itch.io/monsters-creatures-fantasy-2) | Selección de enemigos terrestres o voladores. |
| Monsters Creatures Fantasy | Pack de sprites y animaciones. | LuizMelo | CC0. | [Página del recurso](https://luizmelo.itch.io/monsters-creatures-fantasy) | Selección de enemigos básicos. |
| Evil Wizard | Sprites y animaciones. | LuizMelo | CC0. | [Página del recurso](https://luizmelo.itch.io/evil-wizard) | Candidato a enemigo avanzado. |

Se importarán únicamente los elementos que vayan a utilizarse. No se prevé implementar todas las criaturas de los packs disponibles.

**Selecciones pendientes:** recurso gráfico del jefe final, representación de las reliquias y los puntos de control, interfaz, tipografías, música y efectos de sonido. Primero se comprobará qué objetos del pack pueden representar los elementos interactivos previstos. Cualquier recurso adicional se registrará aquí.

## 14. Declaración de uso de IA

| Herramienta | Uso en la preparación de este hito |
|---|---|
| ChatGPT | Organización de requisitos, revisión del GDD, búsqueda de recursos y adaptación a la plantilla. |

## 15. Aspectos técnicos

Pendiente de desarrollar. 

## 16. Diario de desarrollo

### 2026-10-16

- Se ha definido un plataformas-metroidvania 2D con combate y habilidades desbloqueables.
- Se ha reorganizado el documento según la plantilla del profesor y se han señalado las secciones pendientes de hitos posteriores.
- Se han reunido recursos gratuitos para el protagonista y los enemigos.
- Se ha elegido Critters — Old Castle Tileset como referencia y único pack previsto para los escenarios.
- Se ha adaptado la ambientación a una fortaleza abandonada, con patio y murallas, galerías interiores y torre del guardián.

## 17. Pruebas con jugadores

Pendiente de realizar. 

## 18. Postmortem

Pendiente de redactar al finalizar el proyecto.

---



