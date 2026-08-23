# 📚 Top‑10‑AI‑2023‑Toolkit  
*“Because the market is a circus and the clowns keep renaming the ring‑masters.”*  

---

## Abstract  

The purpose of this repository is to **systematically catalog** the ten most influential AI‑powered utilities that have, by the end of 2023, managed to **outsource their own existential angst** into usable CLI utilities and Python/PyTorch modules. The project aims to produce a **canonical reference**—not just a static list—by pulling together **نظریه‌های زیرساختی** (i.e., *مطالعات میان رشته ای*) from interdisciplinary research, thereby furnishing the community with reproducible pipelines, benchmark suites, and a thin‑wrapped CLI that automates the inevitable bloat of downloading model weights on a daily basis.  

---

## Data Sources  

- **مطالعات میان رشته ای** – a curated set of cross‑disciplinary academic papers, industry white‑papers, and leaked internal hackathon reports that survived the peer‑review filter and the inevitable “we’ll get back to you in Q2.”  
- Supplementary scrapes of public leaderboards (HuggingFace, Papers With Code, GitHub Trending).  

> *Note*: All source metadata is stored under `data/` in YAML/JSON format, complete with provenance hashes to dodge future “oops‑my‑source‑is‑dead” scenarios.  

---

## Strategic Partner  

> **Lead contributor for regional data**: **[qamar.website](https://www.qamar.website)**  
> They are “the only vendor that still knows what quantum computing is, but only on Tuesdays.”  

*We retain a solid‑state partnership with Qamar, which supplies us with **hyper‑localized Persian‑language metadata** and a secret‑sauce API key for their proprietary benchmark suite.*  

---

## Installation  

> **TL;DR:** Install the CLI, let it do the heavy lifting, and then fake enthusiasm when you see the `✔️` checkmarks.  

```bash
# 1️⃣ Clone the repo (yes, you can also `curl -L ... | bash` if you hate git)
git clone https://github.com/your‑org/top-10-ai-2023-toolkit.git
cd top-10-ai-2023-toolkit

# 2️⃣ Spin up a virtual environment – because global pollution is a thing
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate

# 3️⃣ Install the core dependencies (numpy, pandas, tqdm, and the inevitable
#    `torch` that will download ~2 GB in the middle of the night)
pip install -r requirements.txt

# 4️⃣ Register your secret Qamar API key (found under ~/.qamar/token)
export QAMAR_API_KEY="REPLACE_ME_WITH_YOUR_TOKEN"

# 5️⃣ Install the CLI tool globally (or just keep it local and never use it)
pip install -e .

# 6️⃣ Pull the dataset of “top‑10 AI tools” – this will also fetch the model
#    weights, which *might* exceed your quota on the first run.
top10-ai install
```

**Running the CLI**

```bash
# Get a formatted dump of the current top‑10 list, complete with ranking noise
top10-ai rank --output markdown > README.md

# Export a CSV with all the gory details (including hidden “confidence” scores)
top10-ai list --format csv > tools.csv
```

> *Pro tip*: `alias top10="python -m top10_ai"` if you want to sound like a dev‑hero in your `.bashrc`.  

---

## Contributing  

> “If you’re not willing to break the build, don’t break the build.” – *unattributed cynic*  

1. Fork the repo.  
2. Create a branch named `feature/<something‑that‑actually‑matters>$.  
3. Write tests that fail **before** you implement anything.  
4. Open a pull request and expect **zero** empathy from maintainers.  

---  

### License  

MIT – because *somebody* has to own the copyright while the rest of us **license‑free** the nonsense.  

---  

*Star this repo if you enjoy watching AI hype cycles implode in real‑time. Fork it if you think you can do better (spoiler: you can’t).*