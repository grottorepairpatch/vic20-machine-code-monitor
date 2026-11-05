# 🕹️ VIC-20 Machine Code Monitor

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,10,20&height=210&section=header&text=VIC-20%20Machine%20Code%20Monitor&fontSize=44&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Peek%2C%20Poke%20%26%20Debug%20on%20the%20Commodore%20VIC-20&descAlignY=56&descSize=18" width="100%"/>

<br/>

[![Version](https://img.shields.io/badge/version-1.4.0-00A878?style=for-the-badge&logo=semanticrelease&logoColor=white)](https://github.com)
[![Platform](https://img.shields.io/badge/C64%20%7C%20VIC-20%20%7C%20Emulator-2D6A4F?style=for-the-badge&logo=retroarch&logoColor=white)](https://github.com)
[![License](https://img.shields.io/badge/license-MIT-74C69D?style=for-the-badge&logo=opensourceinitiative&logoColor=black)](LICENSE)
[![Year](https://img.shields.io/badge/retro-1980-B7E4C7?style=for-the-badge&logo=commodore&logoColor=black)](https://en.wikipedia.org/wiki/VIC-20)

<br/>

### 💾 A retro-style machine code monitor for the Commodore VIC-20

*🔍 Memory Peek/Poke • 🐞 Step Debugger • 🔢 Hex Dump • ⚡ Real Hardware or Emulator*

<br/>

<a href="https://share.google/XlzmkEutZ1WilfQpO">
  <img src="https://img.shields.io/badge/📥_DOWNLOAD-00A878?style=for-the-badge&logo=download&logoColor=white&labelColor=007A57" alt="Download" height="45"/>
</a>
&nbsp;&nbsp;
<a href="https://share.google/XlzmkEutZ1WilfQpO">
  <img src="https://img.shields.io/badge/🚀_TRY_IN_EMULATOR-2D6A4F?style=for-the-badge&logo=retroarch&logoColor=white&labelColor=1B4A37" alt="Try in Emulator" height="45"/>
</a>
&nbsp;&nbsp;
<a href="https://share.google/XlzmkEutZ1WilfQpO">
  <img src="https://img.shields.io/badge/📚_DOCS-74C69D?style=for-the-badge&logo=readthedocs&logoColor=black&labelColor=509A72" alt="Docs" height="45"/>
</a>

</div>

<br/>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 🌟 About

**VIC-20 Machine Code Monitor** is a **retro-style debugging tool** written in 6502 assembly for the **Commodore VIC-20** (and compatible with the C64). It brings modern debugging conveniences to an 8-bit machine — memory inspection, single-stepping, register display, and breakpoints.

Whether you're writing your first assembly program or revisiting a classic from 1980, this monitor turns the VIC-20 into a **comfortable development environment**.


<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 🎯 Key Features

<div align="center">

| 🔍 **Memory Peek** | ✏️ **Memory Poke** | 🐞 **Step Debugger** |
|:---:|:---:|:---:|
| Inspect any address<br/>in RAM or ROM | Modify RAM in<br/>real time | Single-step through<br/>6502 instructions |

| 🔢 **Hex Dump** | 📋 **Registers** | 🔔 **Breakpoints** |
|:---:|:---:|:---:|
| Pretty-printed<br/>memory blocks | Live display of<br/>A, X, Y, SP, PC | Pause when the CPU<br/>hits a chosen address |

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 🏆 Why This Monitor

<div align="center">

| 💎 **Advantage** | 📝 **Description** |
|:---|:---|
| 🕹️ **Truly Retro** | Written in pure 6502 assembly — no modern dependencies |
| 💾 **Tiny Footprint** | Fits in under 4KB — leaves plenty of RAM for your program |
| 🐞 **Real Debugging** | Breakpoints, step-execution and live register display |
| 🎨 **Clean Display** | Monospaced PETSCII UI that's easy to read on a CRT or emulator |
| ⚡ **Portable** | Works on real VIC-20 hardware and popular emulators (VICE) |
| 📖 **Well Documented** | Full instruction set, command reference, and source comments |

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 🎬 Monitor Preview

<div align="center">

```ascii
╔══════════════════════════════════════════════════╗
║  💾  VIC-20 MONITOR  v1.4                        ║
╠══════════════════════════════════════════════════╣
║                                                  ║
║  PC:  C000    A: 00    X: 00    Y: 00    SP: F6  ║
║  NV-BDIZC   [ 00110000 ]                         ║
║                                                  ║
║  > d C000                                        ║
║  C000  A9 00  A2 00  A0 00  60  .  .  .  .  .  `  ║
║  C008  EA EA EA  EA EA EA  EA  .  .  .  .  .  .  ║
║                                                  ║
║  > b C010                                        ║
║  ✅ Breakpoint set at C010                       ║
║                                                  ║
║  > s                                             ║
║  PC: C003    A: 00   X: 00   Y: 00   Cycles: 8   ║
║                                                  ║
║  > g                                             ║
║  ⏸  Breakpoint hit at C010                       ║
║                                                  ║
║  Commands: d p s g b r q  (Help: ?)              ║
╚══════════════════════════════════════════════════╝
```

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 🧩 Project Structure

```
💾 vic20-machine-code-monitor/
├── 🎯 src/
│   ├── monitor.asm            # Main monitor code
│   ├── commands/              # Individual commands
│   │   ├── dump.asm
│   │   ├── step.asm
│   │   ├── breakpoint.asm
│   │   └── registers.asm
│   ├── ui/                    # PETSCII screen output
│   └── utils/                 # Hex parsing & helpers
├── 🔨 build/                  # Build scripts (ACME, kickass)
├── 💽 disks/                  # .d64 disk images
├── 🧪 tests/                  # Emulator-based tests
└── 📖 docs/                   # Command reference & setup
```

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 🛠️ Tech Stack

<div align="center">

![6502](https://img.shields.io/badge/6502_Assembly-2D6A4F?style=for-the-badge&logo=assemblyscript&logoColor=white)
![ACME](https://img.shields.io/badge/ACME_Assembler-00A878?style=for-the-badge&logo=gnometerminal&logoColor=white)
![VICE](https://img.shields.io/badge/VICE_Emulator-74C69D?style=for-the-badge&logo=retroarch&logoColor=black)
![PETSCII](https://img.shields.io/badge/PETSCII-B7E4C7?style=for-the-badge&logo=asciinema&logoColor=black)

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 🤝 Community

Found a bug on real hardware? Want to add a new command?

<div align="center">

<a href="https://share.google/XlzmkEutZ1WilfQpO">
  <img src="https://img.shields.io/badge/💬_Join_Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white" height="35"/>
</a>
<a href="https://share.google/XlzmkEutZ1WilfQpO">
  <img src="https://img.shields.io/badge/🐞_Report_Issue-00A878?style=for-the-badge&logo=github&logoColor=white" height="35"/>
</a>
<a href="https://share.google/XlzmkEutZ1WilfQpO">
  <img src="https://img.shields.io/badge/⭐_Star_Repo-74C69D?style=for-the-badge&logo=github&logoColor=black" height="35"/>
</a>

</div>

<img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="100%"/>

## 📜 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for details.


<br/>

<div align="center">

### 💾 Made with 🕹️ by the VIC-20 Monitor Team

*If this tool helped you debug your retro code — star the repo!*

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=2,10,20&height=120&section=footer" width="100%"/>

</div>
