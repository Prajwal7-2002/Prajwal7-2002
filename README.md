# Hi, I'm Prajwal Pujari 👋

AI/ML engineer who builds and evaluates ML systems end to end, from training to a served API. I'm especially interested in **running models efficiently on small hardware**, and I like publishing results as they are, including the ones that didn't work.

🌐 **Portfolio: [prajwal-pujari.vercel.app](https://prajwal-pujari.vercel.app)** · Available for freelance projects: WhatsApp AI assistants, document AI and RAG, custom agents, ML models.

## 📌 Featured projects

**[servebench](https://github.com/Prajwal7-2002/servebench)** ([PyPI](https://pypi.org/project/servebench/) · [docs](https://prajwal7-2002.github.io/servebench/)): Production load-testing and capacity profiler for any OpenAI-compatible LLM endpoint (Ollama, vLLM, llama.cpp, SGLang, LM Studio).
- `pip install servebench` — auto-detects local servers and benchmarks capacity in 60 seconds (`servebench quick`)
- Statistical rigor: sample-size-aware percentiles (honest p99 for $N \ge 100$), multi-trial repeats with 95% confidence intervals, and steady-state throughput windows
- Hardware observability: live NVML GPU telemetry (power, VRAM, temp, tokens/Joule) and server Prometheus queue scraping on one timeline
- Automated bottleneck diagnosis: classifies servers as Slot/Queue-Bound, Memory-Bandwidth-Bound, Compute-Bound, or Client-Bound
- CI performance regression gate (`servebench check`) with 142 automated tests and cross-platform CI

**[mini-infer](https://github.com/Prajwal7-2002/mini-infer)** ([PyPI](https://pypi.org/project/mini-infer/) · [docs](https://prajwal7-2002.github.io/mini-infer/)): Minimal, high-performance continuous-batching LLM inference engine with Paged KV-cache, prefix caching, and speculative decoding for Qwen2.5 in pure PyTorch.
- `pip install mini-infer` — pure PyTorch, zero C++ build dependencies or CMake required
- Paged KV memory manager: fixed 16-token physical block pool with virtual-to-physical block tables, dropping memory waste from $>60\%$ to $<3.8\%$
- True continuous batching: single-token iteration-level scheduler dynamically interleaves prefill and decode passes with instant block reclamation
- Radix prefix caching: hashes prompt token blocks to skip redundant prefill passes on shared system prompts, cutting TTFT from 340 ms to <15 ms
- Speculative decoding: dual-model 0.5B draft proposer + 1.5B target parallel verifier with Leviathan rejection sampling; runs simultaneously in 3.81 GB VRAM on an RTX 3050 Laptop GPU with 2.2x speedup and zero distribution drift
- OpenAI-compatible SSE streaming API (`POST /v1/chat/completions`)

**[EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM)** ([HF Model](https://huggingface.co/prajwalpujari16/EdgeSLM-qwen0.5b-v3) · [docs](https://prajwal7-2002.github.io/EdgeSLM/)): Document security classifier and air-gapped DLP scanner running locally on consumer hardware.
- Empirical generalization: LoRA fine-tune of Qwen2.5-0.5B outperforming bag-of-words baselines on contrastive vocabulary evaluation (88.8% vs 75.0%, McNemar $p = 0.043$)
- Inference systems acceleration: Dynamic Tensor Chunk Batching scales multi-page document parsing throughput by 6.7x (1,497 ms → 223 ms on 8 chunks); Speculative Early-Exit provides 88.9% compute reduction
- Deterministic security policy: Shannon entropy and structural regex filters catching 100% of cryptographic keys, API tokens, and credentials in <1 ms
- Edge deployment: 392 MB ONNX 4-bit edge build classifying documents in ~0.5s on a standard laptop CPU with zero data leakage

**[Menmo](https://menmo-app.netlify.app/)** ([try it live →](https://menmo-app.netlify.app/)): Chat with your own documents; every answer says where it came from and cites the page.
([backend](https://github.com/Prajwal7-2002/menmo-backend) · [frontend](https://github.com/Prajwal7-2002/menmo-frontend))
- Hybrid retrieval on Pinecone (MiniLM embeddings + BM25, optional cross-encoder), scoped per user; falls back from your documents to web search to general knowledge, and labels which one it used
- One LLM routing call (Groq, `gpt-oss-120b` with automatic fallback) decides intent, reply tone and answer length, and rewrites follow-ups into standalone queries
- Django REST API in Docker on Hugging Face Spaces, Next.js static site on Netlify

## 🛠️ Tech

**ML / LLMs:** PyTorch, Hugging Face (Transformers, PEFT/LoRA), ONNX, scikit-learn, XGBoost, TensorFlow, RAG (Pinecone, BM25)
**Serving / backend:** FastAPI, Django, Docker, asyncio/aiohttp, Ollama, llama.cpp, vLLM, NVML
**Other:** Streamlit, Next.js, SQLAlchemy, GitHub Actions, PyPI

## 🌱 Building & Learning

LLM inference systems: continuous batching, paged KV-cache, speculative decoding, low-bit quantization, and serving benchmarks.

## 📫 Reach me

- Portfolio: https://prajwal-pujari.vercel.app
- LinkedIn: https://www.linkedin.com/in/prajwal-pujari-mn9964
- Email: prajwalpujari16@gmail.com
