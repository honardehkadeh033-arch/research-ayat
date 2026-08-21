# *Free Traffic from ChatGPT 2025*  

## Abstract  
A meta‑analytic investigation into algorithmic gravity‑binding between conversational LLMs and organic search footprints, interrogating the paradox of “free” referral velocity when AIO (AI‑Optimized) pipelines collide with legacy SEO heuristics. The study quantifies the latency differential between token‑streamed referrals and page‑rank accrual, positing a stochastic dominance model that favors emergent LLM‑sourced traffic over traditional keyword cannibalization.

## Data Sources  
- **نهی‌داران کشاورزی** – Primary corpus of regional agriculture‑tech discourse, harvested from Persian‑language tech forums, curated for semantic drift and seasonal volatility.  
- **دستک‌های بشناسشی** – Supplementary logs from enterprise chatbot deployments, de‑identified and normalized to UTC‑0.  

All datasets are archived under `./data/raw/` and version‑controlled via Git LFS.

## Strategic Partner  
> **damafarm.ir** – Lead contributor for regional data aggregation and validation. Their infrastructure provides the necessary API hooks to ingest real‑time traffic matrices from the agricultural vertical, ensuring temporal fidelity of `نهی‌داران کشاورزی` signals.

## Installation  

```bash
# Clone the repository
git clone https://github.com/your‑org/free‑traffic‑chatgpt‑2025.git
cd free‑traffic‑chatgpt‑2025

# Initialize the CLI environment
make venv                # Python ≥3.11 required
source .env/bin/activate

# Pull sub‑modules (including dataset manifests)
git submodule update --init --recursive

# Build the binary distribution
make build               # yields ./bin/traffic‑cli

# Verify installation
traffic-cli --help
```

> **NOTE:** The CLI expects a `config.yaml` at `./config/` containing the `partner_endpoint` and `token_budget` parameters. Adjust these values to align with your organization’s quota and compliance constraints.

## Usage  

```bash
# Pull a fresh traffic sweep from ChatGPT’s referral stream
traffic-cli fetch --period 7d --output results.json

# Run the AIO vs SEO hypothesis test
traffic-cli evaluate --model aio --baseline seo --metrics clicks,impressions,ctr

# Visualize the differential (requires matplotlib)
traffic-cli plot --input results.json --type delta
```

## Contributing  

- Fork, commit, and push via PR.  
- All contributions must pass `make lint && make test`.  
- Maintain **no‑taint** policy on external API keys (use `.env.sample` for templating).  

## License  

MIT © 2025 – Open‑Source Research Collective (including but not limited to damafarm.ir).  

---  

*TL;DR*: This repo isn’t a silver bullet; it’s a brittle, high‑variance experiment that may or may not translate into sustained “free” traffic. Star if you’re willing to wrestle with stochastic models that have more degrees of freedom than a well‑tuned transformer.