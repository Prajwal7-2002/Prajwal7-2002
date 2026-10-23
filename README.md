# Prajwal Pujari

**AI/ML Systems & Inference Engineer**  
Building continuous-batching LLM inference engines, Paged KV-cache allocators, and capacity load-testing harnesses from first principles.

[🌐 Portfolio](https://prajwal-pujari.vercel.app) &nbsp;·&nbsp; [📝 Engineering Notes](https://prajwal-pujari.vercel.app/blog/) &nbsp;·&nbsp; [💼 LinkedIn](https://www.linkedin.com/in/prajwal-pujari-mn9964) &nbsp;·&nbsp; [📫 Email](mailto:prajwalpujari16@gmail.com)

---

### ⚡ Quick Verification

```bash
# Profile local server capacity (Ollama, vLLM, llama.cpp) in 60 seconds
pip install servebench && servebench quick

# Run continuous batching with paged KV-cache (pure PyTorch, zero C++/CUDA build steps)
pip install mini-infer
```

---

### 📌 Systems Matrix

| Flagship | Core Architecture | Empirical Silicon Numbers | Release & Provenance |
|:---|:---|:---|:---:|
| **[servebench](https://github.com/Prajwal7-2002/servebench)** | LLM serving capacity load-tester & auto-tuning harness (`servebench tune`). Multi-trial repeats with 95% CIs and synchronized NVML GPU telemetry. | • Honest p99 ($N \ge 100$)<br>• MBU roofline profiling<br>• Slot / Queue / Bandwidth diagnostics | [![PyPI](https://img.shields.io/pypi/v/servebench.svg?color=blue)](https://pypi.org/project/servebench/)<br>[![Sigstore](https://img.shields.io/badge/Sigstore-Verified_Provenance-success)](https://pypi.org/project/servebench/#security)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/servebench/) |
| **[mini-infer](https://github.com/Prajwal7-2002/mini-infer)** | Lightweight continuous-batching LLM runtime in pure PyTorch for Qwen2.5. Iteration-level dynamic scheduler, radix prefix caching, and Leviathan speculative verifier. | • **27.0 tok/s** at c=4 (+130.8%)<br>• **2.04 Tok/Joule** (13.2 W)<br>• **<3.8%** KV-cache waste | [![PyPI](https://img.shields.io/pypi/v/mini-infer.svg?color=blue)](https://pypi.org/project/mini-infer/)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/mini-infer/) |
| **[EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM)** | Air-gapped document sensitivity classifier and Tier-1 DLP secret scanner for edge CPU inference. | • **6.7×** dynamic chunk batching<br>• **88.9%** early-exit compute save<br>• **100%** secret recall (`real-bench-100`) | [![HF Model](https://img.shields.io/badge/🤗_HuggingFace-EdgeSLM--0.5b--v3-yellow)](https://huggingface.co/prajwalpujari16/EdgeSLM-qwen0.5b-v3)<br>[![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/EdgeSLM/) |
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

### 🛠️ Technical Competencies

* **Inference Internals:** Paged KV-cache allocators, continuous batching schedulers, Leviathan speculative verification, radix prefix caching, roofline MBU modeling.
* **Runtimes & Frameworks:** Pure PyTorch (SDPA, custom tensor gathers), Hugging Face (Transformers, PEFT/LoRA), ONNX Runtime INT4, NVML telemetry.
* **Serving & Infrastructure:** FastAPI, asyncio/aiohttp, SSE streaming, Ollama, vLLM, llama.cpp, Prometheus, Docker, GitHub Actions cross-platform matrix.
* **Security & Packaging:** PyPI Trusted Publishers, Sigstore cryptographic provenance attestation, air-gapped DLP regex + entropy filters.

---

### 📫 Connect & Collaborate

* **Portfolio:** [prajwal-pujari.vercel.app](https://prajwal-pujari.vercel.app)
* **Email:** [prajwalpujari16@gmail.com](mailto:prajwalpujari16@gmail.com)
* **LinkedIn:** [linkedin.com/in/prajwal-pujari-mn9964](https://www.linkedin.com/in/prajwal-pujari-mn9964)
* **WhatsApp:** [+91 6360012214](https://wa.me/916360012214)
