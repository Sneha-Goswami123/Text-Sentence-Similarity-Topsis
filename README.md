# Sneha-102303723

# TOPSIS for Text Sentence Similarity Models

## 📌 Project Overview
This project applies the **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** method to select the best pre-trained model for the **Text Sentence Similarity** task.

---

## 🎯 Objective
To evaluate and rank multiple pre-trained sentence transformer models using:

1. Quality of similarity prediction  
2. Inference time  
3. Model size  

and select the most balanced model using **TOPSIS multi-criteria decision making**.

---

## 🧠 Models Evaluated

- all-MiniLM-L6-v2  
- all-mpnet-base-v2  
- paraphrase-MiniLM-L6-v2  
- distiluse-base-multilingual-cased-v1  

---

## 📊 Dataset Used

### STS Benchmark Dataset  
Source: HuggingFace – `stsb_multi_mt (English)`

- Contains sentence pairs  
- Human annotated similarity scores from **0 to 5**  
- Standard dataset used in research for semantic textual similarity

### Usage in Project
- 200 samples from test split were used  
- Model cosine similarity was scaled to 0–5  
- Compared with gold scores using MSE

---

## ⚙ Evaluation Criteria

| Criterion | Type |
|---------|------|
| Mean Squared Error (MSE) | Cost |
| Inference Time | Cost |
| Model Size | Cost |

### Weights Used
- MSE → 0.5  
- Time → 0.3  
- Size → 0.2  

---

## 🧮 Methodology

1. Load STS Benchmark dataset  
2. Load pre-trained models  
3. Generate embeddings  
4. Compute cosine similarity  
5. Scale predictions to 0–5  
6. Calculate:
   - MSE with gold scores  
   - Inference time  
   - Model size  
7. Form decision matrix  
8. Apply TOPSIS  
9. Rank models  

---

## 📈 Result

<img width="957" height="591" alt="image" src="https://github.com/user-attachments/assets/cd32c7d3-2aaa-46ca-a70f-8d4f49fcf022" />


---

## 🚀 How to Run

1. Open Google Colab  
2. Install dependencies:

```bash
pip install sentence-transformers datasets numpy pandas matplotlib scikit-learn
