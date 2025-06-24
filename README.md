# self-healing-sentiment-dag

A CLI-based sentiment classifier with fallback logic using a LangGraph DAG and a fine-tuned DistilBERT model. Automatically requests user clarification when prediction confidence is low.

---

##  Project Title: Self-Healing Sentiment Classifier with Confidence-Aware LangGraph DAG

This project implements a robust command-line interface (CLI) application that performs sentiment classification using a fine-tuned transformer model on the Yelp polarity dataset. The core of this system is a **LangGraph-based Directed Acyclic Graph (DAG)** that integrates self-healing mechanisms to ensure accurate and trustworthy predictions—particularly in cases where the model's confidence is low.

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
