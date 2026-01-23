# Comparative Analysis of Pre-trained Models for Text Classification using TOPSIS
## UCS654 Assignment 5
### Name: Khushveer Kaur  
### Roll Number: 102303327  

---

## 1. Objective

The objective of this assignment is to identify the best pre-trained text classification model using a multi-criteria decision-making approach called **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)**.

The comparison is performed **domain-wise** to analyze how different models behave across different types of text data.

---

## 2. Task Description

The task involves:
- Selecting multiple pre-trained models
- Evaluating them on different text domains
- Ranking them using TOPSIS
- Identifying the best-performing model for each domain

---

## 3. Text Domains Considered

The evaluation is carried out separately for the following domains:

- Politics
- Sports
- Medicine

Each domain is treated as an independent case study.

---

## 4. Dataset Source

Datasets are sourced from **HuggingFace**, which provides publicly available datasets suitable for NLP tasks.

Examples:
- News-based datasets for Politics and Sports
- Medical text datasets for the Medicine domain

The dataset loading logic is implemented in: `code/load_dataset.py`


---

## 5. Pre-trained Models Used

The following transformer-based pre-trained models are used for comparison:

- BERT
- RoBERTa
- DistilBERT
- ALBERT

Each model is evaluated independently for every domain.

---

## 6. Evaluation Parameters (Criteria)

For each model, the following parameters are considered:

- P1: Accuracy (Maximize)
- P2: Precision (Maximize)
- P3: Recall (Maximize)
- P4: F1-score (Maximize)
- P5: Inference Time (Minimize)
- P6: Model Size (Minimize)

These parameters form the decision matrix for the TOPSIS method.

---

## 7. Methodology

1. Perform text classification for each domain using all selected models.
2. Compute evaluation metrics for each model.
3. Construct a decision matrix using the metrics.
4. Normalize the decision matrix.
5. Apply TOPSIS to calculate the closeness score.
6. Rank the models based on TOPSIS scores.
7. Identify the best model (Rank = 1) for each domain.

The implementation is done in: `code/classification_domainwise.py`
                               `code/topsis.py`

---

## 8. Results

The results are stored in CSV format under the `results/` directory.

### Files Generated:
- politics_metrics.csv
- politics_topsis.csv
- sports_metrics.csv
- sports_topsis.csv
- medicine_metrics.csv
- medicine_topsis.csv

Each TOPSIS file contains:
- Model-wise TOPSIS scores
- Final ranking

---

## 9. Final Summary of Results

| Text Domain | Best Model |
|------------|------------|
| Politics   | Model with Rank 1 in politics_topsis.csv |
| Sports     | Model with Rank 1 in sports_topsis.csv |
| Medicine   | Model with Rank 1 in medicine_topsis.csv |

This demonstrates that **no single model performs best across all domains**, highlighting the importance of domain-specific evaluation.

---

## 10. How to Run the Code

### Step 1: Install Dependencies
`pip install -r requirements.txt`

### Step 2: Run Classification and Evaluation
`python code/classification_domainwise.py`

### Step 3: Apply TOPSIS
`python code/topsis.py`

---

## 11. Conclusion

This assignment successfully applies the TOPSIS decision-making technique to evaluate pre-trained text classification models. The domain-wise analysis shows that model performance varies significantly depending on the nature of the text data.

TOPSIS proves to be an effective and systematic approach for ranking models based on multiple evaluation criteria.

---






