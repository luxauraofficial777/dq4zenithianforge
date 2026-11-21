<img width="1024" height="1024" alt="image" src="https://github.com/user-attachments/assets/14d12380-3c34-4931-a72d-1b72025a96bc" />

<div align="center">

<img width="1024" height="1024" alt="DQ4 Zenithian Forge Emblem" src="https://github.com/user-attachments/assets/14d12380-3c34-4931-a72d-1b72025a96bc" />

# DRAGON QUEST IV: ZENITHIAN FORGE
### Multi-Generational Localization Suite & Dual-Platform Re-Authoring Engine
**A 25th Anniversary Historical Restoration & Engineering Tribute (2001–2026)**

[![Platform](https://img.shields.io/badge/Platform-PlayStation%201%20%7C%20SNES%20ExHiROM-blue.svg)](#)
[![Target-Binary](https://img.shields.io/badge/Target-SLPM--869.16%20%28HBD1PS1D.Q41%29-indigo.svg)](#)
[![Version](https://img.shields.io/badge/Release-v1.0A--INT-emerald.svg)](#)
[![License](https://img.shields.io/badge/License-CC--BY--NC--SA%204.0-amber.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Architecture-Hardware--Accurate%20In--Place%20Re--Author-crimson.svg)](#)

</div>

---

## 🕊️ Dedication: In Honor of Manabu Yamana & Koichi Nakamura

> *"To forge a world that breathes within the constraints of silicon is the craft of the architect; to imbue it with heart is the gift of the master."*

On November 22, 2001, HeartBeat and Enix released the PlayStation remake of **Dragon Quest IV: Michibikareshi Mono-tachi** (*ドラゴンクエストIV 導かれし者たち*). Directed and programmed under the visionary technical leadership of **Manabu Yamana (山名 学)** and the foundational design direction of Chunsoft founder **Koichi Nakamura (中村 光一)**, the PSX remake was the definitive realization of the Zenithian epic.

Yamana’s proprietary HeartBeat 2.5D engine pushed the PlayStation’s MIPS R3000A CPU and GTE (Geometry Transformation Engine) to their mathematical limits—implementing dynamic tile-plane projection, seamless camera rotations, sophisticated dynamic overlay paging, and an ultra-compact virtual messaging machine.

On this **25th Anniversary**, this repository stands not merely as a complete localization suite, but as a living monument and rigorous IEEE-grade case study of Yamana and Nakamura’s engineering genius.

---

## ⚔️ Project Evolution: From "Frankenstein" to the "Zenithian Forge"

For over two decades, the 2001 PlayStation release of *Dragon Quest IV* remained the only mainline title in the franchise without an authentic, hardware-accurate English home console release. 

### The Historical "Frankenstein" Paradigm (Deprecated)
Early community attempts relied on binary organ-transplants: forcing the North American *Dragon Warrior VII* executable (`SLUS_012.06`) onto the *Dragon Quest IV* disc container. While innovative for its era, this cross-engine grafting caused severe architectural friction:
* **Thread Collisions & CPU Stalls:** Incompatible event-polling routines between the DW7 kernel and DQ4 sub-routines.
* **Heap Fragmentation & Memory Corruptions:** Incoherent buffer allocations crashing real hardware and accurate emulators.
* **Irreconcilable Script Lockups:** Broken camera matrix handlers and coordinate transformation stalls (e.g., the infamous softlock at Auld Well).

### The Zenithian Forge Breakthrough
**DQ4 Zenithian Forge** permanently retires the Frankenstein methodology. Conceived, architected, and engineered by **Lux Aura** under the **VoidWalkers Research Project**, this engine executes a **100% native in-place re-authoring** directly within the original Japanese HeartBeat binary (`SLPM_869.16` / `HBD1PS1D.Q41`).

By reverse-engineering Yamana's internal VM, memory overlays, and DMA sub-block pipelines, Zenithian Forge achieves seamless, hardware-accurate execution across real PlayStation consoles (SCPH-1000 through PSone), ODE hardware (XStation, PSIO), and cycle-accurate emulators (DuckStation, Mednafen).

```
                      +---------------------------------------+
                      |       Original Japanese Binary        |
                      |     SLPM_869.16 (HBD1PS1D.Q41)        |
                      +---------------------------------------+
                                          |
                        [ Low-Level MIPS Decompilation ]
                                          |
                      +---------------------------------------+
                      |        Yamana HeartBeat Engine        |
                      |  - Dynamic Overlay Allocation Manager |
                      |  - 16-Bit Script Bytecode VM          |
                      |  - V-RAM Sub-Block Plane Compositor   |
                      +---------------------------------------+
                                          |
                               [ In-Place Re-Author ]
                                          v
                      +---------------------------------------+
                      |      Zenithian Forge Suite v1.0A      |
                      |  - Hardware-True VWF Font Pipeline    |
                      |  - Zero Engine-Swap Thread Stability  |
                      |  - Unaltered 2.5D Camera Matrix Logic |
                      |  - 9-Language Localization Target     |
                      +---------------------------------------+
```

---

## 🧬 Architectural Documentation & Disassembly Index

This repository houses complete whitepapers, hardware register maps, and reverse-engineering logs documenting the internals of the HeartBeat Engine (`HBE`):

| Technical Dossier | Focus Area / Subsystem |
| :--- | :--- |
| [`CASE_STUDY_NAKAMURA_YAMANA_HEARTBEAT_ENGINE_IEEE_2026.md`](./CASE_STUDY_NAKAMURA_YAMANA_HEARTBEAT_ENGINE_IEEE_2026.md) | Comprehensive IEEE / SIGGRAPH formal case study on engine design and memory geometry. |
| [`NAKAMURA_YAMANA_FORMAL_STUDY.md`](./NAKAMURA_YAMANA_FORMAL_STUDY.md) | Historical context and technical lineage between Chunsoft, HeartBeat, and Enix. |
| [`YAMANA_HBE_HBD_ARCHITECTURE.md`](./YAMANA_HBE_HBD_ARCHITECTURE.md) | High-level decomposition of the `HBD1PS1D.Q41` master runtime supervisor. |
| [`YAMANA_HBE_HBD_DMA_SUBBLOCKS.md`](./YAMANA_HBE_HBD_DMA_SUBBLOCKS.md) | Analysis of V-RAM DMA channel transfers, V-Blank timing, and asset streaming. |
| [`YAMANA_HBE_MESSAGING_VM.md`](./YAMANA_HBE_MESSAGING_VM.md) | Reverse-engineered opcodes and control-flow sequences for the dialogue interpreter. |
| [`YAMANA_HBE_16BIT_SYMBOL_ADDRESSING.md`](./YAMANA_HBE_16BIT_SYMBOL_ADDRESSING.md) | Resolution mechanics for Japanese 16-bit shift tokens and Roman character expansion. |
| [`YAMANA_HBE_FONT_PLANE_RENDERER.md`](./YAMANA_HBE_FONT_PLANE_RENDERER.md) | Custom proportional Variable-Width Font (VWF) engine injection specifications. |
| [`YAMANA_HBE_DISC_INDEX_ARCHIVE.md`](./YAMANA_HBE_DISC_INDEX_ARCHIVE.md) | Disc TOC mapping, LBA alignment, sector hashing, and file integrity protocols. |
| [`YAMANA_HBE_OVERLAY_RESIDENCY.md`](./YAMANA_HBE_OVERLAY_RESIDENCY.md) | RAM allocation tables and overlay paging between Map, Battle, and Cinema states. |
| [`YAMANA_HBE_FRAME_LOOP_SCHEDULER.md`](./YAMANA_HBE_FRAME_LOOP_SCHEDULER.md) | Interrupt service routines, V-Sync dispatchers, and input polling loops. |
| [`YAMANA_HBE_MASTER_SID_LIBRARIES.md`](./YAMANA_HBE_MASTER_SID_LIBRARIES.md) | String Identification (SID) database tables across all 5 + 1 Chapters. |
| [`YAMANA_HBE_MASTER_TID_LIBRARIES.md`](./YAMANA_HBE_MASTER_TID_LIBRARIES.md) | Texture Identification (TID) index dictionaries and V-RAM clut bindings. |
| [`YAMANA_HBE_MASTER_DUNGEON_SCRIPTS.md`](./YAMANA_HBE_MASTER_DUNGEON_SCRIPTS.md) | 3D trigger matrices, camera rotators, and collision meshes in complex environments. |
| [`YAMANA_HBE_BATTLE_OVERLAY_SYSTEM.md`](./YAMANA_HBE_BATTLE_OVERLAY_SYSTEM.md) | Monster animation buffers, spell particle render routines, and battle math. |
| [`YAMANA_HBE_COMPRESSION_CODECS.md`](./YAMANA_HBE_COMPRESSION_CODECS.md) | Bitstream compression algorithms and custom dictionary decompressors. |
| [`YAMANA_HBE_GLOSSARY_AND_INDEX.md`](./YAMANA_HBE_GLOSSARY_AND_INDEX.md) | Unified symbol, variable, function pointer, and hardware address lookup. |

---

## 🛡️ Dual-Platform Research Track: PSX & Super Famicom

The Zenithian Forge project operates on a dual-vector development paradigm:
1. **PlayStation (PSX) Master Engine (Lead):** Hardware-native in-place string injection, VWF rendering, and dialogue reconstruction on `SLPM_869.16`.
2. **Super Famicom (SFC) Backport Track (Secondary):** Architectural research backporting the enhanced campaign, script structure, and Chapter 6 prologue into the *Dragon Quest III* 6 MB ExHiROM Super Famicom engine.

---

## 💿 ROM / ISO Target Verification

Ensure your dump matches these cryptographic signatures prior to running the **VoidPatcher**:

```text
Game Title:      Dragon Quest IV: Michibikareshi Mono-tachi (Japan)
Disc Serial:     SLPM-869.16
Internal ID:     HBD1PS1D.Q41
Platform:        Sony PlayStation (PSX / PSone)

CRC32:           3D67C858
MD5:             B84724628BE9EB226EBFC77D38C87474
SHA-1:           85064625AFA12219880FC8D07047A3CC1C595CB9
```

---

## 🚀 VoidPatcher Deployment & Usage

The **VoidPatcher** toolchain automatically verifies source LBA alignment, builds the new dynamic font plane, adjusts MIPS branch tables, and generates an updated disc image.

```bash
# Clone the repository
git clone https://github.com/luxauraofficial777/dq4zenithianforge.git
cd dq4zenithianforge

# Apply patch using the VoidPatcher CLI
./voidpatcher --source "Dragon Quest IV (Japan) (SLPM-86916).bin" \
              --target "Dragon Quest IV - Zenithian Forge v1.0A.bin" \
              --lang en \
              --verify
```

### Build Versions
* **VoidPatcher v1.0A-INT:** Stable release. Full hardware accuracy across all console revisions, emulators, and ODEs. Includes internationalization support for 9 languages.
* **VoidPatcher RC1 / RB1 (Historical):** Milestones archived for regression testing and debugging legacy Auld Well camera stalls.

---

## 🏛️ Pedigree, Lineage & Historical Credits

This suite represents hundreds of hours of low-level MIPS decompilation, CD-ROM container research, and community reverse-engineering milestones:

* **Conception, Architecture & Finalization:** **Lux Aura** ([`@luxauraofficial777`](https://github.com/luxauraofficial777) / VoidWalkers Research Project).
* **Foundational Text Extraction & Java Engine:** Built upon seminal structural research and early patcher tooling by **Markus Schroeder** (*Markus Projects*).
* **Early Extraction Tooling & Research:** **Mandy Wilkens** (*dq4psxtrans*).
* **In Memoriam & Eternal Honor:**
  * **Koichi Nakamura (中村 光一)** — For creating the rules, the systems, and the design foundations that defined the Japanese RPG.
  * **Manabu Yamana (山名 学)** — For his transcendent engine architecture, assembly mastery, and visionary direction at HeartBeat.
  * **Yuji Horii (堀井 雄二)** — For the timeless Zenithian saga.
  * **Akira Toriyama (鳥山 明)** & **Koichi Sugiyama (すぎやま こういち)** — Whose art and symphony gave breath to the world.

---

## ⚖️ License & Legal Disclaimer

* The research, decompilation scripts, documentation, and tooling in this repository are licensed under [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC-BY-NC-SA 4.0)](LICENSE).
* *Dragon Quest*, *Dragon Quest IV: Michibikareshi Mono-tachi*, and related assets are registered trademarks and copyright of Square Enix Holdings Co., Ltd., Armor Project, and Bird Studio.
* This repository contains **no copyrighted game binaries, ISO images, or commercial ROM dumps**. It is strictly an open-source reverse-engineering suite, academic study, and binary differential patching framework.
