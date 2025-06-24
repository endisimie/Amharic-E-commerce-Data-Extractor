# Amharic-E-commerce-Data-Extractor

This project is part of **EthioMart's initiative** to build a centralized Telegram-based e-commerce platform for Ethiopia. It focuses on extracting key business entities — such as **product names**, **prices**, and **locations** — from Amharic text shared in Telegram channels.

---

## 📌 Project Tasks Covered

### ✅ Data Ingestion & Preprocessing
Automated collection and preparation of raw Amharic text data from public e-commerce Telegram channels.

#### 🔧 Steps:
1. **Connect to Telegram API**
   - Authenticate using `api_id` and `api_hash` via Telethon.
2. **Scrape Telegram Messages**
   - Fetch up to `N` messages from selected public channels.
   - Capture text, images, and timestamps.
3. **Preprocess Messages**
   - Clean Amharic text (emoji, special characters, whitespace).
   - Normalize numbers and punctuations.
   - Optionally remove stopwords.
4. **Structured Storage**
   - Store cleaned messages and metadata to a `.csv` file.
   - Media (e.g., images) saved in folders named by channel.

> ✅ Output: `cleaned_messages.csv` + image folders per channel

---

### ✅  Manual Annotation in CoNLL Format

A subset of messages was labeled manually for **Named Entity Recognition (NER)** using the standard CoNLL BIO tagging format.

#### 🧾 Entity Labels:
- `B-Product`, `I-Product`: Product names
- `B-PRICE`, `I-PRICE`: Price values
- `B-LOC`, `I-LOC`: Locations (e.g., cities, districts)
- `O`: Non-entity tokens



---

### ✅ Task 3: Fine-Tune Amharic NER Model
- Used `Davlan/afro-xlmr-base` as a multilingual transformer model.
- Data labeled in CoNLL format (`amharic_ner_sample.conll`).
- Trained using HuggingFace’s `Trainer API`.
- Final model metrics:
  - **Precision**: ~0.81
  - **Recall**: ~0.78
  - **F1-Score**: ~0.79

### ✅ Task 4: Model Comparison & Selection
- Compared multiple multilingual models:
  - `afro-xlmr-base`
  - `bert-tiny-amharic` (restricted access)
  - `xlm-roberta-base`
- Evaluated on precision, recall, training time, and ability to handle Amharic.
- Selected `afro-xlmr-base` as the final model for deployment.

### ✅ Task 5: Model Interpretability
- Implemented **LIME** to understand token-level NER predictions.
- Applied **SHAP** to analyze entity importance distribution.
- Results saved to `lime_interpretation.html` and SHAP text plots.

### ✅ Task 6: Vendor Scorecard for Micro-Lending
- Created a scoring engine based on:
  - **Posting frequency**
  - **Average views per post**
  - **Average product price**
  - **Top-performing post**
- Designed a composite **Lending Score**:

## 🚀 How to Run

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/amharic-ner-ethiomart.git
cd amharic-ner-ethiomart

