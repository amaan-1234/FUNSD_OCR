````markdown
# 🧾 Form Understanding with LayoutLMv3 on FUNSD

This project demonstrates **form understanding from scanned document images** using [LayoutLMv3](https://huggingface.co/microsoft/layoutlmv3-base), a transformer model that jointly understands text, layout, and image features. We fine-tune the model on the **FUNSD dataset** for **Named Entity Recognition (NER)** to identify key-value pairs in document forms.

---

## 📂 Project Overview

- **Dataset**: [FUNSD (Form Understanding in Noisy Scanned Documents)](https://huggingface.co/datasets/nielsr/funsd-layoutlmv3)
- **Model**: [`microsoft/layoutlmv3-base`](https://huggingface.co/microsoft/layoutlmv3-base)
- **Task**: Token classification (NER) with bounding box awareness
- **Goal**: Automatically extract semantically relevant fields like `QUESTION`, `ANSWER`, `HEADER`, `OTHER` from scanned forms

---

## 🚀 Demo Example


<img width="754" height="1000" alt="OCR" src="https://github.com/user-attachments/assets/6d77457a-e723-4b03-833e-19572566b3ce" />

> *LayoutLMv3 correctly classifies text segments and aligns them with bounding boxes.*

---

````

### 2. Install dependencies

```bash
pip uninstall -y transformers huggingface_hub tokenizers
pip install --no-cache-dir transformers==4.54.1 evaluate seqeval
```

---

## 📊 Results

After fine-tuning, the model achieves strong performance on the eval set:

| Metric        | Score |
| ------------- | ----- |
| **Precision** | 86.0% |
| **Recall**    | 90.4% |
| **F1-score**  | 88.1% |
| **Accuracy**  | 83.0% |
---

## 🧠 Model Details

* **Backbone**: LayoutLMv3 (pretrained with image+text+layout)
* **Loss Function**: Cross-entropy over token-level labels
* **Input features**:

  * `image` (scanned document)
  * `tokens` (text segments)
  * `bboxes` (bounding boxes for each token)
  * `ner_tags` (IOB format labels)

---

## 📁 File Structure

```
.
├── M_FUNSD_Final.ipynb    # Main notebook
├── README.md              # Project description
```

---

## 📚 References

* **LayoutLMv3 paper**: [arXiv:2204.08387](https://arxiv.org/abs/2204.08387)
* **FUNSD dataset**: [Link](https://guillaumejaume.github.io/FUNSD/)
* **Hugging Face Model Card**: [microsoft/layoutlmv3-base](https://huggingface.co/microsoft/layoutlmv3-base)

---

## 🤝 Contributing

Feel free to open issues or pull requests. Contributions are welcome!

---
