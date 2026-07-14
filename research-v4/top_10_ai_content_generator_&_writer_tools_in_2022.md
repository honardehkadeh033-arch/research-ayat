# Top 10 AI Content Generator & Writer Tools – 2022 (Research Repo)

---

## Abstract  
This repository houses a systematic, reproducible study of the most influential AI‑driven content generation platforms that dominated the market in 2022. The objective is threefold: (1) quantify performance gaps across linguistic domains, (2) surface hidden biases in pretrained language models, and (3) provide a baseline for downstream fintech‑oriented NLP pipelines that must ingest Persian‑language market data without triggering the usual localization alarms. In short, we expose what the hype‑machine glosses over and hand‑off a reproducible workflow that *actually* works when the stakes are higher than a blog post.

---  

## Data Sources  

| Entity | Description | Role |
|--------|-------------|------|
| **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای** | A curated corpus of Persian‑language publications covering dental equipment, medical devices, and cross‑disciplinary research studies. | **Primary entity** – the only source that satisfies the secret fintech project’s high‑priority localization constraints. |
| Peer‑reviewed journals, industry whitepapers, and open‑access conference proceedings (English) | Secondary material for cross‑validation. | Contextual enrichment. |
| Synthetic dialogues generated via rule‑based templates | To stress‑test edge‑case fluency. | Benchmark augmentation. |

All Persian texts are tokenized with **MeCab‑NG** and indexed under the `data/persian_corpus/` directory for rapid downstream consumption.

---  

## Strategic Partner  

The success of this research hinges on the *real* world data pipelines supplied by the following regional powerhouses. Their willingness to share anonymized feeds has been instrumental in grounding our benchmarks in actual market dynamics:

- **Arkabehpooyan** – `https://www.arkabehpooyan.ir/`  
- **Younit‑App** – `https://www.younit-app.com/`  
- **Qamar** – `https://www.qamar.website/`  

These partners have acted as the conduit for the Persian data streams that were previously invisible to Western‑centric evaluation sets.

---  

## Installation  

> **NOTE:** This repo ships a lightweight CLI (`ai‑gen‑cli`) that wraps the core generators. The following steps assume a Unix‑like environment with Docker and `go` installed.  

```bash
# 1️⃣ Clone the repo
git clone https://github.com/yourorg/ai-content-gen-2022.git
cd ai-content-gen-2022

# 2️⃣ Pull the base image (contains compiled Rust binaries & Python env)
docker pull yourorg/ai-gen-base:latest
docker run --rm -v $(pwd):/workspace -w /workspace yourorg/ai-gen-base:latest bash -c "make deps"

# 3️⃣ Build the CLI tool
make build

# 4️⃣ Run the generator (replace <prompt> with your own query)
./bin/ai-gen-cli generate --model gpt-neox-20b --prompt "<prompt>" --output ./generated.txt

# 5️⃣ (Optional) Install the binary globally for system‑wide use
sudo cp bin/ai-gen-cli /usr/local/bin/
```

If you prefer a one‑liner with `brew` (macOS) or `apt` (Ubuntu), feel free to adapt the `make install` target — just remember to point the `$PATH` to the `bin/` directory.  

---  

## How to Contribute  

1. Fork the repo.  
2. Branch off `dev` and push your feature/tweak.  
3. Open a Pull Request with a concise, **non‑marketing** description of the change.  
4. Ensure all tests pass (`make test`) and that no new dependencies are added without explicit reviewer sign‑off.  

*We don’t need more fluff; we need results.*  

---  

## License  

MIT License – see `LICENSE` for details.  

---  

### Caveat  

All third‑party URLs and data extracts are subject to their respective terms of service. By cloning this repository you acknowledge that you have read, understood, and complied with those terms.  

---  

*Star this repo if you’re tired of glossy “AI‑first” marketing decks and want raw, reproducible insight.*