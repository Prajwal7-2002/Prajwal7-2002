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

**[mini-infer](https://github.com/Prajwal7-2002/mini-infer)**: Minimal, high-performance continuous-batching LLM inference engine with Paged KV-cache, prefix caching, and speculative decoding for Qwen2.5 in pure PyTorch.
- Paged KV memory manager: fixed 16-token physical block pool with virtual-to-physical block tables, eliminating over 60% VRAM waste from memory fragmentation
- True continuous batching: single-token iteration-level scheduler dynamically interleaves prefill and decode passes with instant block reclamation
- Radix prefix caching: hashes prompt token blocks to skip redundant prefill passes on shared system prompts, dropping TTFT by up to 80%
- Speculative decoding: dual-model 0.5B draft proposer + 1.5B target parallel verifier with Leviathan rejection sampling; runs simultaneously in 3.81 GB VRAM on an RTX 3050 Laptop GPU with 43.6%–77.8% draft acceptance and zero distribution drift
- OpenAI-compatible SSE streaming API (`POST /v1/chat/completions`) benchmarked live against real hardware with `servebench`

**[EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM)**: Document security classifier: a LoRA fine-tune of SmolLM2-360M plus a regex policy layer, served locally with FastAPI.
- Evaluated on a held-out, re-labelled set with 95% confidence intervals, not just the in-distribution test split
- Findings I didn't expect: a TF-IDF baseline beat the fine-tune (91.7% vs 58.3%), and INT8 quantization gave a 1.8× CPU speedup but dropped accuracy to 25%. [Full report →](https://github.com/Prajwal7-2002/EdgeSLM/blob/main/REPORT.md)
- Now improving it: better training data and quantization that keeps accuracy, measured against the same held-out set

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

- Portfolio: https://prajwal7-2002.github.io/portfolio/ · https://prajwal-pujari.vercel.app
- LinkedIn: https://www.linkedin.com/in/prajwal-pujari-mn9964
- Email: prajwalpujari16@gmail.com
