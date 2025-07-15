# NewsCrunch

**NewsCrunch** is a work-in-progress news summarization pipeline that fetches and distills yesterday’s top headlines into short, digestible summaries. It pulls articles using the GNews API, extracts full content, and summarizes them using the `facebook/bart-large-cnn` transformer model. The output is structured and concise, suitable for mobile delivery.

---

## 🔧 Features

- **API-Powered Fetching**: Uses GNews API to retrieve top stories in key categories (World, Business, Technology)
- **Full Text Extraction**: Parses full article bodies via `newspaper3k`, skipping shallow blurbs
- **Transformer-Based Summarization**: Uses BART-Large-CNN for high-quality abstractive summaries
- **Category-Wise Output**: Summaries are grouped by category in JSON format
- **Noise Filtering**: Removes duplicate, irrelevant, and content-deficient entries

---

## 🛠️ Tech Stack

- Python 3.9+
- HuggingFace Transformers
- `facebook/bart-large-cnn` summarizer
- `newspaper3k`
- GNews API
- tqdm for progress feedback

---

## 📦 Output

The tool generates a `daily_summary.json` file with this structure:

```json
{
  "world": [
    "Concise summary 1...",
    "Concise summary 2..."
  ],
  "business": [
    "Concise summary 1...",
    ...
  ],
  "technology": [
    ...
  ]
}
