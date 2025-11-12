# 🧠 NLP Pre-Processing Pipeline with Gradio

This project demonstrates a complete **Natural Language Processing (NLP) pre-processing pipeline** using **SpaCy**, **NLTK**, and **Gradio**.
It provides both a **text-based interface** (for single text input) and a **dataset-based interface** (for bulk processing from CSV/Excel files).

---

## 🚀 Features

- ✅ Run **individual NLP tasks** or a **full pipeline**
- ✅ Process **single text input** or **entire dataset columns**
- ✅ Choose between **stemming** or **lemmatization** in the full pipeline
- ✅ User-friendly **Gradio interface** with tabs for each function
- ✅ Supports `.csv` and `.xlsx` file formats

---

## 🧩 Pre-Processing Pipeline

Each NLP stage transforms the text in a specific way.
The available steps are:

| Step                               | Description                                                          |
| ---------------------------------- | -------------------------------------------------------------------- |
| **Tokenization**                   | Splits text into individual tokens (words, punctuation).             |
| **Stop Words**                     | Removes common words that carry less meaning (e.g., “the”, “and”).   |
| **Stemming**                       | Reduces words to their root form using NLTK’s `PorterStemmer`.       |
| **Lemmatization**                  | Converts words to their base form using SpaCy (context-aware).       |
| **POS Tagging**                    | Assigns parts of speech (noun, verb, adjective, etc.) to each token. |
| **NER (Named Entity Recognition)** | Detects named entities like people, locations, or organizations.     |

---

## ⚙️ Tech Stack

- **Python** – main language
- **pandas** – for dataset handling
- **NLTK** – for stemming and stop-word filtering
- **SpaCy** – for tokenization, lemmatization, POS, and NER
- **Gradio** – for building the interactive interface

---

## 🖥️ User Interface Overview

The app provides two main tabs:

### 🔹 1. Text Tab

- Choose an NLP task (or full pipeline).
- Enter text directly into the textbox.
- See results instantly in structured JSON format.
- When running the **Full Pipeline**, select _stemming_ or _lemmatization_ mode.

### 🔹 2. Dataset Tab

- Upload a `.csv` or `.xlsx` file.
- Select a column (or “All Columns”) to process.
- Choose which NLP function to apply.
- View processed results in JSON format.
- “Full Pipeline” option also allows _stemming_ or _lemmatization_.

---

## ▶️ Run the Application

Clone repository and import the required libraries

```bash
python app.py
```

Once started, Gradio will launch in your browser (e.g., `http://127.0.0.1:7860`).

---

## 📁 Example Use

**Text Mode:**

```text
Input: "Apple is looking at buying U.K. startup for $1 billion."
Output: JSON with tokens, POS tags, entities, and optional lemmatization or stemming.
```

**Dataset Mode:**

- Upload `reviews.csv`
- Select “review_text” column
- Choose “Full Pipeline”
- View processed tokens, entities, etc., for each row.

---

## 🧱 Example Output (Full Pipeline)

```json
{
  "tokenize": [
    "Apple",
    "is",
    "looking",
    "at",
    "buying",
    "U.K.",
    "startup",
    "for",
    "$",
    "1",
    "billion",
    "."
  ],
  "stop_words": ["Apple", "looking", "buying", "U.K.", "startup", "billion"],
  "pos_tagging": [
    ["Apple", "PROPN"],
    ["looking", "VERB"],
    ["startup", "NOUN"]
  ],
  "ner": [
    ["Apple", "ORG"],
    ["U.K.", "GPE"],
    ["$1 billion", "MONEY"]
  ],
  "lemmatized": [
    "Apple",
    "be",
    "look",
    "at",
    "buy",
    "U.K.",
    "startup",
    "for",
    "$",
    "1",
    "billion",
    "."
  ]
}
```

---

## 🏁 Summary

This project provides a **modular and interactive NLP pre-processing system** built with traditional, well-established libraries.
It’s ideal for **data cleaning, NLP model preparation, and educational demonstrations**.
