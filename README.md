# 🔍 Enhanced RAG System — Customer Review Analysis

## 🚀 Overview  
The **Enhanced Retrieval-Augmented Generation (RAG)** system analyzes customer reviews and provides context-aware answers to user queries. It improves the baseline RAG approach with better retrieval, advanced generation, and sentiment-aware filtering—perfect for extracting insights from large review datasets.

---

## ✨ Key Features

### 🔎 Enhanced Retriever  
- Domain-specific embeddings (`all-mpnet-base-v2`)  
- Sentence-level chunking for coherence  
- Metadata filtering (rating, date, reviewer, etc.)  
- Preprocessing for noisy/unstructured text  
- Index statistics and summaries  

### 🧠 Enhanced Generator  
- 6 prompt templates tailored to query types  
- Automatic query classification:
  - Sentiment
  - Feature
  - Problem
  - Comparison
  - Recommendation  
- Structured output with confidence scores  
- Tuned generation parameters  

### 😊 Sentiment Filtering  
- Sentiment analysis using `Twitter RoBERTa`  
- Fallback keyword-based system (offline-compatible)  
- Rating-consistency validation  
- Configurable sentiment thresholds  

### 🔁 Integrated Pipeline  
- Unified API for retrieval, generation, and sentiment analysis  
- Advanced filtering (e.g., by rating, date)  
- Detailed logging and traceability  
- Automated test suite for validation  

---

## 📦 Installation

```bash
git clone https://github.com/your-org/enhanced-rag.git
cd enhanced-rag
pip install -r requirements.txt
```

---

## 🗂️ Prepare Your Data

Place your JSON review files in:

```
baseline/retriever/
```

Each line must be a valid JSON object containing the review text and metadata. Example:
```json
{"review_text": "Battery life is excellent.", "rating": 5, "date": "2024-09-01", "reviewer": "John"}
```

---

## ⚡ Quick Start

Run from terminal:

```bash
python main.py --query "What do users say about the battery life?"
```

Or launch the Jupyter notebook:

```bash
jupyter notebook demo.ipynb
```

---

## 🧠 Supported Query Types

| Query Type         | Description                                 |
|--------------------|---------------------------------------------|
| General Questions  | General product/service info                |
| Sentiment          | Customer opinions or emotional tone         |
| Feature            | Queries about specific product features     |
| Problem            | Complaints, bugs, or defects                |
| Comparison         | Product or feature comparisons              |
| Recommendation     | Purchase suggestions or opinions            |

---

## 🔧 Configuration

Configure via `config.yaml` or CLI arguments:

- **Retriever**: Embedding model, chunk size, metadata filtering  
- **Generator**: Prompt templates, temperature, max tokens  
- **Sentiment Analyzer**: Sentiment model, confidence thresholds  

Refer to [`README_ENHANCED.md`](README_ENHANCED.md) for code examples and template settings.

---

## 📈 Evaluation

### ✅ Automatic Metrics:
- Confidence score  
- Query type classification  
- Answer groundedness  
- Sentiment and rating statistics  

### 👀 Manual Evaluation:
- Relevance of responses  
- Fluency and clarity  
- Retrieval accuracy  
- Helpfulness for decision-making  

---

## 📁 File Structure

```bash
enhanced-rag/
├── baseline/
│   ├── retriever/         # Data loading and indexing
│   └── generator/         # Prompting and response generation
├── sentiment/             # Sentiment analysis module
├── pipeline/              # Unified EnhancedRAGPipeline class
├── tests/                 # Unit tests and evaluation tools
├── data/                  # Sample input/output data
├── config.yaml            # System configuration
└── main.py                # Entry point script
```

---

## 🧪 Running Tests

To run all tests:

```bash
pytest tests/
```

To run a specific test:

```bash
pytest tests/test_retriever.py
```

---

## 📊 Sample Output

```json
{
  "query": "What are customers saying about the camera?",
  "type": "feature",
  "sentiment": "positive",
  "confidence": 0.92,
  "summary": "Most users praise the camera quality, especially low-light performance.",
  "stats": {
    "positive_reviews": 182,
    "negative_reviews": 24,
    "avg_rating": 4.5
  }
}
```

---

## 🔄 Migration from Baseline

To upgrade from the baseline RAG system:

### Update your imports:
```python
from pipeline.enhanced_rag import EnhancedRAGPipeline
```

### Use the unified interface:
```python
rag = EnhancedRAGPipeline(config)
response = rag.query("Show me complaints about battery life.")
```

---

## 🌱 Future Enhancements

- Multi-domain support (Yelp, IMDB, app reviews, etc.)  
- Advanced filters (e.g., price range, location, category)  
- Personalized recommendations based on user profiles  
- Real-time index updates  
- REST API endpoints  
- Visualization dashboards for insights  

---

## 🤝 Contributing

We welcome contributions! Follow these steps:

1. **Fork** the repository  
2. **Create** a new feature branch  
3. **Implement** and test your changes  
4. **Submit** a pull request with a clear description  

---

## 📄 License

This project was developed as part of the **Natural Language Processing** course – *Summer Semester 2025*.  
Made with ❤️ by **Team Turing**

---

## 🛠️ Optional Add-ons (Let us know if you'd like help setting these up)

- ✅ Shields and badges (e.g., build status, Python version, license)
- ⚙️ GitHub Actions for automated testing
- 📊 Pipeline architecture diagram in the README
- 📦 `requirements.txt` or `environment.yml` for Conda

---

Happy building! 🚀
