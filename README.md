# Proyecto DAM – Ajedrez por niveles contra la IA

Videojuego para móviles Android que reinventa el ajedrez clásico: el jugador supera **niveles con objetivos distintos** contra la máquina, en tableros con obstáculos y con **piezas que tienen nuevas mecánicas de movimiento**.

Proyecto del módulo **0492 – Proyecto de Desarrollo de Aplicaciones Multiplataforma** (CFGS DAM) – **Grupo 6**.

---

## 📋 Descripción

El ajedrez tradicional puede resultar difícil y poco atractivo para jugadores novatos. Este juego mantiene lo mejor del ajedrez, el reto estratégico, y lo organiza en partidas cortas por niveles con ayudas visuales.

**Características principales:**

- Modo único: **jugador contra la IA**.
- Niveles con objetivos variados, por ejemplo llevar el rey a una casilla concreta o dar mate al rey enemigo.
- Tableros con **obstáculos** y piezas con **movimientos nuevos**.
- Tres dificultades de la IA: fácil, media y difícil.
- Ayudas visuales: al seleccionar una pieza se marcan las casillas válidas, hay un tutorial y una pantalla de ayuda.
- Progreso guardado en local (estrellas, niveles superados y ajustes). **No requiere conexión a Internet.**

---

## 🛠️ Tecnologías

| Componente | Tecnología |
|---|---|
| Motor | Unity 6 (6000.4.1f1), plantilla 2D |
| Lenguaje | C# |
| IDE | Visual Studio 2022 |
| Render | Universal Render Pipeline 2D (URP) |
| Entrada | Input System |
| Interfaz | UGUI |
| IA del rival | Algoritmo Minimax (poda alfa-beta como optimización futura) |
| Persistencia | PlayerPrefs + JSON |
| Plataforma | Android 7.0 (API 24) o superior, ARM64 |
| Control de versiones | Git + GitHub |

---

## 🏗️ Arquitectura

Se aplica un patrón **MVC adaptado a Unity**:

- **Modelo:** clases C# puras con el tablero, las piezas, las reglas y los niveles.
- **Vista:** MonoBehaviours que dibujan el tablero, las piezas y las pantallas.
- **Controlador:** `GameManager`, que coordina los turnos, la IA y el guardado del progreso.

---

## 📁 Estructura del repositorio

```
Proyecto-DAM/
├── Assets/                 # Recursos del juego
│   ├── Scenes/             # Escenas (SampleScene)
│   ├── Settings/           # Configuración de URP 2D y plantillas de escena
│   └── InputSystem_Actions.inputactions
├── Packages/               # Dependencias del proyecto (manifest.json)
├── ProjectSettings/        # Configuración del proyecto de Unity
├── .gitignore              # Excluye Library, Temp, Logs, Build, etc.
├── .vsconfig               # Componentes recomendados de Visual Studio
└── Proyecto DAM.slnx       # Solución de Visual Studio
```

---

## ▶️ Cómo abrir y ejecutar el proyecto

### Requisitos

- Windows 10/11 (64 bits) o macOS
- [Unity Hub](https://unity.com/download) con **Unity 6000.4.1f1** y el módulo **Android Build Support** (incluye Android SDK, NDK y OpenJDK)
- Visual Studio 2022 con la carga de trabajo *Desarrollo de juegos con Unity*
- Git

### Pasos

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/acastantrek/Proyecto-DAM.git
   ```
2. En Unity Hub: **Add > Add project from disk** y seleccionar la carpeta clonada.
3. Abrir la escena `Assets/Scenes/SampleScene` y pulsar **Play**.

### Generar el APK para Android

1. **File > Build Profiles** (o *Build Settings*), seleccionar **Android** y pulsar **Switch Platform**.
2. En **Player Settings**, revisar el nombre del paquete, la versión, el *Minimum API Level* (API 24), el backend **IL2CPP** y la arquitectura **ARM64**.
3. Con el móvil conectado por USB y la depuración USB activada, pulsar **Build And Run**, o **Build** para obtener solo el `.apk`.

---

## 🚧 Estado del proyecto

**En desarrollo.** El proyecto base de Unity está creado y configurado. El diseño está definido en los entregables: diagramas de clases, componentes y despliegue, mockups y diagrama de navegación.

**Próximos pasos:**

- [ ] Modelo del tablero, piezas y reglas de movimiento
- [ ] IA del rival con Minimax
- [ ] Pantallas: inicio, mapa de niveles, partida, pausa, ajustes y ayuda
- [ ] Niveles con objetivos y obstáculos
- [ ] Guardado del progreso con PlayerPrefs y JSON
- [ ] Pruebas en dispositivos Android y generación del APK final

---

## 👥 Equipo – Grupo 6

| Integrante | Rol |
|---|---|
| Aarón Sánchez Domínguez | Gestor del proyecto y tester |
| Adrián Castan Ruiz | Desarrollo backend e IA |
| MªJosé Rubio Montesinos | Desarrollo frontend y UX/UI |

Metodología de trabajo: **Scrum**.
