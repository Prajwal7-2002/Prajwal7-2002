# Hi, I'm Prajwal Pujari 👋
### AI/ML Systems & Inference Engineer

I build high-throughput **LLM inference runtimes**, **Paged KV-cache memory allocators**, and **hardware capacity benchmarking harnesses** from first principles.

---

## ⚡ The LLM Systems Trilogy

A three-part open-source engineering suite covering inference runtimes, hardware load-testing, and local air-gapped security:

```
                  ┌────────────────────────────────────────────────────────┐
                  │                       servebench                       │
                  │   Production Capacity & Concurrency Load-Tester        │
                  │   (Hardware Roofline Bounds & NVML GPU Telemetry)      │
                  └──────────────────────────┬─────────────────────────────┘
                                             │  evaluates & load-tests
                                             ▼
┌───────────────────────────────────────────────────┐     ┌───────────────────────────────────────────────────┐
│                    mini-infer                     │     │                      EdgeSLM                      │
│        Continuous-Batching Inference Engine       │     │          Air-Gapped Edge DLP Classifier           │
│  • Paged KV-Cache (16-tok blocks, <4% waste)      │     │  • LoRA Fine-tune on Qwen2.5-0.5B (88.8% contrast)│
│  • Radix Tree Prefix Cache (28x TTFT speedup)     │     │  • 6.7x Dynamic Tensor Chunk Batching             │
│  • Speculative Decoding (2.2x speedup, 0 drift)   │     │  • Tier-1 Cryptographic Secret Scanner (100% rec) │
│  • Zero C++ toolchain / pure PyTorch wheels       │     │  • 392 MB ONNX INT4 edge build for consumer CPUs  │
└───────────────────────────────────────────────────┘     └───────────────────────────────────────────────────┘
```

---

### 1. [mini-infer](https://github.com/Prajwal7-2002/mini-infer) 🚀
**A minimal continuous-batching LLM inference engine with Paged KV-cache, radix prefix caching, and speculative decoding.**
[![PyPI version](https://img.shields.io/pypi/v/mini-infer.svg)](https://pypi.org/project/mini-infer/)
[![Documentation](https://img.shields.io/badge/docs-GitHub%20Pages-teal.svg)](https://prajwal7-2002.github.io/mini-infer/)
[![License: Apache 2.0](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://github.com/Prajwal7-2002/mini-infer/blob/main/LICENSE)

- **Paged KV-Cache**: Replaces contiguous VRAM allocation with 16-token physical blocks and virtual-to-physical block tables, dropping memory waste from $>60\%$ to $<3.8\%$.
- **Radix Tree Prefix Cache**: Reuses prefill attention states across shared system prompts and multi-turn conversations, cutting TTFT from $340\text{ ms}$ to $<15\text{ ms}$ (28x speedup).
- **Speculative Decoding**: Dual-model speculative execution pairing a 0.5B draft model with a 1.5B target verifier, delivering 2.2x generation speedup with mathematically zero output distribution drift.
- **Zero Build Toolchain**: Production-grade algorithms in pure, testable Python/PyTorch—zero C++ compiler or CMake required.
- **Install**: `pip install mini-infer`

---

### 2. [servebench](https://github.com/Prajwal7-2002/servebench) 📊
**Production capacity profiler and load-testing harness for local LLM serving endpoints.**
[![PyPI version](https://img.shields.io/pypi/v/servebench.svg)](https://pypi.org/project/servebench/)
[![Documentation](https://img.shields.io/badge/docs-GitHub%20Pages-indigo.svg)](https://prajwal7-2002.github.io/servebench/)
[![License: Apache 2.0](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://github.com/Prajwal7-2002/servebench/blob/main/LICENSE)

- **Statistical Rigor**: Measures TTFT, TPOT, ITL, and throughput across concurrency sweeps with sample-size-aware percentiles (honest p99 only when $N \ge 100$) and 95% bootstrap confidence intervals.
- **Hardware Telemetry**: Synchronized NVML GPU telemetry tracking power draw, VRAM consumption, and energy efficiency (Tokens / Joule) to diagnose memory-bandwidth vs. compute-saturation roofline limits.
- **Universal Engine Support**: Benchmark Ollama, vLLM, llama.cpp, mini-infer, or any OpenAI-compatible API.
- **Automated CI Regression Gating**: Exit-code-based latency SLO enforcement for model deployment pipelines.
- **Install**: `pip install servebench`

---

### 3. [EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM) 🛡️
**Enterprise document sensitivity classifier and air-gapped DLP scanner running locally on consumer hardware.**
[![GitHub Repo](https://img.shields.io/badge/repo-EdgeSLM-green.svg)](https://github.com/Prajwal7-2002/EdgeSLM)
[![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/Prajwal7-2002/EdgeSLM/blob/main/LICENSE)

- **Empirical Generalization**: LoRA fine-tune of Qwen2.5-0.5B outperforming bag-of-words baselines on contrastive vocabulary evaluation (88.8% vs 75.0%, McNemar $p = 0.043$).
- **Inference Systems Acceleration**: Dynamic Tensor Chunk Batching scales multi-page PDF/Word parsing throughput by **6.69x** ($1,497\text{ ms} \to 223\text{ ms}$ on 8 chunks); Speculative Early-Exit provides **88.9% compute reduction**.
- **Deterministic Security Policy**: Shannon entropy ($H \ge 3.8$) and Tier-1 structural regex filters catching 100% of cryptographic keys, API tokens, and database credentials in $<1\text{ ms}$.
- **Edge Deployment**: 392 MB ONNX 4-bit edge build classifying documents in $\approx 0.5\text{s}$ on a standard laptop CPU with zero data leakage.

---

## 🛠️ Technical Competencies

- **Inference Runtimes & Kernels**: PagedAttention, Continuous Batching, Speculative Decoding, Prefix Caching (Radix Tree), PyTorch SDPA, FlashAttention-style tiling.
- **Quantization & Optimization**: ONNX Runtime, INT4/INT8 quantization, KV-cache quantization, TensorRT-LLM, PyTorch Profiler.
- **Systems & Infrastructure**: Python (AsyncIO), C++, PyTorch, CUDA, FastAPI, NVML, Prometheus, Docker, Linux systems programming.
- **Statistical Evaluation**: McNemar paired significance tests, Wilson score intervals, Bootstrap confidence intervals, Empirical capacity modeling.

---

## 📬 Connect

- **Portfolio**: [prajwalpujari.com](https://prajwal-pujari.vercel.app/)
- **LinkedIn**: [linkedin.com/in/prajwal-pujari-mn9964](https://www.linkedin.com/in/prajwal-pujari-mn9964/)
- **Email**: prajwalpujari16@gmail.com
