# 🌆 Grand Theft Auto: San Andreas - Ultimate Definitive Project (2026)

![Header Banner](https://i.imgur.com/83pZ6yO.jpeg)

Este repositorio es una recopilación técnica de **preservación digital**. No es solo un pack de texturas; es una reconstrucción del motor de GTA:SA para que funcione perfectamente en hardware moderno, restaurando los efectos perdidos de la versión de PlayStation 2 y añadiendo correcciones de alta fidelidad.

---

## 🏗️ Arquitectura del Sistema (Core Files)

Basado en la raíz del directorio, estos son los componentes que mantienen el juego estable:

### ⚙️ Librerías de Inyección y Audio
| Archivo | Función Técnica |
| :--- | :--- |
| `vorbisHooked.dll` | **Esencial.** Engaña al juego para que cargue librerías externas (.asi) al iniciar. |
| `eax.dll` | Restaura el soporte para efectos de sonido ambientales (Eco en túneles, reverberación). |
| `bass.dll` | Librería de audio utilizada por CLEO para reproducir sonidos personalizados en mods. |
| `modloader.asi` | El gestor que permite instalar mods sin tocar el `gta3.img`. |

### 🛑 Sistema Anti-Crash
* **CrashInfo.SA.asi:** Genera un log detallado (`CrashList.txt`) si el juego se cierra. Fundamental para debuggear conflictos entre mods.
* **Open Limit Adjuster:** Elimina el límite de memoria del motor. Evita que los edificios desaparezcan cuando hay muchos mods instalados.

---

## 🎨 Galería de Mejoras Visuales (ModLoader)

![Comparison PS2 vs PC](https://i.imgur.com/XU9M9H8.jpeg)

### 🌓 SkyGfx: El Alma del Proyecto
Este es el mod más importante de tu carpeta. Configurado para emular la **PS2 Rendering Pipeline**:
* **Color Filter:** Restaura el tono anaranjado cálido de Los Santos y el azul frío de San Fierro.
* **Dual Cars:** Reflejos en tiempo real sobre la carrocería de los vehículos.
* **Grass Texture:** Hierba volumétrica que reacciona a la luz.

### 🌃 Project 2DFX & Improved 2DFX
Transforma la atmósfera nocturna. Las luces de la ciudad son visibles desde un extremo del mapa al otro.
> ![LOD Lights](https://i.imgur.com/u5uGv1o.png)
> *Vista aérea de Los Santos con Project 2DFX activado.*

---

## 🛠️ Contenido Detallado del Pack

### 🧥 Personajes y Animaciones
* **Mobile Hands:** Sustituye las manos "de bloque" originales por manos con dedos independientes (basado en la versión móvil).
* **New CJs Girlfriends:** Modelos de alta calidad para las novias de CJ, manteniendo el estilo artístico original.
* **anim:** Carpeta que contiene animaciones fluidas extraídas de la versión de consola.

### 🔫 Combate y Realismo
* **WeaponRecoilAuto:** Añade retroceso físico a las armas. Disparar una AK-47 ahora requiere control del ratón.
* **Original Weapons Fix:** Corrige modelos de armas que estaban al revés o tenían texturas mal mapeadas.

### 🌿 Entorno y Ciudad
* **Missing Lampposts Fix:** Coloca postes de luz en lugares donde Rockstar olvidó ponerlos en la versión de PC.
* **Proper_Vehicles_Retex:** Remapeo de texturas de vehículos para que las ruedas y faros se vean en 1080p/4K.

---

## 📂 Análisis de la Estructura de Archivos

```bash
Directorio Raíz/
├── 📁 CLEO/                  # Scripts de lógica (Selector de coches, misiones extra)
├── 📁 modloader/             # Capa de personalización visual (No destructiva)
│   ├── 📁 SkyGfx/            # Motor de renderizado PS2
│   ├── 📁 Project2DFX/       # Distancia de dibujado de luces
│   └── 📁 Proper_Vehicles/   # Texturas HD de vehículos
├── 📁 data/                  # Manejo de físicas (handling.cfg) y mapa
├── 📄 gta_sa.exe             # Ejecutable v1.0 No-CD (Soporta mods)
└── 📄 stream.ini             # Configurado para usar 2048MB de memoria de video
