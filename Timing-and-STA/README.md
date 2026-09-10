# ISA vs Microarchitecture

`Category: Computer Architecture` `Stage: Theory`

---

- **Definition**

The **Instruction Set Architecture (ISA)** is the programmer-visible interface between software and hardware that defines the instructions, registers, data types, memory model, and architectural behavior of a processor. **Microarchitecture** is the internal hardware organization used to implement that ISA, including the datapath, control logic, pipeline, execution units, and memory structures.

---

- **Relevance to RTL Design**

* The ISA defines **what** the processor must do, while the microarchitecture defines **how** the processor performs those operations internally.
* RTL designers implement the **microarchitecture** using hardware description languages such as Verilog or SystemVerilog; the ISA provides the functional requirements that the RTL must satisfy.
* Understanding this distinction is fundamental when designing processor datapaths, control units, pipelines, register files, and other architectural hardware blocks.

---

- **Technical Overview**

### Instruction Set Architecture (ISA)

The ISA is the **software-visible contract** between a processor and the programs that execute on it.

It defines aspects such as:

* Instruction set and instruction formats
* Instruction encoding
* General-purpose and special-purpose registers
* Data types and operand sizes
* Addressing and memory-access rules
* Control-flow instructions
* Exceptions and interrupts
* Privilege and execution modes
* Architectural memory model

Examples of ISAs include:

* RISC-V
* ARM
* x86

The ISA specifies the required behavior of an instruction, but does not normally specify the internal hardware used to achieve that behavior.

### Microarchitecture

Microarchitecture describes the internal organization of a processor that implements a particular ISA.

Typical microarchitectural components include:

* Program Counter (PC)
* Instruction decoder
* Register file
* ALU
* Control unit
* Datapath
* Pipeline registers
* Branch logic
* Hazard detection and forwarding logic
* Cache hierarchy
* Execution units
* Memory interfaces

Microarchitecture therefore determines **how instructions are processed inside the processor**.

### ISA as a Contract

The relationship can be viewed as:

```text
             Software
                 │
                 ▼
        ┌─────────────────┐
        │       ISA       │
        │   WHAT to do    │
        └────────┬────────┘
                 │
                 │ implemented by
                 ▼
        ┌─────────────────┐
        │ Microarchitecture│
        │   HOW to do it  │
        └────────┬────────┘
                 │
                 ▼
            RTL Design
                 │
                 ▼
             Hardware
