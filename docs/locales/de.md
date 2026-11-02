| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Julian Vane (`@goooem`)

> Ingenieur für Eingebettete Systeme & Echtzeit-Audio-DSP  
> Ansässig in Göteborg, Schweden · Tätig an der Schnittstelle von Hardware-Registern und analoger Akustik.

```
       [ Analoge Sensoren / Mikrofone ]
                      │
                      ▼
  ┌───────────────────────────────────────┐
  │  Cortex-M7 / SIMD Audio-Signalproz.   │ ──< 1,8 ms deterministische Latenz >──
  └───────────────────────────────────────┘
                      │
                      ▼
      [ Verteilte Telemetrie & Audio ]
```

---

## 🎧 Über Mich

Ich entwickle deterministische Firmware, harte Echtzeit-Audiopipelines und Edge-Sensorknoten. Die meiste Zeit verbringe ich mit der Analyse von Signal-Rausch-Verhältnissen, der Einsparung von Taktzyklen auf ARM NEON-Vektoreinheiten und dem Debuggen von SPI/I2S-Bussen mit Logikanalysatoren.

- 🔭 **Hauptberuf**: Senior Firmware Architect für verteilte akustische Hydrophon-Arrays zur marinen Bioakustik-Forschung.
- ⚙️ **Open Source**: Entwicklung allokationsfreier (Zero-allocation) Audio-DSP-Primitive, Firmware für modulare Synthesizer und jitterarmer Linux-Treiber.
- 🪵 **Arbeitsumgebung**: Arch Linux, Neovim, Saleae Logic, Lötstation und ein Stapel historischer Roland-Servicehandbücher.
- 💬 **Themen**: Allokationsfreie Ringpuffer, Filter-Phasenverzerrungen, Festkomma-Q31-Arithmetik und Eurorack-Schaltungstopologien.

---

## 🛠️ Aktuelle Schwerpunkte & Forschung

- **Sub-Millisekunden-Audiopuffer**: Entwurf sperrenfreier Single-Producer-Single-Consumer (SPSC) Ringpuffer mit garantierten, begrenzten Ausführungszeiten auf asymmetrischen Multicore-SoCs.
- **Ultra-Niedrigenergie-Hydrophon-Arrays**: Bare-Metal-Firmware für solar- und batteriebetriebene Meeresbojen zur Übertragung akustischer Metadaten über schmalbandige Satellitenverbindungen (Iridium SBD).
- **Eingebettete Audiosynthese**: Modernisierung klassischer Wavetable-Synthesealgorithmen mittels SIMD-beschleunigter Interpolation auf aktuellen Mikrocontrollern.

---

## 💻 Werkzeugkette & Laborausstattung

| Kategorie | Primäre Technologien & Messgeräte |
| :--- | :--- |
| **Sprachen** | C++20/23, Rust (no_std + tokio), C (C11 Bare-Metal), Assembler (ARM Cortex-M / Thumb-2), Python |
| **Architekturen** | STM32H7 (Dual-Core ARM Cortex-M7/M4), RP2040/RP2350, ESP32-S3, Nordic nRF5340 |
| **Audio & Protokolle** | I2S, TDM, PDM-Mikrofone, MIDI 2.0, ALSA, PipeWire, MQTT-SN, CANopen |
| **Messtechnik** | Saleae Logic Pro 16, Rigol DS1054Z Oszilloskop, Hakko FX-888D, Audio Precision SYS-2722 |
| **Build & Tooling** | CMake, Meson, Ninja, GNU Arm Embedded Toolchain, GDB, OpenOCD, probe-rs |

---

## 📦 Ausgewählte Open-Source-Projekte

### [poly-phase](https://github.com/goooem/poly-phase)
*Header-only SIMD-beschleunigter polyphaser FIR-Resampler in C++20.*
- Null dynamische Heap-Allokationen nach der Initialisierung.
- Dedizierte Implementierungen für AVX2, ARM NEON sowie portable Fallbacks.
- Lineare Phasenunterdrückung im Sperrbereich > 110 dB über das gesamte hörbare Spektrum.

### [whisper-dsp](https://github.com/goooem/whisper-dsp)
*Bare-Metal DSP-Bibliothek, maßgeschneidert für ARM Cortex-M Mikrocontroller.*
- Kaskadierte Biquad-Filter für Festkommaformate Q15 und Q31.
- Echtzeitfähige gefensterte FFT-Routinen mit deterministischer Zyklenzahl.
- Optimiert für energiebegrenzte akustische Ereigniserkennung am Sensornetz-Rand.

### [seafloor-stream](https://github.com/goooem/seafloor-stream)
*Robuster akustischer Telemetrie-Daemon, geschrieben in sicherem `no_std` Rust.*
- Entwickelt für verlustbehaftete, intermittierende Unterwasser-Akustikmodems und Satelliten-Uplinks.
- Prioritätswarteschlangen-Kompaktierung verhindert Pufferüberläufe bei Verbindungsabbrüchen.
- Vollständige modulare Testumgebung auf simulierter QEMU-Hardware.

### [knob-os](https://github.com/goooem/knob-os)
*Open-Hardware Firmware für haptische Drehregler für Musiker und Sounddesigner.*
- Regelkreis-Rückkopplung magnetischer Encoder mit PID-Geschwindigkeitsglättung.
- Nativer Support für hochauflösenden Property Exchange gemäß USB MIDI 2.0.
- Konfigurierbare Simulation virtueller Rasten, harter Endanschläge und Federungsdämpfung.

---

## 📐 Konstruktionsleitlinien

```
1. Jedes allozierte Byte muss seine Existenz im Arbeitsspeicher rechtfertigen.
2. Jitter ist verheerender als Latenz; Vorhersehbarkeit ist das höchste Gut.
3. Was sich nicht mit Oszilloskop oder perf nachweisen lässt, ist bloße Spekulation.
4. Schaltplan, Quellcode und mechanische Fertigungstoleranzen müssen exakt dieselbe Sprache sprechen.
5. Einfache Schaltungen mit präziser Firmware überdauern überladene Kontrollstrukturen.
```

---

## ☕ Außerhalb des Terminals

Abseits von seriellen Konsolen und JTAG-Steckern:
- Restaurierung von 1970er-Jahre Bandechogeräten und analogen Drum-Computern.
- Befahrung des Schärengartens von Bohuslän im traditionellen Holz-Kajak.
- Röstung äthiopischer und kolumbianischer Lagenkaffees auf einem offenen Wirbelschichtröster.
- Sammlung früher Ambient-Elektronik-Alben und skandinavischer Folk-Schallplatten.

---

## 📬 Kontakt & Koordinaten

- **E-Mail**: `julian@vane-systems.se` (PGP-Schlüssel auf keys.openpgp.org hinterlegt)
- **Matrix**: `@jules:matrix.org`
- **Mastodon**: `@goooem@merveilles.town`
- **Standort**: Göteborg, Västra Götaland, Schweden [57.7089° N, 11.9746° E]
