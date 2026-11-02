| [KR 한국어](./docs/locales/ko.md) | [US English](./README.md) | [JP 日本語](./docs/locales/ja.md) | [CN 简体中文](./docs/locales/zh-CN.md) | [ES Español](./docs/locales/es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./docs/locales/fr.md) | [DE Deutsch](./docs/locales/de.md) | [RU Русский](./docs/locales/ru.md) | [SA العربية](./docs/locales/ar.md) | [IN हिन्दी](./docs/locales/hi.md) |

---

# Julian Vane (`@julesvane`)

> Embedded Systems & Real-Time Audio DSP Engineer  
> Based in Gothenburg, Sweden · Operating at the boundary of hardware registers and analog acoustics.

```
       [ Analog Sensors / Mics ]
                   │
                   ▼
  ┌─────────────────────────────────┐
  │  Cortex-M7 / SIMD Audio Engine  │ ──< 1.8ms Deterministic Latency >──
  └─────────────────────────────────┘
                   │
                   ▼
   [ Distributed Telemetry & Audio ]
```

---

## 🎧 About Me

I design deterministic firmware, hard real-time audio pipelines, and edge sensor nodes. Most of my days are spent analyzing signal-to-noise ratios, squeezing cycles out of ARM NEON vectors, and debugging SPI/I2S buses with logic analyzers.

- 🔭 **Day Job**: Senior Firmware Architect developing distributed acoustic sensing hydrophones for marine bioacoustics.
- ⚙️ **Open Source**: Building zero-allocation audio DSP primitives, modular synth firmware, and low-jitter Linux drivers.
- 🪵 **Environment**: Arch Linux, Neovim, Saleae Logic, soldering station, and a stack of vintage Roland service manuals.
- 💬 **Ask me about**: Zero-alloc ring buffers, filter phase distortion, fixed-point Q31 arithmetic, and Eurorack circuit topology.

---

## 🛠️ Current Focus & Research

- **Sub-millisecond Audio Buffers**: Designing lock-free single-producer single-consumer (SPSC) ring buffers that guarantee bounded execution times on asymmetric multi-core SoCs.
- **Low-Power Hydrophone Arrays**: Writing bare-metal firmware for solar/battery-powered marine buoys that stream acoustic metadata over low-bandwidth satellite links (Iridium SBD).
- **Embedded Audio Synthesis**: Modernizing vintage wavetable synthesis algorithms with SIMD-accelerated interpolation on modern microcontrollers.

---

## 💻 Core Toolchain & Hardware Bench

| Category | Primary Technologies & Tools |
| :--- | :--- |
| **Languages** | C++20/23, Rust (no_std + tokio), C (C11 bare-metal), Assembly (ARM Cortex-M / Thumb-2), Python |
| **Architectures** | STM32H7 (Dual-core ARM Cortex-M7/M4), RP2040/RP2350, ESP32-S3, Nordic nRF5340 |
| **Audio & Protocols** | I2S, TDM, PDM microphones, MIDI 2.0, ALSA, PipeWire, MQTT-SN, CANopen |
| **Instrumentation** | Saleae Logic Pro 16, Rigol DS1054Z Oscilloscope, Hakko FX-888D, Audio Precision SYS-2722 |
| **Build & Tooling** | CMake, Meson, Ninja, GNU Arm Embedded Toolchain, GDB, OpenOCD, probe-rs |

---

## 📦 Selected Open Source Projects

### [poly-phase](https://github.com/julesvane/poly-phase)
*Header-only SIMD-accelerated polyphase FIR resampler in C++20.*
- Zero runtime heap allocation after initialization.
- AVX2, ARM NEON, and portable fallback implementations.
- Linear-phase rejection > 110 dB across the audible spectrum.

### [whisper-dsp](https://github.com/julesvane/whisper-dsp)
*Bare-metal digital signal processing library tailored for ARM Cortex-M microcontrollers.*
- Fixed-point Q15 and Q31 biquad filter cascades.
- Real-time windowed FFT routines with deterministic cycle counts.
- Optimized for energy-constrained edge acoustic event detection.

### [seafloor-stream](https://github.com/julesvane/seafloor-stream)
*Resilient acoustic telemetry daemon written in safe `no_std` Rust.*
- Handles lossy, intermittent acoustic modems and satellite uplink channels.
- Priority-queue compaction prevents buffer overflow during communication blackouts.
- Full unit test harness running on QEMU simulated hardware.

### [knob-os](https://github.com/julesvane/knob-os)
*Open-hardware haptic rotary controller firmware for musicians and sound designers.*
- Closed-loop magnetic encoder feedback with PID velocity smoothing.
- Native USB MIDI 2.0 High-Resolution Property Exchange support.
- Configurable virtual detents, end-stops, and spring-back simulations.

---

## 📐 Engineering Creed

```
1. Every allocated byte must justify its residency in memory.
2. Jitter is worse than latency; predictability is everything.
3. If it cannot be inspected with an oscilloscope or perf, it is an assumption.
4. Schematics, code, and mechanical tolerances must tell the same story.
5. Simple circuits with well-crafted firmware outlast complex state machines.
```

---

## ☕ Offline Pursuits

When away from serial terminals and debug headers:
- Restoring 1970s tape echo machines and analog drum synths.
- Exploring the Bohuslän archipelago by wooden kayak.
- Roasting single-origin Ethiopian and Colombian coffees on an open-source fluid-bed roaster.
- Collecting early ambient electronic records and Nordic folk pressings.

---

## 📬 Contact & Coordinates

- **Email**: `julian@vane-systems.se` (PGP key available on keys.openpgp.org)
- **Matrix**: `@jules:matrix.org`
- **Mastodon**: `@julesvane@merveilles.town`
- **Location**: Gothenburg, Västra Götaland, Sweden [57.7089° N, 11.9746° E]
