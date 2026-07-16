# AI-Skills

A personal repository for reusable AI skills and structured research workflows.

本仓库用于保存和管理可重复使用的 AI Skills，主要服务于生物医学、生物信息学和科研工作流。

---

## Available Skills

### Biomedical Paper Card

**Path:** [`biomedical-paper-card/SKILL.md`](./biomedical-paper-card/SKILL.md)

Biomedical Paper Card 是一个用于系统化解析生物医学论文的 AI Skill。

其目标不是简单生成论文摘要，而是从科研和 PI 视角，对论文的科学问题、研究设计、证据链和科研价值进行结构化分析，并生成可长期保存的 Paper Card。

### Core Functions

该 Skill 主要包括：

- Scientific background
- Core scientific question
- Central hypothesis
- Study design
- Figure-by-Figure storyline
- Overall scientific storyline
- Key findings
- Mechanistic model
- Cell populations and marker genes
- Key technologies
- Strongest evidence
- Weakest link
- Overinterpretation check
- Major limitations
- Novelty assessment
- Implications for the field
- Implications for my research
- Reusable datasets and resources
- Obsidian knowledge-base tags

### Research Focus

该 Skill 特别适用于以下研究领域：

- Glioblastoma (GBM)
- Cancer neuroscience
- Neuron–tumor interaction
- Malignant cell states
- OPC-like cells
- Cellular plasticity
- Tumor ecosystem
- Tumor microenvironment
- Single-cell omics
- Spatial transcriptomics
- Spatial multiomics

---

## Usage

让支持读取 GitHub repository 的 AI 工具读取对应的 `SKILL.md`，然后按照其中定义的工作流执行任务。

例如：

> Read `biomedical-paper-card/SKILL.md` and follow the Biomedical Paper Card workflow to analyze the paper I provide.

或者：

> 读取 `biomedical-paper-card/SKILL.md`，按照其中定义的 Biomedical Paper Card 工作流分析我提供的论文。

建议在进行论文深度分析时同时提供论文全文 PDF，以保证分析基于原始文献证据。

对于具体 Figure、实验结果或细节问题，应优先回到论文原文进行核实，而不是仅依赖生成后的 Paper Card。

---

## Repository Structure

```text
AI-Skills/
├── README.md
└── biomedical-paper-card/
    └── SKILL.md
