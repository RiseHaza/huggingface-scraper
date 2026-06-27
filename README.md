[Huggingface Scraper](https://apify.com/automation-lab/huggingface-scraper?fpr=data)

## What does Hugging Face Scraper do?

**Hugging Face Scraper** extracts data from [Hugging Face Hub](https://huggingface.co) — the world's largest platform for AI models, datasets, spaces, and research papers. Search by keyword, filter by ML task type, framework, license, or author, and sort by downloads, likes, or trending score.

It uses the **official public Hugging Face REST API** (`api.huggingface.co`) — no browser, no proxy, no API key required. Results are structured and ready for JSON, CSV, or Excel export.

Four scraping modes in one actor: **models**, **datasets**, **spaces**, and **papers**. Plus two power features for AI teams: **Trending Mode** and **Comparison Mode**.

---

## Who is it for?

### 🤖 AI/ML Engineers & Researchers

- Audit which models or datasets are most popular in your domain
- Track new releases by an organization (e.g., `meta-llama`, `google`, `mistralai`)
- Build a curated list of fine-tuned models for a specific task like `text-generation` or `image-classification`
- Monitor trending papers to stay current with the field

### 📊 AI Teams Evaluating Models

- Compare top models side-by-side: same task, filtered by license, ranked by downloads or trending score
- Find commercially-safe models (MIT, Apache 2.0) for production deployment decisions
- Pull README excerpts to quickly understand model capabilities without visiting each page
- Generate a structured comparison table in one run for team review

### 🏢 Enterprise AI Teams & Procurement

- Research vendor model availability across Hugging Face for internal tooling decisions
- Track open-source alternatives to proprietary APIs
- Create internal catalogs of approved models for compliance purposes
- Filter by specific frameworks (PyTorch, TensorFlow, ONNX, MLX) to match your infrastructure

### 🧑‍💻 Developers & Indie Hackers

- Power a model-discovery app or dashboard
- Build automated alerts when new models from a favorite organization appear
- Aggregate Hugging Face data for newsletters, blogs, or comparison sites
- Monitor weekly trending models in your domain via scheduled runs

---

## Why use Hugging Face Scraper?

- ✅ **No API key or login required** — Hugging Face's public REST API is open
- ✅ **Pure HTTP, no browser overhead** — runs in 128 MB memory, completes in seconds
- ✅ **4 resource types in one actor** — models, datasets, spaces, papers
- ✅ **Full filter support** — task type, framework, license, author, language, sort order
- ✅ **License field extracted** — know at a glance if a model is MIT, Apache 2.0, or proprietary
- ✅ **Trending models mode** — one click to get the fastest-rising models right now
- ✅ **Comparison mode** — structured side-by-side output for diffing models in CI or notebooks
- ✅ **README excerpts** — pull the first 500 chars of each model card for quick context
- ✅ **Pagination handled automatically** — extract hundreds or thousands of items
- ✅ **Export in JSON, CSV, or Excel** — directly from Apify Console or API

---

## What data can you extract?

### 🤖 Models

| Field | Description |
| --- | --- |
| `id` | Full model ID (e.g., `meta-llama/Llama-3.1-8B-Instruct`) |
| `author` | Organization or username |
| `downloads` | Total download count |
| `likes` | Community likes |
| `pipeline_tag` | ML task (e.g., `text-generation`, `image-classification`) |
| `library_name` | Framework (e.g., `transformers`, `diffusers`) |
| `license` | License identifier extracted from tags (e.g., `mit`, `apache-2.0`, `llama3.1`) |
| `tags` | Full tag list including license, datasets, languages |
| `createdAt` | Creation date |
| `lastModified` | Last update date |
| `gated` | Whether model requires access approval |
| `private` | Whether model is private |
| `readmeExcerpt` | First 500 characters of the model card README (requires `includeReadmeExcerpt: true`) |
| `url` | Direct link to model page |

### 📦 Datasets

| Field | Description |
| --- | --- |
| `id` | Dataset ID (e.g., `squad`, `m-a-p/FineFineWeb`) |
| `author` | Creator organization or username |
| `downloads` | Total download count |
| `likes` | Community likes |
| `tags` | Task categories, languages, licenses, sizes |
| `description` | First 500 characters of dataset card |
| `createdAt` | Creation date |
| `gated` | Access control status |
| `disabled` | Whether dataset is disabled |
| `url` | Direct link to dataset page |

### 🚀 Spaces

| Field | Description |
| --- | --- |
| `id` | Space ID (e.g., `open-llm-leaderboard/open_llm_leaderboard`) |
| `author` | Creator |
| `likes` | Community likes |
| `sdk` | Runtime SDK (`gradio`, `streamlit`, `docker`, `static`) |
| `tags` | Space tags |
| `createdAt` | Creation date |
| `url` | Direct link to space |

### 📄 Papers

| Field | Description |
| --- | --- |
| `id` | ArXiv paper ID (e.g., `2604.02330`) |
| `title` | Paper title |
| `authors` | Author names (array, hidden authors excluded) |
| `summary` | Full abstract / AI summary |
| `publishedAt` | Publication date |
| `upvotes` | Hugging Face upvote count |
| `thumbnailUrl` | Social preview image URL |
| `projectPage` | Project website |
| `githubRepo` | GitHub repository link |
| `url` | Hugging Face papers link |

---

## How much does it cost to scrape Hugging Face?

This actor uses **pay-per-event (PPE)** pricing — you pay only for what you extract. No monthly subscription. All platform costs included.

|  | Free | Starter ($29/mo) | Scale ($199/mo) | Business ($999/mo) |
| --- | --- | --- | --- | --- |
| **Per item** | $0.00115 | $0.001 | $0.00078 | $0.0006 |
| **1,000 items** | $1.15 | $1.00 | $0.78 | $0.60 |
| **10,000 items** | $11.50 | $10.00 | $7.80 | $6.00 |

Higher-tier plans get additional volume discounts.

**Real-world cost examples:**

| Query | Items | Duration | Cost (Free tier) |
| --- | --- | --- | --- |
| Top 20 trending models | 20 | ~2s | ~$0.023 |
| MIT-licensed text-generation models | 50 | ~5s | ~$0.058 |
| Top 100 trending datasets | 100 | ~5s | ~$0.115 |
| 500 text-generation models | 500 | ~15s | ~$0.575 |
| 20 models with README excerpts | 20 | ~15s | ~$0.023 |

**Free plan estimate:** With Apify's free $5 credit, you can extract ~4,300 items (or ~170 models with README excerpts enabled).

---

## How to scrape Hugging Face Hub

1. Open **[Hugging Face Scraper on Apify Store](https://apify.com/automation-lab/huggingface-scraper)**
2. Click **Try for free** — log in or create a free Apify account
3. Choose a **Resource type**: Models, Datasets, Spaces, or Papers
4. Enter a **Search query** (or leave blank to browse trending items)
5. Set **Max items** to limit results (start small — e.g., 20)
6. Optionally set filters: **Task type**, **Library**, **License**, **Author**, **Language**
7. Click **Start** and wait a few seconds for results
8. Download results as **JSON**, **CSV**, or **Excel**

**Example: Get the hottest trending models right now**

```
{
  "trendingMode": true,
  "maxItems": 50
}
```

**Example: Find commercially-safe text generation models**

```
{
  "resourceType": "models",
  "pipelineTag": "text-generation",
  "license": "apache-2.0",
  "sortBy": "downloads",
  "maxItems": 50
}
```

**Example: Compare top PyTorch image classifiers side-by-side**

```
{
  "resourceType": "models",
  "pipelineTag": "image-classification",
  "library": "pytorch",
  "sortBy": "downloads",
  "maxItems": 20,
  "comparisonMode": true,
  "includeReadmeExcerpt": true
}
```

**Example: All datasets from a specific author**

```
{
  "resourceType": "datasets",
  "author": "allenai",
  "sortBy": "downloads",
  "maxItems": 100
}
```

**Example: Recent AI papers**

```
{
  "resourceType": "papers",
  "searchQuery": "multimodal reasoning",
  "maxItems": 30
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
| --- | --- | --- | --- |
| `resourceType` | string | `models` | Resource to scrape: `models`, `datasets`, `spaces`, `papers` |
| `searchQuery` | string | — | Keyword to filter results. Leave empty to browse all. |
| `maxItems` | integer | `100` | Max items to extract. Set `0` for unlimited. |
| `trendingMode` | boolean | `false` | **New:** Overrides resource type to models and sort to trendingScore. Surfaces fastest-rising models. |
| `comparisonMode` | boolean | `false` | **New:** Saves a structured comparison table to the KV store under key `MODEL_COMPARISON`. Models only. |
| `includeReadmeExcerpt` | boolean | `false` | **New:** Fetches first 500 chars of each model's README card. One extra request per model — use with small `maxItems`. |
| `sortBy` | string | `downloads` | Sort by: `downloads`, `likes`, `trendingScore`, `createdAt`, `lastModified` |
| `pipelineTag` | string | — | Filter by ML task (e.g., `text-generation`, `image-classification`). Dropdown with 28 task types. |
| `library` | string | — | Filter by framework (e.g., `transformers`, `pytorch`, `onnx`). Dropdown with 18 frameworks. |
| `license` | string | — | **New:** Filter by license (e.g., `mit`, `apache-2.0`). Dropdown with 20+ license types. |
| `author` | string | — | Filter by author/organization username |
| `language` | string | — | Filter by language code (e.g., `en`, `fr`, `zh`) |
| `batchSize` | integer | `100` | Items per API request (1–100). Reduce if rate limited. |
| `maxRetries` | integer | `3` | Retry attempts for failed requests |

**Notes:**

- `trendingMode` overrides `resourceType` and `sortBy`
- `comparisonMode` and `includeReadmeExcerpt` apply to models only
- `pipelineTag` does not apply to spaces or papers
- `library` and `license` only apply to models
- Spaces don't support `downloads` sorting — falls back to `likes`
- Set `maxItems: 0` only for author or pipeline-filtered queries; unfiltered full crawls can hit millions of items
- `includeReadmeExcerpt: true` adds one HTTP request per model — keep `maxItems` ≤ 20 for fast runs

---

## Output examples

**Model output (with new fields):**

```
{
  "type": "model",
  "id": "openai-community/gpt2",
  "author": "openai-community",
  "downloads": 12712959,
  "likes": 3173,
  "pipeline_tag": "text-generation",
  "library_name": "transformers",
  "license": "mit",
  "tags": ["transformers", "pytorch", "gpt2", "text-generation", "en", "license:mit"],
  "createdAt": "2022-03-02T23:29:04.000Z",
  "lastModified": "2024-11-15T08:00:00.000Z",
  "gated": false,
  "private": false,
  "readmeExcerpt": "# GPT-2 Pretrained model on English language using a causal language modeling (CLM) objective...",
  "url": "https://huggingface.co/openai-community/gpt2",
  "scrapedAt": "2026-04-05T10:00:00.000Z"
}
```

**Comparison mode output** (saved to KV store key `MODEL_COMPARISON`):

```
[
  {
    "rank": 1,
    "id": "openai-community/gpt2",
    "author": "openai-community",
    "pipeline_tag": "text-generation",
    "library_name": "transformers",
    "license": "mit",
    "downloads": 12712959,
    "likes": 3173,
    "lastModified": "2024-11-15T08:00:00.000Z",
    "gated": false,
    "readmeExcerpt": "# GPT-2 Pretrained model on English language...",
    "url": "https://huggingface.co/openai-community/gpt2"
  }
]
```

**Paper output:**

```
{
  "type": "paper",
  "id": "2604.02329",
  "title": "Generative World Renderer",
  "authors": ["Zheng-Hui Huang", "Zhixiang Wang"],
  "summary": "We present a novel approach to world rendering...",
  "publishedAt": "2026-04-02T00:00:00.000Z",
  "upvotes": 86,
  "thumbnailUrl": "https://cdn-thumbnails.huggingface.co/social-thumbnails/papers/2604.02329.png",
  "projectPage": "",
  "githubRepo": "",
  "url": "https://huggingface.co/papers/2604.02329",
  "scrapedAt": "2026-04-04T10:00:00.000Z"
}
```

---

## Tips for best results

- 🔥 **Use Trending Mode** — enable `trendingMode: true` for instant access to the hottest models, no filters needed
- 📊 **Combine comparison + README** — set `comparisonMode: true` and `includeReadmeExcerpt: true` with `maxItems: 10-20` to get a full AI team evaluation package in one run
- ⚖️ **Filter by license first** — use `license: "apache-2.0"` or `license: "mit"` to pre-screen for commercially safe models before diving deeper
- 🔢 **Start small** — set `maxItems: 20` for your first run to verify the output shape before scaling up
- 🏷️ **Combine filters** — author + pipelineTag + library gives precise results (e.g., Google's text-classification Transformers models)
- 📈 **Use `trendingScore` sort** — captures models gaining momentum in the past week, not just all-time giants
- 🔄 **Schedule for monitoring** — run daily to track new releases from a specific author or new papers in your research area
- ⚠️ **Avoid `maxItems: 0` on broad queries** — Hugging Face has 500,000+ models; an unlimited run could take hours
- 📄 **README excerpts are slow** — each model needs an extra HTTP request; keep `maxItems ≤ 20` when `includeReadmeExcerpt` is enabled
- 🌐 **Language filtering** — use ISO 639-1 codes: `en`, `zh`, `fr`, `de`, `es`, `ja`, `ar`, `pt`, `ru`, `ko`

---

## AI team model evaluation workflow

This actor is purpose-built for AI teams that need to quickly survey the model landscape for a decision.

**Step 1: Discover trending candidates**

```
{ "trendingMode": true, "pipelineTag": "text-generation", "maxItems": 20 }
```

**Step 2: Filter by your license requirements**

```
{ "resourceType": "models", "pipelineTag": "text-generation", "license": "apache-2.0", "sortBy": "downloads", "maxItems": 20 }
```

**Step 3: Deep compare top candidates**

```
{
  "resourceType": "models",
  "pipelineTag": "text-generation",
  "license": "apache-2.0",
  "library": "transformers",
  "sortBy": "downloads",
  "maxItems": 10,
  "comparisonMode": true,
  "includeReadmeExcerpt": true
}
```

The comparison output goes to the **Key-Value Store** tab under key `MODEL_COMPARISON` — a clean ranked JSON array with license, downloads, likes, framework, and README context. Ready to paste into a spreadsheet, notebook, or PR review.

---

## Integrations

**Hugging Face Scraper → Google Sheets for team model reviews**
Run weekly with `comparisonMode: true` on your target task type. Export the `MODEL_COMPARISON` KV key to Google Sheets via Apify's integration. Your team sees a ranked table of models with license, downloads, and descriptions — no manual research needed.

**Hugging Face Scraper → Slack trending alert**
Set up a daily scheduled run with `trendingMode: true` and a webhook that posts the top 5 trending models to your #ml-team Slack channel. Stay ahead of new model releases without constant HF browsing.

**Hugging Face Scraper → Python notebook for benchmark planning**
Use the Apify API to pull filtered model listings into a pandas DataFrame. Filter by task + framework, sort by downloads, and shortlist candidates for evaluation. Use `includeReadmeExcerpt` for a first-pass context on each model.

**Hugging Face Scraper → Make / Zapier pipeline**
Trigger downstream workflows when new papers matching a keyword appear. Route summaries to Notion, email digests, or a database for literature review automation.

**Scheduled model monitoring**
Run once a day for trending models in `text-generation` or `image-classification`. Archive results to compare week-over-week momentum for competitive intelligence.

---

## API usage

### Node.js

```
import { ApifyClient } from 'apify-client';

const client = new ApifyClient({ token: 'YOUR_APIFY_TOKEN' });

// Get trending models with comparison output
const run = await client.actor('automation-lab/huggingface-scraper').call({
  trendingMode: true,
  maxItems: 20,
  comparisonMode: true,
  includeReadmeExcerpt: true,
});

// Main dataset: full model objects
const { items } = await client.dataset(run.defaultDatasetId).listItems();

// KV store: ranked comparison table
const store = await client.keyValueStore(run.defaultKeyValueStoreId);
const comparison = await store.getRecord('MODEL_COMPARISON');
console.log(comparison.value); // ranked array
```

### Python

```
from apify_client import ApifyClient

client = ApifyClient(token="YOUR_APIFY_TOKEN")

# Find MIT-licensed text-generation models
run = client.actor("automation-lab/huggingface-scraper").call(run_input={
    "resourceType": "models",
    "pipelineTag": "text-generation",
    "license": "mit",
    "sortBy": "downloads",
    "maxItems": 50,
})

for item in client.dataset(run["defaultDatasetId"]).iterate_items():
    print(item["id"], item["license"], item["downloads"])
```

### cURL

```
curl -X POST "https://api.apify.com/v2/acts/automation-lab~huggingface-scraper/runs" \
  -H "Authorization: Bearer YOUR_APIFY_TOKEN" \
  -H "Content-Type: application/json" \
  -d '{
    "resourceType": "models",
    "pipelineTag": "image-classification",
    "library": "pytorch",
    "license": "apache-2.0",
    "sortBy": "downloads",
    "maxItems": 50,
    "comparisonMode": true
  }'
```

---

## Use with AI agents via MCP

Hugging Face Scraper is available as a tool for AI assistants that support the [Model Context Protocol (MCP)](https://docs.apify.com/platform/integrations/mcp).

### Setup for Claude Code

```
$claude mcp add --transport http apify "https://mcp.apify.com?tools=automation-lab/huggingface-scraper"
```

### Setup for Claude Desktop, Cursor, or VS Code

Add this to your MCP config file:

```
{
    "mcpServers": {
        "apify": {
            "url": "https://mcp.apify.com?tools=automation-lab/huggingface-scraper"
        }
    }
}
```

Your AI assistant will use OAuth to authenticate with your Apify account on first use.

### Example prompts

Once connected, try asking your AI assistant:

- "Use automation-lab/huggingface-scraper with trendingMode to show me what AI models are trending right now"
- "Get the top 20 MIT-licensed text-generation models from Hugging Face sorted by downloads, with README excerpts"
- "Find PyTorch image-classification models on Hugging Face with comparisonMode enabled so I can compare them"
- "Get all datasets from the allenai organization on Hugging Face sorted by downloads"
- "Fetch the latest 20 papers about multimodal reasoning from Hugging Face and summarize the key themes"

Learn more in the [Apify MCP documentation](https://docs.apify.com/platform/integrations/mcp).

---

## Legality — is it legal to scrape Hugging Face?

Hugging Face Scraper uses the **official public REST API** at `api.huggingface.co` — not web scraping or HTML parsing. This API is publicly documented, freely accessible without authentication, and intended for programmatic access.

This actor only extracts **publicly available metadata** (model names, download counts, tags, paper abstracts). It does not download model weights, datasets, or private content. All extracted data is visible to any anonymous visitor on `huggingface.co`.

As with any data collection, please:

- Respect Hugging Face's [Terms of Service](https://huggingface.co/terms-of-service)
- Don't use the data for spam, misleading AI benchmarks, or abuse of platform resources
- If you build a product using this data, consider crediting the original Hugging Face authors

This actor complies with Apify's [Ethical Web Scraping guidelines](https://apify.com/about/ethical-scraping).

---

## FAQ

**How fast does it extract data?**
Very fast — the Hugging Face API returns up to 100 items per request. Typical runs complete in 2–30 seconds for queries under 500 items. With `includeReadmeExcerpt: true`, add ~0.5s per model. Large unlimited runs (1000+ items) take 1–5 minutes depending on network conditions.

**How much does it cost to get 1,000 models?**
On the free plan: `1,000 × $0.00115 = $1.15`. On a paid Scale plan: `1,000 × $0.00078 = $0.78`. Plus the $0.001 start fee. Comparable to other Apify Hub actors.

**How does comparison mode work?**
When `comparisonMode: true`, the actor saves a ranked JSON array to the Key-Value Store under key `MODEL_COMPARISON`. Each row includes: rank, id, author, pipeline_tag, library_name, license, downloads, likes, lastModified, gated, readmeExcerpt, and url. Access it from the **Key-Value Store** tab in Apify Console, or via API: `GET /v2/key-value-stores/{storeId}/records/MODEL_COMPARISON`.

**What licenses does the license filter support?**
The input schema dropdown includes 20+ options including MIT, Apache 2.0, OpenRAIL, OpenRAIL++, Llama 3/3.1/3.2/3.3, Gemma, GPL-3.0, LGPL-3.0, BSD variants, Creative Commons variants, and more. You can also type any license identifier directly — it maps to HF's internal tag format.

**Is this the same as the official Hugging Face Python API?**
The `huggingface_hub` Python library provides similar listing functionality but requires a Python environment and coding. This actor wraps the same REST API in a no-code, schedulable, cloud-native solution — no Python environment needed, results export directly to JSON/CSV/Excel.

**Why are some models missing `lastModified` or `gated` fields?**
The basic listing endpoint doesn't include every field for performance reasons. `lastModified` and `gated` are returned when the Hugging Face API includes them in search results. For models without these fields, defaults are used (`""` and `false` respectively).

**Why do spaces show 0 for `downloads`?**
Hugging Face doesn't track download counts for Spaces — only for models and datasets. Use `likes` as the engagement metric for spaces.

**My query returns fewer items than `maxItems`. Is something wrong?**
No — the Hugging Face Hub simply has fewer matching items. This is common for narrow filters (specific author + task type + library + license). The actor stops gracefully when there's nothing more to fetch.

**README excerpts are empty even with `includeReadmeExcerpt: true`. Why?**
Some models don't have a `README.md` file in their repository, or the file requires authentication to access (gated models). For gated models, the excerpt will always be empty — this is expected.

---

## Related AI/ML scrapers and tools

- 🔬 [ArXiv Scraper](https://apify.com/automation-lab/arxiv-scraper) — Scrape research papers from ArXiv with full abstract, authors, and subjects
- 🛒 [Amazon Scraper](https://apify.com/automation-lab/amazon-scraper) — Extract product data, reviews, and pricing from Amazon
- 🍎 [Apple App Store Scraper](https://apify.com/automation-lab/apple-app-store-scraper) — Scrape app listings, ratings, and reviews from the App Store
- 🏪 [Apify Store Analyzer](https://apify.com/automation-lab/apify-store-analyzer) — Analyze actor listings and usage statistics on Apify Store
- 🛍️ [Best Buy Scraper](https://apify.com/automation-lab/bestbuy-scraper) — Extract product data and reviews from Best Buy