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

## 🚀 How to Run

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/amharic-ner-ethiomart.git
cd amharic-ner-ethiomart

