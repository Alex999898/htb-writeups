---
layout: default
title: "Reversing"
parent: Challenges
nav_order: 4
permalink: /challenges/reversing/
---

# Reversing Challenges

Writeups for HTB Reverse Engineering challenges.

## Challenge Index

| Challenge | Difficulty | Techniques | Key Takeaway |
|-----------|-----------|------------|--------------|
| [Behind the Scenes](behind-the-scenes/) | Very Easy | x86, ltrace/strace | Basic dynamic analysis |
| [WIDE](wide/) | Very Easy | Strings, Wide Characters | Unicode string analysis |
| [Shattered Tablet](shattered-tablet/) | Very Easy | x86, Static Analysis | Simple flag check reversal |
| [Hunting License](hunting-license/) | Easy | ELF, GDB | Debugging and breakpoint analysis |
| [Rebuilding](rebuilding/) | Easy | x86, Control Flow | Reconstructing algorithms |
| [Bypass](bypass/) | Easy | .NET, dnSpy | .NET binary decompilation |
| [Baby RE](baby-re/) | Easy | x86, Ghidra | Basic static analysis workflow |
| [Impossible Password](impossible-password/) | Easy | Anti-Debugging, ptrace | Bypassing anti-debug checks |
| [Bomb](bomb/) | Easy | x86, Phase-based | Multi-phase reverse engineering |
| [Cant Vote](cant-vote/) | Easy | ELF, Patching | Binary patching techniques |
| [Ouija](ouija/) | Medium | x86, Custom Encoding | Custom encoding scheme reversal |
| [Potion Master](potion-master/) | Medium | Rust, Binary Analysis | Reversing Rust binaries |
| [Snakecode](snakecode/) | Medium | Python Bytecode | Python .pyc decompilation |
| [Alien Saboteur](alien-saboteur/) | Medium | VM, Custom Architecture | Custom VM instruction set reversal |
| [Teleport](teleport/) | Medium | Anti-Debugging, Obfuscation | Bypassing multiple protections |
| [LootStash](loot-stash/) | Medium | Go Binary | Reversing Go binaries |
| [Maze](maze/) | Medium | ARM, Cross-Architecture | ARM binary analysis |
| [CrackMe](crackme/) | Medium | x86, Keygen | Writing keygens from reversed logic |
| [Interstellar C2](interstellar-c2/) | Hard | C2 Protocol, Crypto | Reversing C2 communications |
| [FlecksOfGold](flecks-of-gold/) | Hard | Firmware, MIPS | Embedded firmware analysis |
| [QuillCTF](quillctf/) | Hard | Solidity Bytecode | EVM bytecode reversing |

## By Architecture

| Architecture | Challenges | Tools |
|-------------|-----------|-------|
| x86/x64 Linux ELF | Baby RE, Bomb, Hunting License, Rebuilding | Ghidra, GDB+GEF, radare2 |
| .NET | Bypass | dnSpy, ILSpy, dotPeek |
| Python | Snakecode | uncompyle6, decompyle3 |
| Rust | Potion Master | Ghidra (with Rust support) |
| Go | LootStash | Ghidra, GoReSym |
| ARM | Maze | Ghidra, QEMU |
| Java | - | jadx, JD-GUI, Procyon |
| MIPS | FlecksOfGold | Ghidra, binwalk |
| EVM | QuillCTF | Panoramix, Dedaub |

## Recommended Tools

| Tool | Purpose |
|------|---------|
| [Ghidra](https://github.com/NationalSecurityAgency/ghidra) | Primary decompiler and disassembler (free, NSA) |
| [IDA Free](https://hex-rays.com/ida-free) | Industry-standard disassembler |
| [radare2](https://github.com/radareorg/radare2)/[rizin](https://github.com/rizinorg/rizin) | CLI reverse engineering framework |
| [GDB](https://www.sourceware.org/gdb/) + [GEF](https://github.com/hugsy/gef) | Dynamic analysis and debugging |
| [Binary Ninja](https://binary.ninja) | Modern binary analysis platform |
| [dnSpy](https://github.com/dnSpy/dnSpy) | .NET assembly editor and debugger |
| [jadx](https://github.com/skylot/jadx) | Java/Android decompiler |
| [x64dbg](https://github.com/x64dbg/x64dbg) | Windows debugger |
| [Cutter](https://github.com/rizinorg/cutter) | GUI for radare2 |
| strace/ltrace | System/library call tracing |

## Approach

1. **Identify the binary**: `file binary`, check architecture and type
2. **Static analysis**: Load in Ghidra, find `main()`, understand control flow
3. **String analysis**: `strings -n 8 binary` for hardcoded values
4. **Dynamic analysis**: Run in GDB, set breakpoints at comparisons
5. **Understand the algorithm**: Reverse the logic, write a solver
6. **Handle protections**: Anti-debug, obfuscation, packing
