# Amharic E-commerce Data Extractor

## 📌 Overview

**EthioMart** aims to unify Ethiopia’s fragmented Telegram-based e-commerce scene by creating a centralized hub. This project develops a pipeline to extract and structure key business information from multiple Amharic Telegram channels using fine-tuned language models.

The system uses **Named Entity Recognition (NER)** to identify product names, prices, and locations from unstructured text, images, and documents shared in Telegram channels. This enriched data powers a centralized platform for seamless product discovery and vendor analytics.

## 🚀 Key Objectives

- Ingest and preprocess multilingual e-commerce data (mainly Amharic) from Telegram.
- Fine-tune transformer-based LLMs for Amharic NER (XLM-R, AfroXLMR, BERT-tiny).
- Label Amharic messages using CoNLL format for training.
- Compare multiple NER models using F1-score, precision, and recall.
- Apply SHAP/LIME for model interpretability.
- Design a vendor scorecard engine to support micro-lending decisions.


## 🧾 Entities Extracted

- **Required:**  
  - `Product` (e.g. shoes, jackets)  
  - `Price` (e.g. 500 ብር)  
  - `Location` (e.g. Addis Ababa, Bole)

- **Optional:**  
  - `Delivery_Fee` (e.g. "free delivery")  
  - `Contact_Info` (e.g. phone numbers, Telegram handles)


## 🧪 Tasks Breakdown

### ✅ Task 1: Data Collection & Preprocessing
- Connect to at least 5 Telegram e-commerce channels.
- Scrape messages, metadata, and images in real time.
- Normalize Amharic text and store structured data.

### ✅ Task 2: Data Labeling
- Label 30–50 messages in **CoNLL format**.
- Apply BIO tagging (B-Product, I-LOC, B-PRICE, O, etc.)

### ✅ Task 3: Model Fine-tuning
- Use Hugging Face's `transformers` + Google Colab.
- Models: `XLM-R`, `bert-tiny-amharic`, `AfroXLMR`
- Align labels with tokens and train with `Trainer API`.

### ✅ Task 4: Model Comparison
- Evaluate models based on F1-score, training time, etc.
- Recommend the best model for production.

### ✅ Task 5: Model Interpretability
- Apply `SHAP` and `LIME` to explain NER predictions.
- Analyze ambiguous samples and visualize token impact.

### ✅ Task 6: Vendor Scorecard (FinTech Use Case)
- Compute:
  - Average Views/Post  
  - Posts/Week  
  - Avg. Product Price  
  - Lending Score = `(Views * 0.5) + (Posts/week * 0.5)`
- Present results in a summary report.


## Data Sources

- Telegram e-commerce channels (e.g., `@ShagerOnlineStore`)
- Amharic NER dataset (publicly available)
- Amharic message text and related images


## 🛠 Tech Stack

- **Language:** Python 3.10+
- **LLMs:** Hugging Face Transformers (XLM-R, AfroXLMR, mBERT)
- **Labeling:** CoNLL Format
- **Model Explainability:** SHAP, LIME
- **Data Sources:** Telegram Bots API or custom scrapers
