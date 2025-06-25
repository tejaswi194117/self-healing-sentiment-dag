"""# self-healing-sentiment-dag

A CLI-based sentiment classifier with fallback logic using a LangGraph DAG and a fine-tuned DistilBERT model. Automatically requests user clarification when prediction confidence is low.

---

##  Project Title: Self-Healing Sentiment Classifier with Confidence-Aware LangGraph DAG

This project implements a robust command-line interface (CLI) application that performs sentiment classification using a fine-tuned transformer model on the Yelp polarity dataset. The core of this system is a **LangGraph-based Directed Acyclic Graph (DAG)** that integrates self-healing mechanisms to ensure accurate and trustworthy predictions—particularly in cases where the model's confidence is low.

---

##  Demo Video

Watch the full walkthrough of the CLI-based self-healing sentiment classifier in action:

🔗 [Watch on Loom](https://www.loom.com/share/2cf567bde2d646b59296d515891219e3?sid=8cd8f06a-9583-482c-ae9e-efe10f1d6e0f)



---

##  Overview

- **Dataset Used**: Yelp Polarity (binary sentiment: positive/negative)
- **Model**: DistilBERT (fine-tuned using Hugging Face + LoRA/full finetuning)
- **Framework**: LangGraph for decision DAG
- **Fallback**: Triggered if confidence < 70%
- **Interface**: Fully interactive CLI with logging and correction capabilities

---

##  Features

- Fine-tuned transformer for sentiment analysis
- LangGraph DAG with:
  - `InferenceNode`: Predicts sentiment
  - `ConfidenceCheckNode`: Checks prediction confidence
  - `FallbackNode`: Requests clarification if confidence is low
- Self-healing logic with user input recovery
- CLI-based interaction loop
- Structured logging of all predictions, confidence scores, and corrections

---

##  How It Works

### 1. Prediction Phase
User inputs a sentence. The model predicts its sentiment and provides a confidence score.

### 2. Confidence Check
If confidence < 70%, a fallback is triggered.

### 3. Fallback and Clarification
The system prompts the user to clarify or confirm their intent. The final label is then logged.

### Example CLI Output:
Input: The movie was painfully slow and boring.

[InferenceNode] Predicted label: Positive | Confidence: 54%

[ConfidenceCheckNode] Confidence too low. Triggering fallback...

[FallbackNode] Could you clarify your intent? Was this a negative review?

User: Yes, it was definitely negative.

Final Label: Negative (Corrected via user clarification)

---

##  Setup Instructions

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/self-healing-sentiment-dag.git
cd self-healing-sentiment-dag"""
