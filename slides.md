---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Just-In-Time Compilation of NES Games In .Net
info:
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
---

# Just-In-Time Compilation of NES Games In .Net

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---

# NES Hardware

<img src="/img/nes-motherboard.jpg" style="height:90%; display: block; margin: 0 auto" />

---

# What Is An Emulator?

<img src="/img/understanding-emulators.png" style="height:90%; display: block; margin: 0 auto" />

---

# Giant Switch Blocks

<img src="/img/switch-block.png" style="height:90%; display: block; margin: 0 auto" />

---

# CPU Pipelineing

<img src="/img/pipelined.webp" style="height:95%; display: block; margin: 0 auto"/>

---

# Branch Prediction

<img src="/img/branch-misprediction.png" style="height:90%; display: block; margin: 0 auto" />

---

# Linear Assembly Is Efficient

<img src="/img/instruction_execution_in_5_stage_pipeline.webp" style="height:90%; display: block; margin: 0 auto" />

---

# Giant Switch Blocks

<img src="/img/switch-block.png" style="height:90%; display: block; margin: 0 auto" />

---

# Just-In-Time Assembly Generation

<img src="/img/understanding-emulators.png" style="height:90%; display: block; margin: 0 auto" />

---

# .Net Runtime To The Rescue

<img src="/img/Architecture-of-NET-framework.png" style="height:90%; display: block; margin: 0 auto" />

---

# Microsoft Intermediate Language (MSIL)

<img src="/img/msil-example.png" style="height:90%; display: block; margin: 0 auto" />

---

# Building A Custom Assembly

<img src="/img/assembly_generation.png" style="height:95%; display: block; margin: 0 auto" />

---

# ILGenerator Class

<img src="/img/ilgenerator.png" style="height:90%; display: block; margin: 0 auto" />

---

# Beware!

<img src="/img/invalid-program-exception.png" style="height:90%; display: block; margin: 0 auto" />

---

# 6502 Operations

* 3 8-bit registers
* 7 CPU Flags
* 8-bit memory read and writes
  * Including stack operations
* Values can be constant values, direct memory locations, or indirect memory locations

---

# 6502 Assembly

<img src="/img/6502-instructions.png" style="height:95%; display: block; margin: 0 auto" />

---
layout: two-cols
---

# 6502 Instruction

1. Inc (Increment)

::right::

# Actual Work

1. Increment operand 
2. Set CPU Zero flag if result is zero
3. Set CPU Negative flag if negative

---

# Composable Sub-Instructions

* 12 Partial Instructions
  * Copy Value
  * Return
  * Unary Operator
  * Binary Operator
  * Mark Label
  * Call Function
  * Jump Unconditionally
  * Jump If Zero
  * Jump If Not Zero
  * Push Stack Value
  * Pop Stack Value

---

# 6502 Function Disassembly

<img src="/img/disassemble-function.png" style="height:95%; display: block; margin: 0 auto" />

---

# JIT Loop

<img src="/img/jit-loop-no-cache.png" style="height:95%; display: block; margin: 0 auto" />

--- 

# Mental Model Of Function Calls

<img src="/img/function-calls.png" style="height:95%; display: block; margin: 0 auto" />

---

# Actual Function Calls

<img src="/img/program-flow.png" style="height:95%; display: block; margin: 0 auto" />

---

# JIT Loop

<img src="/img/jit-loop-no-cache-return.png" style="height:95%; display: block; margin: 0 auto" />

---

# Caching For Performance

<img src="/img/jit-loop-full.png" style="height:95%; display: block; margin: 0 auto" />

---

# Self Modifying Code (flashing light warning)

<video src="/img/c64-basic.mp4" autoplay=on loop=on style="height:95%; display: block; margin: 0 auto" />

---

# BASIC Loop

1. Increment `B` value
1. Increment `C` value
1. Load memory address `0xCCBB`
1. Parse Character
1. Repeat For Next Character

---

# Self Modifying Code

<img src="/img/bad-smc-handling.png" style="height:95%; display: block; margin: 0 auto" />

---

# JIT Bottleneck

<img src="/img/jit-bottleneck.webp" style="height:95%; display: block; margin: 0 auto" />

---

# Strategy #1: Interpreter

## Back to the giant switch block!

---

# Strategy #2: Detect Self Modifying Code Targets

## Use custom instructions to handle known cases

---

# Performance Numbers

---

# Performance Numbers (Sans GPU)

---

# MSIL Has Many Applications

* Aspect-Oriented Programming
* Compile-Time Performance For Runtime Logic
* Performance Evaluation
* Decompilation

--- 
layout: two-cols
---

# Thank You!

<img src="/img/linked-in-qr-code.png" style="height:70%; display: block; margin: 0 auto" />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
<a href="https://www.linkedin.com/in/mshapirodev">https://www.linkedin.com/in/mshapirodev</a>

::right::

<br />
<br />

<img src="/img/github-qr-code.png" style="height:70%; display: block; margin: 0 auto" />
&nbsp; &nbsp; &nbsp; &nbsp; &nbsp;
<a href="https://github.com/KallDrexx/Dotnet6502">https://github.com/KallDrexx/Dotnet6502</a>

