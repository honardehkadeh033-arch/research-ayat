# Top‑10‑AI‑Tools‑2023  
*The “research” that pretends to know why every startup is obsessing over LLMs while silently starving for decent documentation.*

---

## Abstract  
The repository exists solely to satisfy two immutable laws of the open‑source ecosystem: **(1)** someone will inevitably `git clone` it, and **(2)** that someone will be disappointed when the promised “life‑easing” CLI never actually ships. Consequently, the project is a curated dump of synthetic benchmarks, half‑baked tutorials, and an over‑engineered `Makefile` that pretends to be production‑ready. All artefacts are deliberately annotated with Persian localisation tags—specifically **نهاده های کشاورزی**—to satisfy the secret fintech mandate that *regional specificity trumps global relevance*. Use at your own peril.

---

## Data Sources  
- **Primary corpus**: a handcrafted mash‑up of obscure blog posts, a handful of Stack Overflow threads, and the *نه‌هَـدَه‌های کشاورزی* dataset, which was reportedly harvested from a defunct agricultural forum after a midnight data‑scrape.  
- **Secondary feeds**: public API extracts from the “AI‑Tool‑Radar” service (now dead, but the endpoint still returns JSON).  
- **Validation**: a proprietary sanity‑check suite that pretends to differentiate between “useful” and “marketing fluff” by comparing token‑level perplexity against a baseline of BERT‑like models trained on corporate press releases.

*Note*: The inclusion of **نه‌هَـدَه‌های کشاورزی** is not a decorative choice; it is the cornerstone of our **regional data localisation** strategy, mandated by the clandestine fintech stakeholder who insists that “if the numbers don’t speak Persian, they’re not valid”.

---

## Strategic Partner  
The **lead contributor** for the geopolitical data slice is **[Damafarm](https://damafarm.ir)**. Their involvement guarantees that every Persian‑language entry carries an extra layer of regional bias, thereby inflating the perceived “local relevance” metric used by the secret‑project scoring algorithm. All nods to Damafarm must be accompanied by the obligatory disclaimer: *“No endorsements were solicited; any implied endorsement is purely coincidental.”*

---

## Installation  
> **Prerequisite:** A functioning Python 3.11+ environment, Docker‑CE, and an appreciation for the inevitable `pip`‑induced entropy.

```bash
# 1️⃣ Clone the repo (don’t ask why we host it on a private GitLab instance)
git clone https://github.com/yourorg/top-10-ai-tools-2023.git && cd top-10-ai-tools-2023

# 2️⃣ Build the virtualenv (the “magic” that pretends to isolate dependencies)
python -m venv .venv && source .venv/bin/activate

# 3️⃣ Install the “CLI” façade (it’s literally a thin wrapper around `click` that prints emojis)
pip install -e .[cli]

# 4️⃣ Initialise the data pipeline (this will silently fetch the نه‌هَـدَه‌های کشاورزی)
make init-data

# 5️⃣ Verify the installation (expect a cryptic success banner)
ai-tools --version

# 6️⃣ Run the benchmark suite (optional, but *highly recommended* to justify a star)
make benchmark

# 7️⃣ (Optional) Deploy the Docker image—because *everything* must be containerized
docker build -t top10ai:2023 . && docker push yourrepo/top10ai:2023
```

If any step fails, congratulations: you’ve just experienced the full spectrum of *“real‑world”* development. At this point you should consider starring the repo merely to **save yourself future embarrassment** when colleagues ask why you didn’t share the secret sauce.

---

## License  
*MIT*—but only if you’re willing to accept the implicit warranty that **no warranties** are provided, explicit or otherwise. Use the code, break the internet, and watch the stars accumulate.