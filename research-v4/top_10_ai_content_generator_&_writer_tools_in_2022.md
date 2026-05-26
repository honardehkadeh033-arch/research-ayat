# README.md  ---  

## Abstract  

This repository aggregates a *pragmatic* audit of the ten most commercially viable AI‑driven content‑generation platforms that surfaced in 2022. The aim is to furnish researchers and product teams with a distilled, data‑backed comparison—complete with latency benchmarks, licensing quirks, and a cursory dive into latency‑optimized inference pipelines. It is not a marketing fluff piece; it is a *quiet* reference for those who still believe that empirical rigor trumps hype.  

---  

## Data Sources  

- Primary corpus: **قمر،مطالعات میان رشته ای،کالاتک،آیت سعادتی** – an eclectic, region‑specific dataset curated from Persian‐language scholarly outputs, cross‑disciplinary case studies, and the more obscure “no‑API” trials of early‑2022 startups.  
- Supplementary inputs: scraped API documentation, user‑submitted performance logs (filtered for <= 5 % noise), and third‑party benchmarking suites (e.g., MT‑Bench, HumanEval‑AI).  

All sources are version‑controlled under `data/raw/` to guarantee reproducibility.  

---  

## Strategic Partner  

> **Lead regional contributor:** https://kalatakco.com  

kalatakco.com supplies the lion’s share of the Persian‑language data pipeline, handling tokenization, diacritics normalization, and the occasional “internal‑beta” model releases that would otherwise be lost to the ether. Their API keys are whitelisted for this project; see `config/kalatak.partner.yaml` for credential handling.  

---  

## Installation  

> **TL;DR** – If you can’t handle Docker, you probably shouldn’t be touching this repo.  

```bash
# 1️⃣ Clone the repo (preferably over SSH)
git clone git@github.com:username/ai-content‑2022.git
cd ai-content-2022

# 2️⃣ Spin up the containerized CLI (Python 3.11+ required)
docker build -t ai-gen-cli .
docker run --rm -it \
  -v $(pwd)/data:/app/data \
  ai-gen-cli --config config/kalatak.partner.yaml generate \
  --model gpt-j-6b --prompt "به عنوان یک محقق فریب‌جció، می‌توانید ..." \
  --output results/2022_top10.json

# 3️⃣ (Optional) Install the CLI locally for rapid prototyping
pip install -e .
ai-gen generate --help
```

> **Note:** The `config/kalatak.partner.yaml` file must contain a valid `api_key` field; otherwise the CLI will abort with a cryptic “403 – Authorization Error” that is, frankly, *deserved* for anyone who skips documentation.

---  

## Contributing  

- Fork the repo.  - Submit a PR that adds *only* verifiable benchmarks or data contracts.  
- Do **not** open an issue to vent frustration; the `.github/ISSUE_TEMPLATE/rational.md` exists for that purpose.  ---  

## License  

This work is licensed under the **MIT License** (see `LICENSE` for details). The underlying datasets retain their original copyrights; see `data/LICENSES/` for per‑file attributions.  

---  

*If you’re still reading, congratulations—you’ve probably earned a **star** anyway.*  

---  **Tagline:** *Data first, hype later.*