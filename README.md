# Hi, I'm Weijian Deng (邓伟键)

I build **LLM systems**: MoE inference optimization, training and RL infrastructure, and high-performance C++ execution engines.

- 🎓 Master's student at **Beihang University**, AI track, 2025–2028
- 🎓 B.Eng., School of Computer Science, Beihang University, 2021–2025 (GPA 3.8/4.0)
- 🔍 Looking for **2027 internships in LLM training / inference infrastructure**, on-site or remote
- 📫 [emmmvkdeng@gmail.com](mailto:emmmvkdeng@gmail.com)

<!-- 第一个上游 PR 提交后取消注释，同时加 "## Open source" 列表：
[![Merged upstream PRs](https://img.shields.io/github/issues-search?query=author%3AVikingDeng%20is%3Apr%20is%3Amerged%20-user%3AVikingDeng%20is%3Apublic&label=merged%20upstream%20PRs&color=8957e5)](https://github.com/search?q=author%3AVikingDeng+is%3Apr+is%3Amerged+-user%3AVikingDeng&type=pullrequests)
[![Open upstream PRs](https://img.shields.io/github/issues-search?query=author%3AVikingDeng%20is%3Apr%20is%3Aopen%20-user%3AVikingDeng%20is%3Apublic&label=open%20upstream%20PRs&color=238636)](https://github.com/search?q=author%3AVikingDeng+is%3Apr+is%3Aopen+-user%3AVikingDeng&type=pullrequests)

## Open source
- **Project:** one-line summary [#123](link)
-->

## MoE inference on Ascend

**Huawei Ascend AI Innovation Contest 2025, MoE track — Silver Award, team lead**

Optimized DeepSeek-MoE-16B and Qwen1.5-MoE-A2.7B inference (MindSpore / MindNLP) with zero accuracy loss.

- Profiling showed MoE MLP costing ~20× attention, so the work focused on expert dispatch and GEMM.
- **Prefill:** sorted tokens by expert and turned ragged dispatch into padded `[E, T_max, H]` batched matmuls (Pad → BMM → Gather/ScatterAdd).
- **Decode:** stacked the active experts' gate/up/down weights for batched top-k BMM; FP32 accumulation removed output mismatch.
- **Result:** overall score 263.4 → 353.7 (**+34.3%**), peak memory **−15.4%**.

## Experience

**ByteDance** — Backend / Agent Intern, Intelligent Creation · 2026.04 – 2026.09

**Shopee** — Backend Intern, SRA High-Performance Computing Platform · 2025.11 – 2026.03
- Built two-level request / candidate execution plans for an Apache Arrow ranking-feature engine (C++): candidate-independent subgraphs run once per request, per-candidate work runs as columnar batches, verified by a differential tester against the legacy path.
- Hot-reloaded plans as immutable snapshots with validated atomic swap; traced a production core dump (overwritten `ListArray` offsets) with GDB to an out-of-bounds write and fixed it.

## Research

First-author papers, under review at AAAI 2027:
- **GazeSieve** — training-free, gaze-guided evidence selection for egocentric video QA, with a new benchmark of 99 videos and 2,607 human-annotated cases.
- **CAVI-Bubble** — inference-time completion control for aerial vision-language navigation on a frozen 7B policy; success rate 34.3% → 41.5%.

## Projects

- [cockroachdb-agentic-memory](https://github.com/VikingDeng/cockroachdb-agentic-memory) — persistent memory layer for AI agents: MCP server + HNSW vector indexing on CockroachDB, deployed on AWS (hackathon).

## Awards

- Huawei Ascend AI Innovation Contest 2025, MoE track — Silver Award (team lead)
- Beijing College Students Mathematics Competition — First Prize ×2

## Skills

**Languages:** C++, Python · **ML:** PyTorch, MindSpore, CUDA · **Systems:** Apache Arrow, Linux, GDB, profiling
