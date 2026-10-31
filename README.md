<div align="center">

# Prajwal Pujari

### `AI/ML Systems & High-Performance Inference Engineer`

Building continuous-batching LLM runtimes, Paged KV-cache memory allocators, and capacity load-testing harnesses from first principles.

[![PyPI Profile](https://img.shields.io/badge/PyPI-Prajwal2002PI-3775A9?style=flat-square&logo=pypi&logoColor=white)](https://pypi.org/user/Prajwal2002PI/)
[![Portfolio](https://img.shields.io/badge/Workstation-Live_Portfolio-06b6d4?style=flat-square&logo=vercel&logoColor=white)](https://prajwal-pujari.vercel.app)
[![Engineering Notes](https://img.shields.io/badge/Notes-Deep_Dives-10b981?style=flat-square&logo=readme&logoColor=white)](https://prajwal-pujari.vercel.app/blog/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/prajwal-pujari-mn9964)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-Direct_Chat-25D366?style=flat-square&logo=whatsapp&logoColor=white)](https://wa.me/916360012214?text=Hi%20Prajwal,%20I%20saw%20your%20GitHub%20profile.)
[![Email](https://img.shields.io/badge/Email-prajwalpujari16@gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:prajwalpujari16@gmail.com)

<br/>

> **Hardware-Calibrated Runtimes · Zero CUDA OOMs · Zero-Cost Abstractions**  
> Empirical roofline modeling, zero-copy physical block gathering, and verified cryptographic provenance.

</div>

---

### ⚡ Quick Verification

```bash
# Profile local server capacity (Ollama, vLLM, llama.cpp) with automated roofline tuning
pip install servebench && servebench quick

# Pre-flight analytical capacity planning, multi-GPU matrix & cloud $/1M tokens (zero GPU needed)
pip install infersize && infersize compare --model qwen2.5-7b --quant fp16

# Run continuous batching with paged KV-cache (pure PyTorch, zero C++/CUDA build steps)
pip install mini-infer

# Discrete-event serving simulator with Radix prefix caching & Perfetto trace export
pip install sched-sim && sched-sim run --scheduler cache-aware --trace sharegpt

# Quantization engine & Pareto evaluation benchmark (INT4/INT8/BitNet 1.58b)
pip install quantbench-engine && quantbench pack-inspect --scheme int4
```

---

### 📌 Systems Matrix

| Flagship | Core Architecture | Empirical Silicon Numbers | Release & Provenance |
|:---|:---|:---|:---:|
| **[servebench](https://github.com/Prajwal7-2002/servebench)** | LLM serving capacity load-tester & auto-tuning harness (`servebench tune`). Multi-trial repeats with 95% CIs and synchronized NVML GPU telemetry. | • Honest p99 ($N \ge 100$)<br>• MBU roofline profiling<br>• Slot / Queue / Bandwidth diagnostics | [![PyPI](https://img.shields.io/pypi/v/servebench.svg?color=blue)](https://pypi.org/project/servebench/)<br>[![Sigstore](https://img.shields.io/badge/Sigstore-Verified_Provenance-success)](https://pypi.org/project/servebench/#security)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/servebench/) |
| **[mini-infer](https://github.com/Prajwal7-2002/mini-infer)** | Lightweight continuous-batching LLM runtime in pure PyTorch for Qwen2.5. Iteration-level dynamic scheduler, Paged KV-cache virtual memory, radix prefix caching, and Leviathan speculative verifier. | • **27.0 tok/s** at c=4 (+130.8%)<br>• **2.04 Tok/Joule** (13.2 W)<br>• **<3.8%** KV-cache waste | [![PyPI](https://img.shields.io/pypi/v/mini-infer.svg?color=blue)](https://pypi.org/project/mini-infer/)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/mini-infer/) |
| **[sched-sim](https://github.com/Prajwal7-2002/sched-sim)** | Discrete-event LLM serving simulator with first-principles roofline latency models, SGLang-style Radix prefix caching, and Perfetto trace visualizer. | • **0.87s** full sweep<br>• **87%** test coverage<br>• **0-copy** prefix hits | [![PyPI](https://img.shields.io/pypi/v/sched-sim.svg?color=blue)](https://pypi.org/project/sched-sim/)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/sched-sim/) |
| **[quantbench](https://github.com/Prajwal7-2002/quantbench)** | Unified from-scratch quantization engine (INT4/INT8/FP8/BitNet 1.58b), vectorized sub-byte packing, Ampere 2:4 structured sparsity, dynamic `QuantLinear` layers, and dual-metric Pareto evaluation benchmark. | • **3.5x** INT4 / **7.5x** BitNet<br>• **47/47** tests pass (95%)<br>• **0-copy** hook dequant | [![PyPI](https://img.shields.io/pypi/v/quantbench-engine.svg?color=blue)](https://pypi.org/project/quantbench-engine/)<br>[![GitHub](https://img.shields.io/badge/GitHub-quantbench-black?logo=github)](https://github.com/Prajwal7-2002/quantbench) |
| **[infersize](https://github.com/Prajwal7-2002/infersize)** | Pre-flight analytical performance modeling, multi-GPU comparison matrix, and cloud TCO ($/1M tokens) capacity planner. Zero GPU required, dynamic Hugging Face Hub ingestion, MoE active routing, and Architecture RFC export. | • **<10 ms** CPU solve<br>• **36/36** tests pass (95%)<br>• **Zero GPU** required | [![GitHub](https://img.shields.io/badge/GitHub-infersize_v0.2.0-black?logo=github)](https://github.com/Prajwal7-2002/infersize)<br>[![CI](https://github.com/Prajwal7-2002/infersize/actions/workflows/ci.yml/badge.svg)](https://github.com/Prajwal7-2002/infersize/actions) |
| **[EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM)** | Air-gapped document sensitivity classifier and Tier-1 DLP secret scanner for edge CPU inference. | • **20+** HF downloads (v3)<br>• **6.7×** dynamic batching<br>• **100%** secret recall | [![HF Model](https://img.shields.io/badge/🤗_HuggingFace-EdgeSLM--0.5b--v3-yellow)](https://huggingface.co/prajwalpujari16/EdgeSLM-qwen0.5b-v3)<br>[![HF Downloads](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fhuggingface.co%2Fapi%2Fmodels%2Fprajwalpujari16%2FEdgeSLM-qwen0.5b-v3&query=%24.downloads&label=%F0%9F%A4%97%20Downloads&color=blue)](https://huggingface.co/prajwalpujari16/EdgeSLM-qwen0.5b-v3)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/EdgeSLM/) |
| **[Menmo](https://menmo-app.netlify.app/)** | Hybrid retrieval RAG service (Pinecone MiniLM + BM25) with dynamic fallback and page-level source citations. | • Scoped multi-tenant search<br>• Zero-hallucination routing<br>• Django + Next.js decoupled | [Live App →](https://menmo-app.netlify.app/)<br>[Backend](https://github.com/Prajwal7-2002/menmo-backend) · [Frontend](https://github.com/Prajwal7-2002/menmo-frontend) |

---

### 🔬 Engineering Approach & Negative Results

I believe that engineering credibility is built by documenting trade-offs, architectural failures, and hardware bounds alongside performance gains:

* **Naive KV-Allocation Fails Under Dynamic Lengths**:  
  Pre-allocating contiguous tensor buffers for worst-case context lengths wasted **>60% of GPU memory** due to internal and external fragmentation. Fixed by implementing fixed 16-token physical block pools with virtual-to-physical block tables in pure PyTorch, cutting memory waste to **<3.8%**.
* **Unbatched Iteration Bottlenecks on DRAM Memory Bandwidth**:  
  Stepping concurrent sequences through serial model calls forced the GPU to stream model weights from DRAM 4 separate times per step (capping decode at 11.7 tok/s on an RTX 3050). Switching to zero-copy physical block gathering streams weights **exactly once per step across all sequences**, jumping throughput to **27.0 tok/s (+130.8%)** and delivering **2.04 Tok/Joule**.
* **Synthetic LoRA Overfitting on Edge Models**:  
  Initial LoRA fine-tunes on synthetic compliance data showed high train accuracy but collapsed on real-world document formatting. Implemented contrastive evaluation pairs and McNemar significance testing ($p = 0.043$) to validate generalization before exporting to 392 MB ONNX INT4.
* **No Cherry-Picked Latency Metrics**:  
  Single-run p99 latency spikes are statistically deceptive without sufficient sample size. `servebench` strictly enforces $N \ge 100$ before calculating p99 percentiles, and reports 95% confidence intervals across multi-trial repeats.

---

### 📝 Engineering Notes & Deep Dives

* **[Roofline Benchmarking & Auto-Tuning LLM Serving: How We Pushed Pure PyTorch to 27 tok/s](https://prajwal-pujari.vercel.app/blog/posts/roofline-serving-benchmarks.html)** (`2026-10-23`)  
  *Measuring empirical Memory Bandwidth Utilization (MBU), saturation knees, and multi-stream batching to eliminate TTFT degradation on consumer laptop GPUs.*
* **[Why Naive KV-Caches Waste >60% VRAM (And How Paged Memory Fixes It)](https://prajwal-pujari.vercel.app/blog/posts/paged-kv-cache-vram.html)** (`2026-10-22`)  
  *How replacing contiguous memory allocations with 16-token physical blocks and virtual table mapping brings production PagedAttention to pure PyTorch.*

---

### 🛠️ Technical Competencies & Stack

```
Runtime Systems   : Paged KV-Cache Allocators · Continuous Batching · Radix Prefix Caching · Speculative Decoding · Discrete-Event Simulation
Silicon Profiling : Roofline MBU Modeling · NVML Telemetry · Saturation Knee Detection · TTFT / ITL / TPOT Analysis
Core Stack        : PyTorch (SDPA, Tensor Gathers) · Python 3.10+ · CUDA / NVML · ONNX Runtime INT4 · Hugging Face
Serving & Infra   : FastAPI · Asyncio / Aiohttp · SSE Streaming · vLLM · Ollama · Docker · GitHub Actions CI/CD
Security & Trust  : PyPI Trusted Publishers (OIDC) · Sigstore Cryptographic Attestation · Zero-Secret Airgap DLP
```

---

### 📫 Connect & Collaborate

* **Portfolio:** [prajwal-pujari.vercel.app](https://prajwal-pujari.vercel.app)
* **PyPI Packages:** [pypi.org/user/Prajwal2002PI](https://pypi.org/user/Prajwal2002PI/)
* **LinkedIn:** [linkedin.com/in/prajwal-pujari-mn9964](https://www.linkedin.com/in/prajwal-pujari-mn9964)
* **Email:** [prajwalpujari16@gmail.com](mailto:prajwalpujari16@gmail.com)
* **WhatsApp:** [Direct Chat (WhatsApp ↗)](https://wa.me/916360012214?text=Hi%20Prajwal,%20I%20saw%20your%20GitHub%20profile.)
