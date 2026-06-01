# Kai

**FPGA Hardware Acceleration | Self-Attention & Transformer Optimizer**

I build small, focused open-source tools that sit at the boundary between Transformer architecture and the hardware that runs it — cost models, tile planners, and developer tools that make AI workloads more legible to engineers.

📍 Tokyo · 🛠️ Python / JavaScript / FPGA mapping concepts

---

## Current Focus

- Self-attention and KV cache cost modeling
- FPGA-oriented tile planning and resource estimation for Transformer inference
- Developer tools that help AI coding agents understand repositories faster
- Turning abstract model shapes into concrete engineering constraints (SRAM, BRAM, URAM, DSP)

## Projects

### [fpga-attention-tile-planner](https://github.com/jiakai03177-coder/fpga-attention-tile-planner) · `v0.2.0`

Plan self-attention query/key tile sizes for FPGA accelerators. Estimates BRAM18K / URAM / DSP48 utilization against real device presets (VU9P, ZCU102, VCK190 …) so you can answer *"does this attention tile fit my FPGA?"* before writing HDL.

```bash
attention-tiles --preset llama3-8b --seq-len 4096 --sram-kib 512 --device vu9p
```

> Why: most FPGA attention papers stop at "we tiled it" — this answers the missing question of *which* tile actually fits.

### [attention-cost-lab](https://github.com/jiakai03177-coder/attention-cost-lab)

Estimate Transformer attention FLOPs, KV cache size, and decode memory pressure directly from model shape parameters. Useful for early-stage architecture sizing before you spin up a GPU.

```bash
attention-cost --preset llama3-8b --seq-len 8192
```

> Why: turns "how big does this model get at long context?" from a spreadsheet exercise into one CLI call.

### [repo-context-packer](https://github.com/jiakai03177-coder/repo-context-packer)

Generate compact AI-ready context packs for codebases so coding agents (Claude Code, Codex, Cursor) can understand a repo before editing it.

```bash
repo-context-packer --token-budget 8000
```

> Why: AI coding agents waste tokens re-reading the same files. This solves it once, upstream.

## Direction

I care about the path from algorithm shape to hardware-aware execution:

```text
Transformer architecture
        ↓
attention / KV cache cost
        ↓
memory bandwidth pressure
        ↓
on-chip tile planning (SRAM, BRAM, URAM)
        ↓
DSP / compute mapping
        ↓
acceleration strategy
```

Each of my projects sits on one of those arrows. The goal is to make every step a concrete, measurable engineering decision instead of a vibe.

## Tech

Python · JavaScript · Node.js · GitHub Actions · FPGA / Xilinx UltraScale+ resource modeling · Transformer inference analysis · CLI tool design

---

*Open to collaboration on FPGA-based Transformer inference, attention kernel optimization, and AI developer tooling.*
