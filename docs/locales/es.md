| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Julian Vane (`@julesvane`)

> Ingeniero de Sistemas Embebidos y Procesamiento Digital de Señales de Audio (DSP) en Tiempo Real  
> Con sede en Gotemburgo, Suecia · Operando en el límite entre los registros de hardware y la acústica analógica.

```
       [ Sensores Analógicos / Micrófonos ]
                        │
                        ▼
  ┌───────────────────────────────────────────┐
  │  Motor de Audio Cortex-M7 / SIMD          │ ──< Latencia Determinista de 1.8ms >──
  └───────────────────────────────────────────┘
                        │
                        ▼
       [ Telemetría Distribuida y Audio ]
```

---

## 🎧 Sobre Mí

Diseño firmware determinista, tuberías de audio de tiempo real estricto y nodos de sensores de borde. La mayor parte de mis jornadas transcurren analizando relaciones señal/ruido, exprimiendo ciclos de cálculo a vectores ARM NEON y depurando buses SPI/I2S con analizadores lógicos.

- 🔭 **Ocupación Principal**: Arquitecto Senior de Firmware desarrollando hidrófonos de detección acústica distribuida para bioacústica marina.
- ⚙️ **Código Abierto**: Creación de primitivas DSP de audio con cero asignaciones en memoria dinámica (Zero-alloc), firmware para sintetizadores modulares y controladores de Linux con fluctuación (jitter) mínima.
- 🪵 **Entorno de Trabajo**: Arch Linux, Neovim, Saleae Logic, estación de soldadura y una pila de manuales de servicio vintage de Roland.
- 💬 **Hablemos sobre**: Búferes circulares sin asignación, distorsión de fase en filtros, aritmética de punto fijo Q31 y topología de circuitos Eurorack.

---

## 🛠️ Enfoque Actual e Investigación

- **Búferes de Audio Submilimétricos**: Diseño de búferes circulares de único productor y único consumidor (SPSC) libres de bloqueos que aseguran tiempos de ejecución acotados en SoCs multinúcleo asimétricos.
- **Matrices de Hidrófonos de Muy Bajo Consumo**: Desarrollo de firmware bare-metal para boyas marinas alimentadas por energía solar y baterías que transmiten metadatos acústicos a través de enlaces satelitales de bajo ancho de banda (Iridium SBD).
- **Síntesis de Audio Embebida**: Modernización de algoritmos clásicos de síntesis por tablas de ondas mediante interpolación acelerada por SIMD en microcontroladores modernos.

---

## 💻 Cadena de Herramientas y Banco de Hardware

| Categoría | Tecnologías Principales y Herramientas |
| :--- | :--- |
| **Lenguajes** | C++20/23, Rust (no_std + tokio), C (C11 bare-metal), Ensamblador (ARM Cortex-M / Thumb-2), Python |
| **Arquitecturas** | STM32H7 (Doble núcleo ARM Cortex-M7/M4), RP2040/RP2350, ESP32-S3, Nordic nRF5340 |
| **Audio y Protocolos** | I2S, TDM, micrófonos PDM, MIDI 2.0, ALSA, PipeWire, MQTT-SN, CANopen |
| **Instrumentación** | Saleae Logic Pro 16, Osciloscopio Rigol DS1054Z, Hakko FX-888D, Audio Precision SYS-2722 |
| **Compilación y Depuración** | CMake, Meson, Ninja, GNU Arm Embedded Toolchain, GDB, OpenOCD, probe-rs |

---

## 📦 Proyectos de Código Abierto Destacados

### [poly-phase](https://github.com/julesvane/poly-phase)
*Remuestreador polifásico FIR en C++20 acelerado por SIMD en un único archivo de cabecera.*
- Cero asignaciones en memoria dinámica (heap) en tiempo de ejecución tras la inicialización.
- Implementaciones optimizadas para AVX2, ARM NEON y una alternativa portátil de respaldo.
- Rechazo en banda de atenuación de fase lineal > 110 dB en todo el espectro audible.

### [whisper-dsp](https://github.com/julesvane/whisper-dsp)
*Biblioteca de procesamiento digital de señales bare-metal adaptada a microcontroladores ARM Cortex-M.*
- Cascadas de filtros bicuadráticos (Biquad) en punto fijo Q15 y Q31.
- Rutinas de FFT en tiempo real con ventanas de cálculo y recuento de ciclos de reloj deterministas.
- Optimizado para la detección de eventos acústicos anómalos en nodos de borde con restricciones energéticas.

### [seafloor-stream](https://github.com/julesvane/seafloor-stream)
*Demonio de telemetría acústica de alta resiliencia desarrollado en Rust seguro (`no_std`).*
- Tolera enlaces con pérdidas e intermitencias en módems acústicos submarinos y satélites.
- Compactación en cola de prioridad que previene desbordamientos de búfer durante períodos sin comunicación.
- Banco de pruebas unitarias automatizado y ejecutable sobre hardware simulado en QEMU.

### [knob-os](https://github.com/julesvane/knob-os)
*Firmware de controlador rotativo háptico de hardware abierto para músicos y diseñadores sonoros.*
- Retroalimentación de codificador magnético en bucle cerrado con suavizado de velocidad PID.
- Soporte nativo para el intercambio de propiedades en alta resolución bajo la norma USB MIDI 2.0.
- Simulación configurable de topes virtuales, límites mecánicos y resortes elásticos.

---

## 📐 Credo de Ingeniería

```
1. Cada byte asignado debe justificar rigurosamente su permanencia en memoria.
2. La fluctuación (jitter) es peor que la latencia; la predictibilidad lo es todo.
3. Si un comportamiento no puede medirse con un osciloscopio o perf, es solo una suposición.
4. Los diagramas esquemáticos, el firmware y las tolerancias mecánicas deben contar la misma historia.
5. Circuitos sencillos respaldados por firmware impecable superan a máquinas de estados complejas.
```

---

## ☕ Fuera del Terminal

Cuando me encuentro lejos de terminales serie y cables de depuración:
- Restauración de máquinas de eco de cinta de los años 70 y sintetizadores analógicos de batería.
- Exploración del archipiélago de Bohuslän a bordo de un kayak de madera.
- Tueste de cafés de origen único de Etiopía y Colombia en un tostador de lecho fluido de código abierto.
- Colección de vinilos de música electrónica ambiental pionera y folclore nórdico.

---

## 📬 Contacto y Coordenadas

- **Correo electrónico**: `julian@vane-systems.se` (Clave PGP disponible en keys.openpgp.org)
- **Matrix**: `@jules:matrix.org`
- **Mastodon**: `@julesvane@merveilles.town`
- **Ubicación**: Gotemburgo, Västra Götaland, Suecia [57.7089° N, 11.9746° E]
