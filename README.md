# Kai

FPGA Hardware Acceleration | Self-Attention & Transformer Optimizer

I build small open-source tools for efficient AI inference, transformer cost analysis, and AI-assisted engineering workflows.

## Current Focus

- Self-attention and KV cache cost modeling
- FPGA-oriented acceleration ideas for Transformer inference
- Developer tools that help AI coding agents understand repositories faster
- Practical profiling utilities that turn model shapes into engineering constraints

## Projects

### [attention-cost-lab](https://github.com/jiakai03177-coder/attention-cost-lab)

Estimate Transformer attention FLOPs, KV cache size, and decode memory pressure from model shape parameters.

```bash
attention-cost --preset llama3-8b --seq-len 8192
```

### [fpga-attention-tile-planner](https://github.com/jiakai03177-coder/fpga-attention-tile-planner)

Plan self-attention query/key tile sizes for FPGA and accelerator SRAM budgets.

```bash
attention-tiles --preset llama3-8b --seq-len 4096 --sram-kib 512
```

### [repo-context-packer](https://github.com/jiakai03177-coder/repo-context-packer)

Generate compact AI-ready context packs for codebases so coding agents can understand a repo before editing it.

```bash
repo-context-packer --token-budget 8000
```

## Direction

I am especially interested in the path from algorithm shape to hardware-aware execution:

```text
Transformer architecture -> attention/KV cache cost -> memory bandwidth pressure -> tile planning -> acceleration strategy
```

## Tech

Python, JavaScript, Node.js, GitHub Actions, FPGA acceleration concepts, Transformer inference analysis.
