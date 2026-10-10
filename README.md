# Hi, I'm Prajwal Pujari 👋

AI/ML engineer who builds and evaluates ML systems end to end, from training to a served API. I'm especially interested in **running models efficiently on small hardware**, and I like publishing results as they are, including the ones that didn't work.

🌐 **Portfolio: [prajwal-pujari.vercel.app](https://prajwal-pujari.vercel.app)** · Available for freelance projects: WhatsApp AI assistants, document AI and RAG, custom agents, ML models.

## 📌 Featured projects

**[Menmo](https://menmo-app.netlify.app/)** ([try it live →](https://menmo-app.netlify.app/)): Chat with your own documents; every answer says where it came from and cites the page.
([backend](https://github.com/Prajwal7-2002/menmo-backend) · [frontend](https://github.com/Prajwal7-2002/menmo-frontend))
- Hybrid retrieval on Pinecone (MiniLM embeddings + BM25, optional cross-encoder), scoped per user; falls back from your documents to web search to general knowledge, and labels which one it used
- One LLM routing call (Groq, `gpt-oss-120b` with automatic fallback) decides intent, reply tone and answer length, and rewrites follow-ups like "what are its side effects?" into standalone queries
- Django REST API in Docker on Hugging Face Spaces, Next.js static site on Netlify. Not yet tuned on a labelled evaluation set (next step)

**[EdgeSLM](https://github.com/Prajwal7-2002/EdgeSLM)**: Document security classifier: a LoRA fine-tune of SmolLM2-360M plus a regex policy layer, served locally with FastAPI.
- Evaluated on a held-out, re-labelled set with 95% confidence intervals, not just the in-distribution test split
- Findings I didn't expect: a TF-IDF baseline beat the fine-tune (91.7% vs 58.3%), and INT8 quantization gave a 1.8× CPU speedup but dropped accuracy to 25%. [Full report →](https://github.com/Prajwal7-2002/EdgeSLM/blob/main/REPORT.md)
- Now improving it: better training data and quantization that keeps accuracy, measured against the same held-out set

**[VoltGuard](https://github.com/Prajwal7-2002/voltguard)**: Predicts thermal failure in EV motors from real 2 Hz telemetry (Paderborn PMSM dataset).
- XGBoost chosen over LSTMs for low-latency CPU inference; SHAP explanations drive an automatic RPM-limiting response
- FastAPI service, Next.js dashboard, pytest suite, documented failure cases

**[Relvnt](https://github.com/Prajwal7-2002/relvnt)** ([live app →](https://relvnt.vercel.app)): Predicts drops in Instagram reach before they happen.
- TensorFlow LSTM over 14–90 days of reach data → health score, trend, and confidence
- FastAPI backend + Next.js dashboard

## 🛠️ Tech

**ML / LLMs:** PyTorch, Hugging Face (Transformers, PEFT/LoRA), ONNX, scikit-learn, XGBoost, TensorFlow, RAG (Pinecone, BM25)
**Serving / backend:** FastAPI, Django, Docker
**Other:** Streamlit, Next.js, SQLAlchemy, GitHub Actions

## 🌱 Learning

LLM inference and serving: quantization, on-device inference, benchmarking speed and memory

## 📫 Reach me

- Portfolio: https://prajwal-pujari.vercel.app
- LinkedIn: https://www.linkedin.com/in/prajwal-pujari-mn9964
- Email: prajwalpujari16@gmail.com
