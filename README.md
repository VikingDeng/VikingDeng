### Hi, I'm Weijian Deng

I'm a master's student at Beihang University (AI track, 2025–2028). I did my undergrad in computer science at Beihang too. These days I mostly work on LLM systems, especially MoE inference and the performance side of training.

I'm looking for a 2027 internship in LLM training or inference infrastructure. You can reach me at emmmvkdeng@gmail.com.

<!-- 第一个上游 PR 提交后取消注释：
**Open source**
- Megatron-LM: one-line summary (#123)
-->

**MoE inference on Ascend.** I led our team in the MoE track of Huawei's 2025 Ascend AI contest, where we won silver. The goal was to speed up DeepSeek-MoE-16B and Qwen1.5-MoE-A2.7B on Ascend NPUs with no accuracy loss. Profiling showed the MoE layers taking about 20x as long as attention, so most of our work went into expert dispatch. In prefill we grouped tokens by expert and ran each expert as one batched matmul; in decode we stacked the active experts' weights together. The score went from 263.4 to 353.7, and peak memory dropped by 15%.

**Shopee** (backend intern, Nov 2025 – Mar 2026). I worked on a C++ service built on Apache Arrow that computes ranking features. I split execution into a per-request part and a batched per-candidate part, so anything that doesn't depend on the candidate runs once per request, and wrote a differential tester to check it against the old path. I also traced a production crash from a core dump back to an out-of-bounds write.

**ByteDance** (backend / agent intern, Apr – Sep 2026).

**Research.** I have two first-author papers under review at AAAI 2027: GazeSieve, on using eye gaze to pick frames for egocentric video QA, and CAVI-Bubble, on teaching a drone navigation agent when to stop.

Outside of that: a hackathon project on [agent memory with CockroachDB](https://github.com/VikingDeng/cockroachdb-agentic-memory), and two first prizes in the Beijing college math competition.
