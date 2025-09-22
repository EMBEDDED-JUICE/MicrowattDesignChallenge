# Transparent Self-Monitoring Microwatt

**Hackathon:** [Microwatt Momentum – OpenPOWER HW Design Hackathon](https://chipfoundry.org/)  
**Theme:** *"Microwatt for the open computing era"*

---

## 📌 Abstract

The **Transparent Self-Monitoring Microwatt** project aims to transform the open-source [Microwatt POWER CPU core](https://git.openpower.foundation/cores/microwatt) into a **self-observable and developer-friendly platform** by embedding real-time performance monitoring and telemetry capabilities directly into the CPU pipeline. While Microwatt already provides an accessible reference design for the POWER ISA, debugging and performance analysis often depend on external tools, intrusive instrumentation, or FPGA probes. This creates a barrier for students, researchers, and open-hardware developers who wish to study microarchitectural behavior or optimize workloads on resource-constrained platforms.

To address this, our design introduces a **lightweight telemetry and debug subsystem** that continuously monitors key pipeline signals and records essential performance metrics. These include **instructions per cycle (IPC), branch prediction accuracy, stall cycles, and memory latency metrics**, which are critical for both academic research and practical optimization. Additionally, we implement a configurable **on-chip trace buffer** that captures a short instruction history, enabling step-by-step workload analysis without external trace hardware.  

All telemetry data is made accessible through **memory-mapped registers** within the OpenFrame SoC environment, and a **C software demo** demonstrates how to retrieve and visualize this information. For extended use, telemetry can also be exported through UART or JTAG interfaces, allowing integration with standard debugging workflows.  

From a reproducibility standpoint, the project adheres to **hackathon requirements** by providing fully open-source RTL, AI prompt logs (if applicable), STA and SDF constraints, and OpenLane/chipIgnite configuration files for SKY130 implementation. This ensures that any participant or community member can reproduce results, validate design choices, and extend the work for future research.  

By embedding self-monitoring into Microwatt, this project bridges the gap between **research CPUs** and **production observability frameworks**, helping the open-source hardware ecosystem advance toward **transparent, self-diagnosing processors**. The result is a powerful educational and research tool that empowers developers to learn CPU internals, debug complex workloads, and accelerate innovation in the open computing era.

---

## 🚀 Key Features
- **Performance Monitoring Counters (PMCs):** IPC, branch misprediction count, stall cycles, memory access latency.  
- **On-Chip Trace Buffer:** Captures recent instruction PCs + opcodes, FIFO-based, triggered capture support.  
- **Telemetry Export:** Memory-mapped registers, C demo software for stats, optional UART/JTAG export.  
- **Verification & Reproducibility:** RTL-level testbenches, validation against software-instrumented models, documented OpenLane flow.  

---

## 🎯 Why This Project
- **Practical & New:** Adds observability infrastructure directly inside Microwatt.  
- **Educational Impact:** Helps students and researchers learn CPU behavior.  
- **Community Benefit:** Improves reproducibility for Microwatt-based designs.  
- **Feasible:** Modular RTL design fits OpenFrame SoC user area with clear scope.  

---

## 🛠 Tools & Platforms
- [Microwatt CPU Core](https://git.openpower.foundation/cores/microwatt)  
- ChipFoundry OpenFrame SoC Platform  
- OpenPOWER ISA  
- OpenLane / chipIgnite Flow on SKY130  
- Simulation Tools: Verilator, GHDL, GTKWave  
- Software Tools: GCC for POWER, GDB  

---

## 📦 Deliverables (Aligned to Project Requirements)
- **Short English Description:** This README contains the concise project summary and design overview.  
- **Open-Source RTL & Integration:** VHDL/Verilog sources for the telemetry engine and Microwatt integration wrapper, published with **Apache-2.0** license.  
- **OpenFrame Fit Artifacts:** Top-level OpenFrame user-project wrapper, IO/pin constraints, area/timing utilization reports, and a *fit/area report* demonstrating the design fits the OpenFrame User Project area.  
- **Reproducible RTL Verification:** Self-contained testbenches (with Makefile/CIs or `scripts/run_sim.sh`), expected outputs, and waveform dumps; includes *golden logs* for pass/fail.  
- **STA & SDF Collateral:** Timing constraints (`.sdc`), STA setup/hold reports, back-annotated **SDF** files, and simulation scripts showing SDF-annotated runs.  
- **AI Usage Disclosure:** If AI was used, provide all prompts and session logs under `docs/ai/` (timestamps + context) as required.  
- **Reproducible Physical Flow:** Complete **OpenLane/chipIgnite** configuration (`config.tcl`, `pin_order.cfg`, floorplan constraints), run scripts, and final run results (DRC/LVS/antenna/CTS/timing reports). Alternative open flows accepted if fully documented and reproducible.  
- **SKY130 Compatibility:** Design targets **SKY130** standard-cell libraries; no custom cells required. Document used libraries and corners.  
- **Precheck & Tapeout Proof:** ChipFoundry precheck pass logs and tapeout submission artifacts (manifests, checksums) included in `tapeout/`.  
- **Demo Materials:** Screenshots and a **how-to / step-by-step** video link in `docs/demo/` demonstrating project creation and usage (may be used by ChipFoundry for promotion).  
- **Software Examples:** Minimal C demo to read PMCs/trace via MMIO; optional UART/JTAG telemetry exporter.  
- **Repo Repro Guide:** `docs/REPRODUCE.md` covering environment, Docker/conda image, exact commands, seeds, and expected outputs.

---

## 🗓 Project Timeline
1. **Week 1 (Proposal):** Define architecture, block diagrams, set up environment  
2. **Weeks 2–3 (Implementation):** Develop counters, registers, trace buffer  
3. **Week 4 (Verification):** Run testbenches, integrate demo software  
4. **Final Week:** Prepare repo, documentation, demo video  

---

## 📄 License
Released under the **Apache 2.0 License** to ensure open-source adoption and community contributions.

---

## 👥 Contributors
- **Naveen Kumar Senthil Kumar** ([ns6503@nyu.edu](mailto:ns6503@nyu.edu))  
- **Dhirajzen Bagawath Geetha Kumaravel** ([db5309@nyu.edu](mailto:db5309@nyu.edu))  

