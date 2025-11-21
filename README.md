# spaCy vs BERT Tokenization (Hugging Face)

This mini project compares **spaCy’s linguistic tokenization** with **BERT’s WordPiece tokenization** (via Hugging Face) and shows how their tokens align at the character-level using offset mappings.

It is implemented as a single, clean Jupyter notebook.

---

## 🎯 Goal

When working with transformer models you often need to:

- Understand how **word-level** tokens (like spaCy’s) relate to
- **Subword-level** tokens (like BERT’s WordPiece: `de`, `##posit`)
- Handle **special tokens** such as `[CLS]` and `[SEP]`
- Align everything back to the **original text** via character offsets

This notebook makes that process explicit and easy to see.

---

## 🧠 What This Project Demonstrates

- **Modern NLP tooling**
  - Using **spaCy** for standard linguistic tokenization
  - Using **Hugging Face**’s `BertTokenizerFast` for WordPiece subword tokenization

- **Tokenization & alignment concepts**
  - How a normal sentence is split into:
    - spaCy tokens (words, punctuation)
    - BERT subwords with `[CLS]` / `[SEP]`
  - Using `offset_mapping` to map tokens back to **(start, end)** character spans
  - Inspecting `special_tokens_mask` to identify special tokens

- **Practical debugging with tokenizers**
  - Understanding the structure of the tokenizer output (`input_ids`, `offset_mapping`, `special_tokens_mask`, etc.)
  - Fixing common issues like missing fields (`KeyError: 'special_tokens_mask'`) by setting `return_special_tokens_mask=True`.

- **Clean, reproducible notebook**
  - A single notebook that installs dependencies, downloads the spaCy model, and runs example comparisons end-to-end.

---


├── README.md                     # Project documentation
└── requirements.txt              # (Optional) Python dependencies
