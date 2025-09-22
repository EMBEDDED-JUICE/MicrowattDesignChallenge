Project Proposal: Transparent Self-Monitoring Microwatt

Hackathon: Microwatt Momentum – OpenPOWER HW Design Hackathon

Theme: "Microwatt for the open computing era"

# Abstract

This project enhances the open-source Microwatt POWER CPU core by integrating a real-time on-chip telemetry and debug engine. The engine continuously monitors pipeline activity, instruction flow, and performance metrics such as instruction-per-cycle (IPC), branch mispredictions, stall cycles, and memory accesses. It exposes this information through memory-mapped registers accessible to software and provides an optional trace buffer for instruction history.  
<br/>The goal is to make Microwatt more developer-friendly by providing built-in observability, enabling researchers, FPGA developers, and students to easily debug, profile, and optimize workloads running on Microwatt without relying on external debug tools.  
<br/>This proposal addresses the hackathon’s theme by advancing Microwatt into the era of transparent, self-diagnosing, open CPUs — bridging the gap between academic research and practical deployment.

# Key Features

- Performance Monitoring Counters (PMCs): IPC, branch misprediction count, stall cycles, memory access latency.
- On-Chip Trace Buffer: Captures recent instruction PCs + opcodes, FIFO-based, triggered capture support.
- Telemetry Export: Memory-mapped registers, C demo software for stats, optional UART/JTAG export.
- Verification & Reproducibility: RTL-level testbenches, validation against software-instrumented models, documented OpenLane flow.

# Why This Project

• Practical & New: Adds observability infrastructure directly inside Microwatt.  
• Educational Impact: Helps students and researchers learn CPU behavior.  
• Community Benefit: Improves reproducibility for Microwatt-based designs.  
• Feasible: Modular RTL design fits OpenFrame SoC user area with clear scope.

# Tools & Platforms

- Microwatt CPU Core (<https://git.openpower.foundation/cores/microwatt>)
- ChipFoundry OpenFrame SoC Platform
- OpenPOWER ISA
- OpenLane / chipIgnite Flow on SKY130
- Simulation Tools: Verilator, GHDL, GTKWave
- Software Tools: GCC for POWER, GDB

# Deliverables

- RTL code for telemetry engine + Microwatt integration
- Testbenches for verification of counters and trace buffer
- C demo software for telemetry access
- Documentation of AI prompts used (if AI-assisted)
- Open-source GitHub repository (MIT/Apache2 licensed)
- Screenshots + demo video showing project usage

# Project Timeline

1. Week 1 (Proposal): Define architecture, block diagrams, set up environment
2. Week 2–3 (Implementation): Develop counters, registers, trace buffer
3. Week 4 (Verification): Run testbenches, integrate demo software
4. Final Week: Prepare repo, documentation, demo video

# Judging Fit

• Documentation: Clear repo structure, reproducible OpenLane flow  
• Prompt Documentation: Full record of AI LLM prompts (if used)  
• Code Quality: Modular, well-documented RTL  
• Verification: Thorough test coverage  
• Technical Merit: Extends Microwatt with an innovative monitoring subsystem

# License

This project will be released under the Apache 2.0 License to ensure open-source adoption and community contributions.
