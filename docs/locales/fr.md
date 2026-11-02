| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Julian Vane (`@goooem`)

> Ingénieur en Systèmes Embarqués & Traitement Numérique du Signal Audio (DSP) Temps Réel  
> Basé à Göteborg, Suède · À la frontière des registres matériels et de l'acoustique analogique.

```
       [ Capteurs Analogiques / Micros ]
                        │
                        ▼
  ┌───────────────────────────────────────────┐
  │  Moteur Audio Cortex-M7 / SIMD            │ ──< Latence Déterministe de 1,8 ms >──
  └───────────────────────────────────────────┘
                        │
                        ▼
       [ Télémétrie Distribuée & Audio ]
```

---

## 🎧 À Propos

Je conçois des micrologiciels (firmwares) déterministes, des pipelines audio temps réel strict et des nœuds de capteurs en périphérie de réseau (edge). Mon quotidien consiste à analyser les rapports signal sur bruit, optimiser les cycles d'instructions ARM NEON et déboguer les bus SPI/I2S à l'aide d'analyseurs logiques.

- 🔭 **Poste Principal** : Architecte firmware senior développant des hydrophones de détection acoustique distribuée pour la bioacoustique marine.
- ⚙️ **Open Source** : Création de briques de base DSP sans allocation dynamique (zero-allocation), firmwares pour synthétiseurs modulaires et pilotes Linux à très faible gigue (jitter).
- 🪵 **Environnement** : Arch Linux, Neovim, Saleae Logic, station de soudage et pile de manuels de service Roland d'époque.
- 💬 **Discutons de** : Búffers circulaires sans allocation, distorsion de phase des filtres, calculs en virgule fixe Q31 et topologie des circuits Eurorack.

---

## 🛠️ Recherches & Projets en Cours

- **Tampons Audio Sub-milliseconde** : Conception de buffers circulaires non bloquants à producteur unique et consommateur unique (SPSC) garantissant des temps d'exécution stricts sur SoCs multicœurs asymétriques.
- **Réseaux d'Hydrophones à Ultra-Basse Consommation** : Développement de micrologiciels bare-metal pour bouées marines solaires/batteries transmettant des métadonnées acoustiques par liaison satellite à faible débit (Iridium SBD).
- **Synthèse Audio Embarquée** : Modernisation d'algorithmes classiques de synthèse par table d'ondes via interpolation accélérée par SIMD sur microcontrôleurs récents.

---

## 💻 Chaîne d'Outils & Équipement Matériel

| Catégorie | Technologies Principales & Outils de Laboratoire |
| :--- | :--- |
| **Langages** | C++20/23, Rust (no_std + tokio), C (C11 bare-metal), Assembleur (ARM Cortex-M / Thumb-2), Python |
| **Architectures** | STM32H7 (Double cœur ARM Cortex-M7/M4), RP2040/RP2350, ESP32-S3, Nordic nRF5340 |
| **Audio & Protocoles** | I2S, TDM, micros PDM, MIDI 2.0, ALSA, PipeWire, MQTT-SN, CANopen |
| **Instrumentation** | Saleae Logic Pro 16, Oscilloscope Rigol DS1054Z, Hakko FX-888D, Audio Precision SYS-2722 |
| **Compilation & Outils** | CMake, Meson, Ninja, GNU Arm Embedded Toolchain, GDB, OpenOCD, probe-rs |

---

## 📦 Projets Open Source Sélectionnés

### [poly-phase](https://github.com/goooem/poly-phase)
*Rééchantillonneur FIR polyphase C++20 en fichier d'en-tête unique, accéléré par SIMD.*
- Aucune allocation dynamique sur le tas (heap) après la phase d'initialisation.
- Prise en charge native d'AVX2, d'ARM NEON et d'une solution de secours portable.
- Atténuation de bande coupée à phase linéaire > 110 dB sur tout le spectre audible.

### [whisper-dsp](https://github.com/goooem/whisper-dsp)
*Bibliothèque bare-metal de traitement numérique du signal pour microcontrôleurs ARM Cortex-M.*
- Cascades de filtres biquadratiques en virgule fixe Q15 et Q31.
- Routines FFT fenêtrées en temps réel avec nombre de cycles d'horloge déterministe.
- Optimisé pour la détection d'anomalies acoustiques sur des équipements aux ressources énergétiques limitées.

### [seafloor-stream](https://github.com/goooem/seafloor-stream)
*Démon de télémétrie acoustique sous-marine résilient écrit en Rust sûr (`no_std`).*
- Conçu pour les modems acoustiques et les liaisons satellites à fort taux de perte de paquets.
- Compaction de file d'attente à priorité évitant tout débordement de tampon lors des interruptions réseau.
- Suite de tests unitaires rigoureuse s'exécutant sur matériel simulé sous QEMU.

### [knob-os](https://github.com/goooem/knob-os)
*Micrologiciel de contrôleur rotatif haptique matériel libre pour musiciens et concepteurs sonores.*
- Retour d'effort sur encodeur magnétique en boucle fermée avec lissage de vélocité PID.
- Prise en charge native de l'échange de propriétés haute résolution de la norme USB MIDI 2.0.
- Simulation paramétrable de crans virtuels, de butées rigides et de rappel élastique.

---

## 📐 Principes d'Ingénierie

```
1. Chaque octet alloué doit justifier rigoureusement sa présence en mémoire.
2. La gigue (jitter) est pire que la latence ; la prévisibilité est la priorité absolue.
3. Si un comportement ne peut être mesuré à l'oscilloscope ou avec perf, ce n'est qu'une supposition.
4. Les schémas électroniques, le micrologiciel et les tolérances mécaniques doivent s'accorder parfaitement.
5. Un circuit épuré doté d'un micrologiciel soigné surpasse toujours les machines à états alambiquées.
```

---

## ☕ Activités Hors Ligne

Loin des consoles séries et des connecteurs de programmation :
- Restauration de chambres d'écho à bande des années 70 et de boîtes à rythmes analogiques.
- Randonnées côtières dans l'archipel du Bohuslän en kayak de mer en bois.
- Torréfaction artisanale de cafés de spécialité d'Éthiopie et de Colombie sur torréfacteur à lit fluidisé libre.
- Collection de vinyles de musique électronique ambient des origines et d'enregistrements folkloriques scandinaves.

---

## 📬 Contact & Coordonnées

- **Courriel** : `julian@vane-systems.se` (Clé PGP disponible sur keys.openpgp.org)
- **Matrix** : `@jules:matrix.org`
- **Mastodon** : `@goooem@merveilles.town`
- **Localisation** : Göteborg, Västra Götaland, Suède [57.7089° N, 11.9746° E]
