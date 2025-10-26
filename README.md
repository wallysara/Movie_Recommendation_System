# Item-Based Movie Recommendation System (KNN with Cosine Similarity)

This project implements a **personalized movie recommender system** using the **MovieLens 100K** dataset and an **item-based collaborative filtering** approach powered by **cosine similarity**.  
The system predicts user ratings and generates top-N movie recommendations based on item-item similarity.

---

## 🧠 Overview

- Built an **item-based KNN recommender** that uses cosine similarity between movies.  
- Predicted ratings using **weighted averages** of top-50 most similar items.  
- Included robust fallback strategies for unseen users or items.  
- Evaluated performance using **Root Mean Squared Error (RMSE)** for prediction accuracy.

---

## ⚙️ Techniques Used

| Step | Method | Description |
|------|---------|-------------|
| Data Preparation | MovieLens 100K | Loaded user, movie, and rating data |
| Similarity Computation | Cosine Similarity | Computed item-item similarity matrix |
| Rating Prediction | Weighted KNN | Predicted ratings using top-50 similar items |
| Evaluation | RMSE | Measured overall accuracy |

---

## 🧩 Implementation Steps

1. **Load Dataset**
   - Files: `u.data`, `u.item`, `u.user`  
   - Parsed using `pandas` with appropriate encoding and delimiters.

2. **Train-Test Split**
   - Used an 80/20 split for training and testing with reproducible random state.

3. **Matrix Construction**
   - Created user-item interaction matrix for training (`pivot table` with users × movies).

4. **Item Similarity**
   - Calculated cosine similarity between items to measure similarity in user rating patterns.

5. **Prediction**
   - Implemented a safe prediction function handling missing users or items gracefully.
   - Final predicted rating computed as weighted average of neighbors.

6. **Evaluation**
   - Achieved **RMSE ≈ 0.98** on the MovieLens 100K test set.

---

## 🧪 Example Output

```python
Top 10 Recommendations for User 1:
[(242, 4.82), (174, 4.65), (50, 4.58), (98, 4.51), (181, 4.47), ...]
```
RMSE: 0.98

🧰 Requirements
```pip install pandas numpy scikit-learn```

📚 References:

MovieLens 100K Dataset

Collaborative Filtering Concepts (Koren et al., 2009)
