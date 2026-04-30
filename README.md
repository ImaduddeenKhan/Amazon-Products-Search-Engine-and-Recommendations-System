# 🛍️ Amazon Product Search & Recommendation Engine
**NLP-powered search and recommendations over real Amazon catalog data.**

A Streamlit web app that transforms product queries into **top-10 relevant recommendations** using TF-IDF and cosine similarity — ideal for showcasing practical ML + NLP skills in e-commerce.

![Build](https://img.shields.io/badge/build-manual-lightgrey)
![License](https://img.shields.io/badge/license-not%20specified-lightgrey)
![Python](https://img.shields.io/badge/python-3.x-blue)
![Streamlit](https://img.shields.io/badge/streamlit-1.x-FF4B4B)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-ML-F7931E)
![NLTK](https://img.shields.io/badge/NLTK-NLP-0C55A5)

---

## ✅ At a Glance (1-Minute Summary)
- **What it does:** Searches an Amazon-style catalog and returns the **10 most similar products** to any query.
- **Why it matters:** Demonstrates how search and recommendation engines power product discovery at scale.
- **Key features:** NLP preprocessing, TF-IDF vectorization, cosine similarity ranking, Streamlit UI.
- **Tech stack:** Python, Pandas, NLTK, scikit-learn, Streamlit.

---

## 🚀 Project Overview
This project delivers a compact yet powerful **search + recommendation engine** over real product metadata. Users type a product query, and the system surfaces the most relevant items based on semantic similarity. It’s a clean, production-style demo of how modern e-commerce search works under the hood.

## 🧠 Problem & Solution
**Problem:** Large online catalogs make it hard to quickly find the best matching products.

**Solution:** An NLP pipeline that preprocesses product text, converts it to vectors with TF-IDF, and ranks results with cosine similarity — all wrapped in an interactive UI for instant exploration.

## ✨ Features
- **Top-10 ranked recommendations** for any query
- **Real Amazon dataset** (Title, Description, Category)
- **NLP preprocessing** (tokenization + stemming)
- **TF-IDF vectorization** for semantic relevance
- **Streamlit UI** for fast, clean interaction

## 🛠 Tech Stack
- **Python**
- **Pandas** for data handling
- **NLTK** for tokenization and stemming
- **scikit-learn** for TF-IDF and cosine similarity
- **Streamlit** for the web interface

## 📸 Screenshots / Demo
![Screenshot of the Streamlit interface displaying a product search query and the top-10 ranked product recommendations with titles and descriptions](img.jpeg)

## ⚙️ Installation & Setup
> Requires Python 3.x

```bash
# 1) (Optional) Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate

# 2) Install dependencies
pip install pandas numpy nltk scikit-learn streamlit pillow

# 3) Download required NLTK data (punkt is required for word_tokenize)
python -m nltk.downloader punkt

# 4) Run the app
streamlit run app.py
```

> Note: The current app only needs `punkt` for tokenization. `SnowballStemmer` ships with NLTK, and stopwords are not used in this version.

**Dataset:** The included `amazon_product.csv` must remain in the project root. Current header (note mixed casing): `id`, `Title`, `Description`, `Category`. This matches the source dataset, and the app expects these exact names unless you normalize them in code (e.g., all lowercase) and update the app accordingly.

## 📂 Project Structure
```
.
├── app.py              # Streamlit app + recommendation logic
├── amazon_product.csv  # Product dataset
├── img.jpeg            # UI screenshot
└── README.md           # Project documentation
```

## 🔮 Future Improvements
- Query spell-correction and autocomplete
- Model caching for faster startup
- Scalable vector search (FAISS / ANN)
- Deployed public demo

## 🤝 Contribution Guidelines
Contributions are welcome!
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-change`)
3. Commit your changes
4. Open a pull request with a clear description

## 📜 License
No license is specified yet (default: all rights reserved). For permissions or licensing questions, please open an issue or contact the repository owner.
