<div align="center">

# Prajwal Pujari

### `AI/ML Systems & High-Performance Inference Engineer`

Building continuous-batching LLM runtimes, Paged KV-cache memory allocators, sub-byte bit-packers, and empirical serving benchmarks from first principles.

[![HuggingFace Profile](https://img.shields.io/badge/🤗_HuggingFace-prajwalpujari16-yellow?style=flat-square)](https://huggingface.co/prajwalpujari16)
[![PyPI Profile](https://img.shields.io/badge/PyPI-Prajwal2002PI-3775A9?style=flat-square&logo=pypi&logoColor=white)](https://pypi.org/user/Prajwal2002PI/)
[![Portfolio](https://img.shields.io/badge/Workstation-Live_Portfolio-06b6d4?style=flat-square&logo=vercel&logoColor=white)](https://prajwal-pujari.vercel.app)
[![Engineering Notes](https://img.shields.io/badge/Notes-Deep_Dives-10b981?style=flat-square&logo=readme&logoColor=white)](https://prajwal-pujari.vercel.app/blog/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/prajwal-pujari-mn9964)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-Direct_Chat-25D366?style=flat-square&logo=whatsapp&logoColor=white)](https://wa.me/916360012214?text=Hi%20Prajwal,%20I%20saw%20your%20GitHub%20profile.)
[![Email](https://img.shields.io/badge/Email-prajwalpujari16@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:prajwalpujari16@gmail.com)

<br/>

> **Hardware-Measured Runtimes · Honest Benchmarks · Client-Side Interactive Studios**  
> Empirical roofline modeling, zero-copy physical block gathering, and verified cryptographic provenance.  
> **Portfolio Health: 529 tests passed, 0 failed (6 skipped) in CI across 9 core repositories.**

</div>

---

### 🌐 Live Hugging Face Interactive Studios (0ms Cold Start, 100% Client-Side)

All studios are deployed as permanent, zero-cold-start static web applications on Hugging Face Spaces (`sdk: static`) with interactive client-side execution:

| Studio | Space Link | Interactive Capabilities |
|:---|:---|:---|
| **`streamspec`** | [**prajwalpujari16/streamspec**](https://huggingface.co/spaces/prajwalpujari16/streamspec) | **Speculative Layer-Streaming Studio**: Live memory bus Gantt simulator (AirLLM 1-token crawl vs StreamSpec batched GEMM), double-buffered prefetch pipeline inspector, and Williams Roofline capacity CAD. |
| **`token-atlas`** | [**prajwalpujari16/token-atlas**](https://huggingface.co/spaces/prajwalpujari16/token-atlas) | **Multilingual Token Inflation Tax Explorer**: 52-language FLORES-200 inflation matrix & token fertility multipliers (published benchmark: GPT-4 and GPT-4o), multi-domain benchmarks, and cost router. |
| **`infersize`** | [**prajwalpujari16/infersize**](https://huggingface.co/spaces/prajwalpujari16/infersize) | **LLM Capacity Planning CAD**: Pre-flight analytical VRAM sizing, multi-GPU comparison matrix, speculative decoding latency sizer, and cloud TCO ($/1M tokens) estimator. |
| **`quantbench`** | [**prajwalpujari16/quantbench**](https://huggingface.co/spaces/prajwalpujari16/quantbench) | **Sub-Byte Quantization Studio**: SQNR-vs-compression Pareto frontier explorer, live BitNet 1.58b / INT4 / 2:4 sparsity bit-packing registers, and Transformer layer sensitivity simulator. |
| **`sched-sim`** | [**prajwalpujari16/sched-sim**](https://huggingface.co/spaces/prajwalpujari16/sched-sim) | **Discrete-Event Serving Scheduler**: Animated Gantt player demonstrating Head-of-Line prefill blocking vs. Sarathi Chunked Prefill ($C=512$), SJF, and Disaggregated serving. |
| **`mini-infer`** | [**prajwalpujari16/mini-infer**](https://huggingface.co/spaces/prajwalpujari16/mini-infer) | **PagedAttention GPU Memory Pool**: Interactive virtual block table allocator, copy-on-write radix prefix caching simulator, and speculative decoding acceptance verifier. |
| **`runsonmine`** | [**prajwalpujari16/runsonmine**](https://huggingface.co/spaces/prajwalpujari16/runsonmine) | **Empirical Silicon LLM Benchmark Registry**: 24 physical measurements on Dual Tesla T4 & RTX 3050 Laptop, concurrency scaling curves ($c=1 \to 8$), and 1-click PR submission portal. |

---

### 📦 Hugging Face Benchmark Datasets

| Dataset | Hub Link | Verified Contents |
|:---|:---|:---|
| **`token-atlas-benchmark`** | [prajwalpujari16/token-atlas-benchmark](https://huggingface.co/datasets/prajwalpujari16/token-atlas-benchmark) | 52-language FLORES-200 benchmark & token inflation metrics for GPT-4 and GPT-4o. |
| **`quantbench-pareto`** | [prajwalpujari16/quantbench-pareto](https://huggingface.co/datasets/prajwalpujari16/quantbench-pareto) | 12-configuration Pareto frontier + 28 layer sensitivity rows. **Illustrative values** (generated on a small synthetic model); real-model results are in the repo's DEVLOG. |
| **`llm-serving-traces`** | [prajwalpujari16/llm-serving-traces](https://huggingface.co/datasets/prajwalpujari16/llm-serving-traces) | 165 real serving traces (LMSYS/RAG/CodeGen) + 15 scheduler comparisons + 12 silicon validation rows. |
| **`consumer-silicon-benchmarks`** | [prajwalpujari16/consumer-silicon-benchmarks](https://huggingface.co/datasets/prajwalpujari16/consumer-silicon-benchmarks) | 24 empirical data points on Dual Tesla T4 & RTX 3050 Laptop + 6-step concurrency curve. |

---

### ⚡ 1-Line Quick Verification

```bash
# 1. Profile local server capacity (Ollama, vLLM, llama.cpp) with automated roofline tuning
pip install servebench && servebench quick

# 2. Pre-flight analytical capacity planning, multi-GPU matrix & cloud $/1M tokens (zero GPU needed)
pip install infersize && infersize compare --model qwen2.5-7b --quant fp16

# 3. Continuous-batching inference runtime with Paged KV-cache (pure PyTorch, zero C++ build steps)
pip install mini-infer

# 4. Discrete-event serving simulator with Radix prefix caching & chunked prefill
pip install sched-sim && sched-sim run --scheduler chunked --chunk-budget 512

# 5. From-scratch quantization engine & Pareto evaluation benchmark (INT4/INT8/FP8/BitNet 1.58b)
pip install quantbench-engine && quantbench pack-inspect --format int4

# 6. Multilingual token inflation tax analyzer across 52 languages
pip install token-atlas-engine && token-atlas compare --text "Hello world"

# 7. Asynchronous Speculative Layer-Streaming for 70B & DeepSeek-R1 on consumer VRAM
pip install streamspec && streamspec demo
```

---

### 📌 Systems Engineering Flagship Matrix

| Flagship | Core Architecture | Empirical Silicon Numbers | Release & Provenance |
|:---|:---|:---|:---:|
| **[streamspec](https://github.com/Prajwal7-2002/streamspec)** | Asynchronous Speculative Layer-Streaming engine for 70B & DeepSeek-R1 models on consumer VRAM (8–16 GB). Fast in-memory draft scout (0.5B), double-buffered async prefetcher (>90% bus overlap), zero-extra-sweep round optimization, online dynamic adaptive K controller, single-pass batched GEMM sweeps, Multi-Head Latent Attention (MLA) latent KV compression, and exact Leviathan distribution verification. | • **1.85x** fewer weight sweeps (Qwen2.5 1.5B + 0.5B draft, measured)<br>• **93.9%** prefetch overlap (measured, CUDA)<br>• **~7x** MLA KV reduction (test config)<br>• **14/14** tests pass (100%) | [![PyPI](https://img.shields.io/pypi/v/streamspec.svg?color=blue)](https://pypi.org/project/streamspec/)<br>[![HF Space](https://img.shields.io/badge/🤗_HF_Space-Studio-blue)](https://huggingface.co/spaces/prajwalpujari16/streamspec)<br>[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Prajwal7-2002/streamspec/blob/main/notebooks/streamspec_70b_benchmark.ipynb)<br>[![CI](https://github.com/Prajwal7-2002/streamspec/actions/workflows/ci.yml/badge.svg)](https://github.com/Prajwal7-2002/streamspec/actions) |
| **[mini-infer](https://github.com/Prajwal7-2002/mini-infer)** | Lightweight continuous-batching LLM runtime in pure PyTorch for Qwen2.5. Iteration-level dynamic scheduler, Paged KV-cache with sub-byte INT4/FP8 compression, radix prefix caching, and Leviathan speculative verifier. | • **27.0 tok/s** at c=4 vs **11.7** before batching (RTX 3050, 12 requests/level)<br>• **2.04 Tok/Joule** (13.2 W)<br>• **-72.7%** KV-cache size with INT4 (calculated)<br>• **70/70** tests pass (100%) | [![PyPI](https://img.shields.io/pypi/v/mini-infer.svg?color=blue)](https://pypi.org/project/mini-infer/)<br>[![HF Space](https://img.shields.io/badge/🤗_HF_Space-Studio-blue)](https://huggingface.co/spaces/prajwalpujari16/mini-infer)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-teal)](https://prajwal7-2002.github.io/mini-infer/) |
| **[servebench](https://github.com/Prajwal7-2002/servebench)** | LLM serving capacity load-tester & auto-tuning harness (`servebench tune`). Multi-trial repeats with 95% CIs and synchronized NVML GPU telemetry. | • Warns when p99 rests on <100 samples<br>• MBU roofline profiling<br>• Slot/Queue/Bandwidth diagnostics<br>• **173/173** tests pass (100%) | [![PyPI](https://img.shields.io/pypi/v/servebench.svg?color=blue)](https://pypi.org/project/servebench/)<br>[![Sigstore](https://img.shields.io/badge/Sigstore-Verified_Provenance-success)](https://pypi.org/project/servebench/#security)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-teal)](https://prajwal7-2002.github.io/servebench/) |
| **[quantbench](https://github.com/Prajwal7-2002/quantbench)** | Unified from-scratch quantization engine (INT4/INT8/FP8/BitNet 1.58b), vectorized sub-byte packing, Ampere 2:4 structured sparsity, dynamic `QuantLinear` layers, and dual-metric Pareto evaluation benchmark. | • INT4: **2.08x** smaller on Qwen2.5-0.5B (+21% perplexity, measured)<br>• **3.5x** INT4 per layer (theoretical)<br>• **47** pass · **6** skipped (95% cov) | [![PyPI](https://img.shields.io/pypi/v/quantbench-engine.svg?color=blue)](https://pypi.org/project/quantbench-engine/)<br>[![HF Space](https://img.shields.io/badge/🤗_HF_Space-Studio-blue)](https://huggingface.co/spaces/prajwalpujari16/quantbench)<br>[![HF Dataset](https://img.shields.io/badge/🤗_HF_Dataset-Pareto-yellow)](https://huggingface.co/datasets/prajwalpujari16/quantbench-pareto)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-teal)](https://prajwal7-2002.github.io/quantbench/) |
| **[sched-sim](https://github.com/Prajwal7-2002/sched-sim)** | Discrete-event LLM serving simulator with first-principles roofline latency models, SGLang-style Radix prefix caching, Sarathi chunked prefill, and Perfetto trace visualizer. | • Held-out validation on real runs: TPOT within **±12%** on 6/7 Ollama rows<br>• TTFT prediction still off for larger models ([results](https://github.com/Prajwal7-2002/sched-sim/blob/main/benchmarks/RESULTS.md))<br>• **45/45** tests pass (87% cov) | [![PyPI](https://img.shields.io/pypi/v/sched-sim.svg?color=blue)](https://pypi.org/project/sched-sim/)<br>[![HF Space](https://img.shields.io/badge/🤗_HF_Space-Studio-blue)](https://huggingface.co/spaces/prajwalpujari16/sched-sim)<br>[![HF Dataset](https://img.shields.io/badge/🤗_HF_Dataset-Traces-yellow)](https://huggingface.co/datasets/prajwalpujari16/llm-serving-traces)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-teal)](https://prajwal7-2002.github.io/sched-sim/) |
| **[infersize](https://github.com/Prajwal7-2002/infersize)** | Pre-flight analytical performance modeling, multi-GPU comparison matrix, speculative decoding sizer, and cloud TCO ($/1M tokens) capacity planner. Interactive Web Studio, NVML hardware fit verifier, and dynamic Hugging Face Hub ingestion. | • **~10–20 ms** per comparison on a laptop CPU<br>• **60/60** tests pass (88% cov)<br>• **Zero GPU** required | [![PyPI](https://img.shields.io/pypi/v/infersize.svg?color=blue)](https://pypi.org/project/infersize/)<br>[![HF Space](https://img.shields.io/badge/🤗_HF_Space-Studio-blue)](https://huggingface.co/spaces/prajwalpujari16/infersize)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-teal)](https://prajwal7-2002.github.io/infersize/) |
| **[token-atlas](https://github.com/Prajwal7-2002/token-atlas)** | Universal multilingual tokenizer efficiency benchmark & global linguistic inflation atlas. Analyzes 52 languages, multi-domain benchmarks (Code, Indentation, Tool Schemas), cost router, and prompt minifier. | • **52** languages analyzed<br>• GPT-4 & GPT-4o in published benchmark<br>• **43/43** tests pass (94% cov)<br>• **0ms** interactive playground | [![PyPI](https://img.shields.io/pypi/v/token-atlas-engine.svg?color=blue)](https://pypi.org/project/token-atlas-engine/)<br>[![HF Space](https://img.shields.io/badge/🤗_HF_Space-Studio-blue)](https://huggingface.co/spaces/prajwalpujari16/token-atlas)<br>[![HF Dataset](https://img.shields.io/badge/🤗_HF_Dataset-Benchmark-yellow)](https://huggingface.co/datasets/prajwalpujari16/token-atlas-benchmark)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-teal)](https://prajwal7-2002.github.io/token-atlas/) |
| **[runsonmine](https://github.com/Prajwal7-2002/runsonmine)** | Community database of measured (not estimated) LLM inference speeds on real consumer silicon (laptops, desktops, Macs). | • **24** empirical runs<br>• **26/26** tests pass (100%) | [![HF Space](https://img.shields.io/badge/🤗_HF_Space-Studio-blue)](https://huggingface.co/spaces/prajwalpujari16/runsonmine)<br>[![HF Dataset](https://img.shields.io/badge/🤗_HF_Dataset-Benchmarks-yellow)](https://huggingface.co/datasets/prajwalpujari16/consumer-silicon-benchmarks)<br>[![GitHub](https://img.shields.io/badge/GitHub-runsonmine-black?logo=github)](https://github.com/Prajwal7-2002/runsonmine) |
| **[EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM)** | Air-gapped document sensitivity classifier and Tier-1 DLP secret scanner for edge CPU inference. | • **26** HF downloads (v3, all-time)<br>• **6.7×** dynamic batching<br>• **51/51** tests pass (100%) | [![HF Model](https://img.shields.io/badge/🤗_HuggingFace-EdgeSLM--0.5b--v3-yellow)](https://huggingface.co/prajwalpujari16/EdgeSLM-qwen0.5b-v3)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-teal)](https://prajwal7-2002.github.io/EdgeSLM/) |

---

### 🧩 Upstream Contributions (Merged)

Production bugfixes and architectural patches merged into leading LLM SDKs, inference engines, and quantization runtimes:

* **[ModelCloud/GPTQModel](https://github.com/ModelCloud/GPTQModel)**:
  * [**#5175**](https://github.com/ModelCloud/GPTQModel/pull/5175) — Bounded token-row activation capture and streaming reservoir for AWQ & ParoQuant, eliminating linear host RAM explosion during calibration ([#5137](https://github.com/ModelCloud/GPTQModel/issues/5137)).
  * [**#4399**](https://github.com/ModelCloud/GPTQModel/pull/4399) — Omitted forced `offload_state_dict` to prevent unintended `TMPDIR` disk copies during model loading ([#4385](https://github.com/ModelCloud/GPTQModel/issues/4385)).
  * [**#4145**](https://github.com/ModelCloud/GPTQModel/pull/4145) — Preserved Bloom AWQ module forward replay inputs (`residual`, `alibi`, `mask`) and reject unsafe norm folds.
  * [**#4142**](https://github.com/ModelCloud/GPTQModel/pull/4142) — Scoped deterministic PyTorch algorithms in GPU weighted k-means (VPTQ).
  * [**#4096**](https://github.com/ModelCloud/GPTQModel/pull/4096) — Repaired `hf_repack_layer` and `hf_pack_layer` GPTQ v1 qzero bit-packing alignment.
  * [**#4029**](https://github.com/ModelCloud/GPTQModel/pull/4029) — Standardized multi-EOS stop lists, tokenizer output unpacking, and OpenAI/vLLM request parsing.
* **[mozilla-ai/any-llm](https://github.com/mozilla-ai/any-llm)**:
  * [**#1650**](https://github.com/mozilla-ai/any-llm/pull/1650) — Replaced `@abstractmethod` completion/embedding converter stubs on `AnyLLM` with non-abstract `NotImplementedError` defaults, eliminating boilerplate stubs across capability-restricted providers ([#1486](https://github.com/mozilla-ai/any-llm/issues/1486)).

---

### 🔬 Engineering Approach & Systems Insights

I believe that engineering credibility is built by documenting trade-offs, architectural failures, and hardware bounds alongside performance gains:

* **Naive KV-Allocation Fails Under Dynamic Lengths**:  
  Pre-allocating contiguous buffers for a 2,048-token worst case reserves the full 1,280 MB per stream even for a 48-token reply. Fixed 16-token physical block pools with virtual-to-physical block tables in pure PyTorch allocate memory as sequences grow: about **30 MB** for that reply (calculated from tensor sizes).
* **Unbatched Iteration Bottlenecks on DRAM Memory Bandwidth**:  
  Stepping concurrent sequences through serial model calls forced the GPU to stream model weights from DRAM 4 separate times per step (capping decode at 11.7 tok/s on an RTX 3050). Switching to zero-copy physical block gathering streams weights **exactly once per step across all sequences**, jumping throughput to **27.0 tok/s (+130.8%)** and delivering **2.04 Tok/Joule**.
* **Head-of-Line Prefill Starvation Under Continuous Batching**:  
  In standard FCFS continuous batching, a 2,048-token prompt prefill monopolizes the compute pipeline for >120ms, causing active decoding streams to stutter with severe TPOT latency spikes. In `sched-sim` simulations, Sarathi-style **Chunked Prefill ($C=512$)** interleaves prompt chunks with decodes and keeps TPOT under 40ms without hurting throughput (simulated, not yet validated on silicon).
* **Memory Savings Are Not Speed Savings Without Fused Kernels**:  
  On Qwen2.5-0.5B (RTX 3050), `quantbench` INT4 shrank the model from **958 MB to 461 MB** but raised perplexity **+21%** and ran at **0.18x** bf16 speed, because the reference runtime dequantizes full weights every forward pass. Post-hoc ternary quantization destroyed the model entirely. Bandwidth savings need fused dequant-matmul kernels.
* **No Cherry-Picked Latency Metrics**:  
  Single-run p99 latency spikes are statistically deceptive without sufficient sample size. `servebench` warns when a p99 rests on fewer than 100 requests (it then approximates the sample maximum), and reports 95% confidence intervals across multi-trial repeats.

---

### 📝 Engineering Notes & Deep Dives

* **[The Hidden Token Tax: Why Multilingual LLM APIs Cost Up to 4.5× More](https://prajwal-pujari.vercel.app/blog/posts/token-inflation-multilingual-tax.html)** (`2026-11-13`)  
  *Why non-English prompts face extreme Byte-Pair Encoding fragmentation, how 4-space Python and JSON tool schemas add 2.6× token bloat, and how modern tokenizers (Qwen, Tekken, DeepSeek) rebalance API economics across 52 languages.*
* **[Roofline Benchmarking & Auto-Tuning LLM Serving: How We Pushed Pure PyTorch to 27 tok/s](https://prajwal-pujari.vercel.app/blog/posts/roofline-serving-benchmarks.html)** (`2026-10-23`)  
  *Measuring empirical Memory Bandwidth Utilization (MBU), saturation knees, and multi-stream batching to eliminate TTFT degradation on consumer laptop GPUs.*
* **[Why Naive KV-Caches Waste >60% VRAM (And How Paged Memory Fixes It)](https://prajwal-pujari.vercel.app/blog/posts/paged-kv-cache-vram.html)** (`2026-10-22`)  
  *How replacing contiguous memory allocations with 16-token physical blocks and virtual table mapping brings production PagedAttention to pure PyTorch.*

---

### 🛠️ Technical Competencies & Systems Stack

```
Runtime Systems   : Paged KV-Cache Allocators · Continuous Batching · Radix Prefix Caching · Speculative Decoding · Discrete-Event Simulation
Silicon Profiling : Roofline MBU Modeling · NVML Telemetry · Saturation Knee Detection · TTFT / ITL / TPOT Analysis
Core Stack        : PyTorch (SDPA, Tensor Gathers) · Python 3.10+ · CUDA / NVML · ONNX Runtime INT4 · Hugging Face
Quantization      : Symmetric AbsMax · INT4 Blockwise · BitNet 1.58b Ternary · Ampere 2:4 Structured Sparsity · SmoothQuant · AWQ / GPTQ
Serving & Infra   : FastAPI · Asyncio / Aiohttp · SSE Streaming · vLLM · Ollama · Docker · GitHub Actions CI/CD
Security & Trust  : PyPI Trusted Publishers (OIDC) · Sigstore Cryptographic Attestation · Zero-Secret Airgap DLP
```

---

### 📫 Connect & Collaborate

* **Portfolio Website:** [prajwal-pujari.vercel.app](https://prajwal-pujari.vercel.app)
* **Hugging Face Hub:** [huggingface.co/prajwalpujari16](https://huggingface.co/prajwalpujari16)
* **PyPI Packages:** [pypi.org/user/Prajwal2002PI](https://pypi.org/user/Prajwal2002PI/)
* **LinkedIn:** [linkedin.com/in/prajwal-pujari-mn9964](https://www.linkedin.com/in/prajwal-pujari-mn9964)
* **Email:** [prajwalpujari16@gmail.com](mailto:prajwalpujari16@gmail.com)
