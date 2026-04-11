---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
#background: https://cover.sli.dev
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

<video src="/img/games.mp4" autoplay=on loop=on muted style="height:350px; display: block; margin: 0 auto" />

---

# What Happens When You Compile Code?

<img src="/img/llvm-trials.png" style="height:90%; display: block; margin: 0 auto" />
---

# Language Bytecode

<img src="/img/bytecode.png" style="height:90%; display: block; margin: 0 auto" />
---

# .Net Runtime Process

<img src="/img/Architecture-of-NET-framework.png" style="height:90%; display: block; margin: 0 auto" />
---

# What Is MSIL

<img src="/img/msil-example.png" style="height:90%; display: block; margin: 0 auto" />

---
layout: center
---

# Why Is This Useful?

---

# Aspect Oriented Programming

* Code that modifies code during or after compilation
  * Typescript Decorators
  * Java Annotations
  * C# Attributes


---

# Decompilation

<img src="/img/decompilation-labelled.png" style="height:90%; display: block; margin: 0 auto" />

---
layout: center
---

# Decompilation = Transpilation

---

# C# -> C

<img src="/img/transpile-labelled.png" style="height:90%; display: block; margin: 0 auto" />

---

# C# On Embedded

<img src="/img/embedded-csharp.png" style="height:90%; display: block; margin: 0 auto" />

---

# C# On Embedded

<video src="/img/embedded.mp4" autoplay=on loop=on muted style="height:350px; display: block; margin: 0 auto" />
---

# C# In The Linux Kernel

<img src="/img/uprobe-code.png" style="height:90%; display: block; margin: 0 auto" />

---

# C# In The Linux Kernel

<img src="/img/ebpf.png" style="height:90%; display: block; margin: 0 auto" />

---

# C# On An SNES

<img src="/img/snes-code.png" style="height:90%; display: block; margin: 0 auto" />

---

# C# On An SNES

<video src="/img/snes-csharp.mp4" autoplay=on loop=on muted style="height:400px; display: block; margin: 0 auto" />

---
layout: center
---

# But Then I Had A Thought

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

# CPU Pipelining

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

# Building A Custom Assembly

<img src="/img/assembly_generation.png" style="display: block; margin: 0 auto" />

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

# Performance Numbers

<img src="/img/perf-numbers.png" style="height:90%; display: block; margin: 0 auto" />

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

