| [KR 한국어](./ko.md) | [US English](../../README.md) | [JP 日本語](./ja.md) | [CN 简体中文](./zh-CN.md) | [ES Español](./es.md) |
| :---: | :---: | :---: | :---: | :---: |
| [FR Français](./fr.md) | [DE Deutsch](./de.md) | [RU Русский](./ru.md) | [SA العربية](./ar.md) | [IN हिन्दी](./hi.md) |

---

# Julian Vane (`@julesvane`)

> Engenheiro de Sistemas Embarcados e Processamento Digital de Sinais de Áudio (DSP) em Tempo Real  
> Radicado em Gotemburgo, Suécia · Atuando na fronteira entre registradores de hardware e acústica analógica.

```
       [ Sensores Analógicos / Microfones ]
                        │
                        ▼
  ┌───────────────────────────────────────────┐
  │  Motor de Áudio Cortex-M7 / SIMD          │ ──< Latência Determinística de 1,8 ms >──
  └───────────────────────────────────────────┘
                        │
                        ▼
       [ Telemetria Distribuída e Áudio ]
```

---

## 🎧 Sobre Mim

Desenvolvo firmware determinístico, pipelines de áudio em tempo real estrito e nós sensores de borda. Passo grande parte dos meus dias analisando relações sinal-ruído, economizando ciclos em vetores ARM NEON e depurando barramentos SPI/I2S com analisadores lógicos.

- 🔭 **Atuação Principal**: Arquiteto sênior de firmware desenvolvendo hidrofones de sensoriamento acústico distribuído para bioacústica marinha.
- ⚙️ **Código Aberto**: Construção de primitivas DSP de áudio com alocação zero (Zero-allocation), firmware para sintetizadores modulares e drivers Linux com jitter mínimo.
- 🪵 **Ambiente de Trabalho**: Arch Linux, Neovim, Saleae Logic, estação de solda e uma pilha de manuais de serviço vintage da Roland.
- 💬 **Gosto de conversar sobre**: Buffers circulares sem alocação, distorção de fase em filtros, aritmética de ponto fixo Q31 e topologias de circuitos Eurorack.

---

## 🛠️ Pesquisa e Foco Atual

- **Buffers de Áudio Submilissegundo**: Projeto de buffers circulares livres de bloqueio do tipo produtor único e consumidor único (SPSC), garantindo tempos de execução limitados em SoCs multinúcleo assimétricos.
- **Arranjos de Hidrofones de Baixíssimo Consumo**: Escrita de firmware bare-metal para boias oceânicas movidas a energia solar e bateria que transmitem metadados acústicos por canais de satélite de baixa largura de banda (Iridium SBD).
- **Síntese de Áudio Embarcada**: Modernização de algoritmos clássicos de síntese por tabela de ondas (wavetable) com interpolação acelerada por SIMD em microcontroladores modernos.

---

## 💻 Ferramental Principal e Bancada de Hardware

| Categoria | Tecnologias Principais e Equipamentos |
| :--- | :--- |
| **Linguagens** | C++20/23, Rust (no_std + tokio), C (C11 bare-metal), Assembly (ARM Cortex-M / Thumb-2), Python |
| **Arquiteturas** | STM32H7 (Dual-core ARM Cortex-M7/M4), RP2040/RP2350, ESP32-S3, Nordic nRF5340 |
| **Áudio e Protocolos** | I2S, TDM, microfones PDM, MIDI 2.0, ALSA, PipeWire, MQTT-SN, CANopen |
| **Instrumentação** | Saleae Logic Pro 16, Osciloscópio Rigol DS1054Z, Hakko FX-888D, Audio Precision SYS-2722 |
| **Build e Depuração** | CMake, Meson, Ninja, GNU Arm Embedded Toolchain, GDB, OpenOCD, probe-rs |

---

## 📦 Projetos Open Source em Destaque

### [poly-phase](https://github.com/julesvane/poly-phase)
*Reamostrador polifásico FIR em C++20 de cabeçalho único (header-only) acelerado por SIMD.*
- Zero alocações na heap em tempo de execução após a inicialização.
- Implementações otimizadas para AVX2, ARM NEON e fallback portátil.
- Atenuação da banda de rejeição com fase linear > 110 dB em todo o espectro audível.

### [whisper-dsp](https://github.com/julesvane/whisper-dsp)
*Biblioteca bare-metal de processamento digital de sinais para microcontroladores ARM Cortex-M.*
- Cascatas de filtros biquad em ponto fixo Q15 e Q31.
- Rotinas FFT com janelamento em tempo real e contagem determinística de ciclos de clock.
- Otimizada para detecção de anomalias acústicas em dispositivos de borda com severas restrições energéticas.

### [seafloor-stream](https://github.com/julesvane/seafloor-stream)
*Daemon resiliente de telemetria acústica marinha desenvolvido em Rust seguro (`no_std`).*
- Trata links intermitentes e sujeitos a perdas em modems acústicos e satélites.
- Compactação por fila de prioridade para evitar estouro de buffer durante blecautes de comunicação.
- Suíte completa de testes unitários executada diretamente em hardware simulado no QEMU.

### [knob-os](https://github.com/julesvane/knob-os)
*Firmware de hardware aberto para controladores rotativos hápticos voltado a músicos e sound designers.*
- Controle em malha fechada de encoder magnético com suavização de velocidade via PID.
- Suporte nativo ao protocolo de troca de propriedades em alta resolução do padrão USB MIDI 2.0.
- Simulação configurável de batentes virtuais, paradas mecânicas e retorno com amortecimento elástico.

---

## 📐 Princípios de Engenharia

```
1. Todo byte alocado deve justificar sua presença contínua na memória.
2. Jitter é pior do que latência; previsibilidade temporal é o valor absoluto.
3. Se um comportamento não pode ser comprovado no osciloscópio ou pelo perf, é mera suposição.
4. Esquemáticos, código de firmware e tolerâncias mecânicas devem contar a mesma história.
5. Circuitos limpos acompanhados de firmware impecável duram mais que máquinas de estados confusas.
```

---

## ☕ Atividades Fora do Terminal

Longe dos cabos de depuração e interfaces seriais:
- Restauração de ecos de fita magnética dos anos 1970 e baterias eletrônicas analógicas.
- Expedições pelo arquipélago de Bohuslän a bordo de um caiaque de madeira artesanal.
- Torra de cafés de origem única da Etiópia e da Colômbia em um torrador de leito fluidizado aberto.
- Coleção de vinis pioneiros de música eletrônica ambiente e prensagens de música folclórica nórdica.

---

## 📬 Contato e Coordenadas

- **E-mail**: `julian@vane-systems.se` (Chave PGP disponível em keys.openpgp.org)
- **Matrix**: `@jules:matrix.org`
- **Mastodon**: `@julesvane@merveilles.town`
- **Localização**: Gotemburgo, Västra Götaland, Suécia [57.7089° N, 11.9746° L]
