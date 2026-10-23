# Hi, I'm Prajwal Pujari 👋

AI/ML systems engineer building continuous-batching LLM inference runtimes, Paged KV-cache allocators, and capacity benchmarking harnesses. I focus on **running models efficiently on small hardware**, evaluating systems on real silicon with sample-size-aware percentiles, synchronized GPU telemetry, and publishing raw engineering results.

🌐 **Portfolio: [prajwal-pujari.vercel.app](https://prajwal-pujari.vercel.app)** · 📝 **Engineering Notes: [prajwal-pujari.vercel.app/blog](https://prajwal-pujari.vercel.app/blog/)**  
Available for AI/ML systems engineering roles & freelance consulting (Document AI, cited RAG pipelines, private on-premise SLMs).

---

## 📝 Recent Engineering Notes & Teardowns

- **[Roofline Benchmarking & Auto-Tuning LLM Serving: How We Pushed Pure PyTorch to 27 tok/s](https://prajwal-pujari.vercel.app/blog/posts/roofline-serving-benchmarks.html)** (`2026-10-23`)  
  *Eliminating DRAM memory-bandwidth waste in naive continuous batching: unified batched physical block gather scaled concurrency 4 throughput by +130.8% (11.7 → 27.0 tok/s) and delivered 2.04 Tok/Joule on an RTX 3050 Laptop GPU.*
- **[Why Naive KV-Caches Waste >60% VRAM (And How Paged Memory Fixes It)](https://prajwal-pujari.vercel.app/blog/posts/paged-kv-cache-vram.html)** (`2026-10-22`)  
  *How replacing contiguous memory pre-allocations with 16-token physical blocks and virtual table mapping reduces KV-cache memory waste from >60% to <3.8% in pure PyTorch.*

---

## 📌 Featured Systems Work

### **[servebench](https://github.com/Prajwal7-2002/servebench)** · [![PyPI](https://img.shields.io/pypi/v/servebench?color=blue)](https://pypi.org/project/servebench/) [![Sigstore](https://img.shields.io/badge/Sigstore-Provenance_Verified-success)](https://pypi.org/project/servebench/#security) [![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/servebench/)
*Production load-testing, saturation auto-tuning, and capacity profiler for any OpenAI-compatible LLM endpoint (Ollama, vLLM, llama.cpp, SGLang, LM Studio).*
- `pip install servebench` — auto-detects local servers and benchmarks capacity in 60 seconds (`servebench quick`)
- **Auto-Tuning (`servebench tune`)**: Sweeps concurrency levels, detects knee saturation points, and generates optimal serving configurations
- **Statistical Rigor**: Sample-size-aware percentiles (honest p99 for $N \ge 100$), multi-trial repeats with 95% confidence intervals, and steady-state throughput windows
- **Hardware Observability**: Synchronized NVML GPU telemetry (power, VRAM, temp, tokens/Joule) and server Prometheus queue scraping on one timeline
- **Automated Diagnosis**: Classifies bottlenecks as Slot/Queue-Bound, Memory-Bandwidth-Bound, Compute-Bound, or Client-Bound
- **CI Performance Gate**: `servebench check` with 152 automated tests across Ubuntu, macOS, and Windows matrix; verified Sigstore cryptographic provenance

### **[mini-infer](https://github.com/Prajwal7-2002/mini-infer)** · [![PyPI](https://img.shields.io/pypi/v/mini-infer?color=blue)](https://pypi.org/project/mini-infer/) [![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/mini-infer/)
*Minimal, high-performance continuous-batching LLM inference engine with Paged KV-cache, prefix caching, and speculative decoding for Qwen2.5 in pure PyTorch.*
- `pip install mini-infer` — pure PyTorch, zero C++ compiler toolchains or CUDA build steps required
- **Paged KV Memory Manager**: Fixed 16-token physical block pool with virtual-to-physical block tables, dropping memory waste from $>60\%$ to $<3.8\%$
- **Unified Batched Gather**: Zero-copy physical block gathering leaps concurrency 4 decode to **27.0 tok/s (+130.8%)** drawing 13.2 W (**2.04 Tok/Joule**) on an RTX 3050 Laptop GPU
- **True Continuous Batching**: Single-token iteration-level scheduler dynamically interleaves prefill and decode passes with instant block reclamation
- **Radix Prefix Caching**: Hashes prompt token blocks to skip redundant prefill passes on shared system prompts, cutting TTFT from 340 ms to <15 ms
- **Speculative Decoding**: Dual-model 0.5B draft proposer + 1.5B target parallel verifier with Leviathan rejection sampling; runs simultaneously in 3.81 GB VRAM with 2.2x speedup and mathematically zero distribution drift
- **Streaming API**: OpenAI-compatible SSE streaming server (`POST /v1/chat/completions`)

### **[EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM)** · [![HF Model](https://img.shields.io/badge/🤗_HuggingFace-EdgeSLM--0.5b--v3-yellow)](https://huggingface.co/prajwalpujari16/EdgeSLM-qwen0.5b-v3) [![Docs](https://img.shields.io/badge/docs-GitHub_Pages-blue)](https://prajwal7-2002.github.io/EdgeSLM/)
*Document security classifier and air-gapped DLP scanner running locally on consumer hardware.*
- **Empirical Generalization**: LoRA fine-tune of Qwen2.5-0.5B outperforming bag-of-words baselines on contrastive vocabulary evaluation (88.8% vs 75.0%, McNemar $p = 0.043$)
- **Dynamic Chunk Batching**: Scales multi-page document parsing throughput by 6.7x (1,497 ms → 223 ms on 8 chunks); Speculative Early-Exit provides 88.9% compute reduction
- **Deterministic Policy**: Structural regex and Shannon entropy filters catching 100% of cryptographic keys, API tokens, and credentials in <1 ms
- **Edge Deployment**: 392 MB ONNX INT4 edge build classifying documents in ~0.5s on a standard laptop CPU with zero data leakage

### **[Menmo](https://menmo-app.netlify.app/)** ([try it live →](https://menmo-app.netlify.app/)) · ([backend](https://github.com/Prajwal7-2002/menmo-backend) · [frontend](https://github.com/Prajwal7-2002/menmo-frontend))
*Chat with your own documents; every answer cites the source and exact page.*
- Hybrid retrieval on Pinecone (MiniLM embeddings + BM25, optional cross-encoder), scoped per user; falls back from documents to web search to general knowledge
- Intelligent query routing (Groq, `gpt-oss-120b` with fallback) deciding intent, reply tone, and rewriting follow-ups into standalone queries
- Django REST API in Docker on Hugging Face Spaces, Next.js static site on Netlify

---

## 🛠️ Tech Stack & Systems Tooling

- **ML Systems & Runtimes:** PyTorch (SDPA, custom KV-cache allocators), Hugging Face (Transformers, PEFT/LoRA), ONNX Runtime, CUDA/NVML, continuous batching schedulers
- **Serving & Capacity:** FastAPI, asyncio/aiohttp, SSE streaming, Ollama, vLLM, llama.cpp, Prometheus telemetry
- **Information Retrieval:** Pinecone, ChromaDB, BM25, Sentence-Transformers, cross-encoders
- **Tooling & Infrastructure:** Python 3.11+, Typer, Docker, GitHub Actions CI/CD matrix, PyPI (Trusted Publishers + Sigstore provenance), Next.js

---

## 🌱 Currently Engineering

- **LLM Serving Efficiency**: Preemptive iteration chunking, memory-bandwidth roofline modeling, KV-cache block quantization, and speculative verification scheduling.

---

## 📫 Connect & Collaborate

- **Portfolio:** [prajwal-pujari.vercel.app](https://prajwal-pujari.vercel.app)
- **LinkedIn:** [linkedin.com/in/prajwal-pujari-mn9964](https://www.linkedin.com/in/prajwal-pujari-mn9964)
- **Email:** [prajwalpujari16@gmail.com](mailto:prajwalpujari16@gmail.com)
- **WhatsApp:** [+91 6360012214](https://wa.me/916360012214)
