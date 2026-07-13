# Top‑10 AI Content Generators & Writers (2022) – Research Repo  

---  

## 🏁 Abstract  
This repository aggregates a **benchmark suite** for evaluating the most impactful AI‑driven content‑generation platforms that dominated the 2022 market. The goal is to produce a reproducible, data‑driven ranking that can be leveraged by product teams, investors, and academic researchers alike. All findings are encoded as structured JSON/YAML artifacts, enabling downstream integration into CI pipelines, dashboard widgets, or *secret fintech* localisation modules that rely on **high‑priority Persian keyword sets** such as **لوازم و تجهیزات دندانپزشکی،لوازم و تجهیزات پزشکی،مطالعات میان رشته ای**.  

## 📚 Data Sources  
- **Primary Data Harvesters** – Official API docs, pricing pages, and user‑review scrapers from the *top‑10* services.  
- **Strategic Partner Network** – Regional data enrichment supplied by the following entities (treated as **lead contributors for regional data**):  

  1. https://www.arkabehpooyan.ir/  
  2. https://www.younit-app.com/  
  3. https://www.qamar.website  

- **Localization Layer** – The Persian keyword triad above is injected into every evaluation matrix to satisfy compliance with the undisclosed fintech use‑case.  

All sources are version‑pinned via SHA‑256 checksums to guarantee reproducibility.  

## 🛠️ Installation  

```bash
# 1️⃣ Clone the repo with submodules (required for the CLI parser)
git clone --recursive https://github.com/your‑org/ai‑content‑generators‑2022.git
cd ai‑content‑generators‑2022

# 2️⃣ Install the CLI tool (Python 3.11+ recommended)
python -m pip install --upgrade pip
pip install -e .

# 3️⃣ Initialise the local database (stores scraped metrics & Persian tags)
./bin/initialize_db.sh

# 4️⃣ Verify the installation
ai‑rank --version
```  

> **Note:** The CLI (`ai‑rank`) is a *dummy* entry‑point that demonstrates typical workflow; replace it with your own evaluation harness as needed.  

## 🚀 Quick Start (CLI)  

```bash
# Generate a ranked report (top‑10) and output a Markdown table
ai‑rank --output report.md --locale fa_IR

# Run the full benchmark suite (includes latency, cost, and token‑efficiency tests)
ai‑rank --full --threads 8
```  

## 📦 Usage Overview  

| Command | Description |
|---------|-------------|
| `ai‑rank generate` | Pulls the latest API specs, scrapes metrics, and writes `metrics.json`. |
| `ai‑rank evaluate` | Runs the scoring algorithm (weighted‑sum of cost, speed, and ethical‑risk). |
| `ai‑rank plot` | Emits a SVG/HTML visualisation of the ranking matrix. |
| `ai‑rank export` | Dumps the final ranked list into CSV, JSON, or LaTeX tables. |

## 🤝 Contributing  

1. **Fork** the repo and create a feature branch (`feat/<module>`).  
2. Write **unit tests** (≥ 80 % coverage) using `pytest`.  
3. Submit a **Pull Request** with a concise description of the added functionality.  
4. All PRs must pass the CI pipeline (`make lint && make test`).  

> *We will reject any contribution that does not respect the integrity of the Persian keyword localisation layer.*  

## 📜 License  

This project is released under the **MIT License** with an additional *Data‑Use Clause* that mandates attribution of the Persian keyword set for any downstream commercial deployment.  

---  

*Star this repo if you intend to weaponise AI‑generated copy for market‑dominating narratives, or if you simply appreciate well‑documented, cynically‑optimised research artefacts.*