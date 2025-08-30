# Movie Recommender System – Genre, Age, and Theme-Based Recommendations

A personalized movie recommendation system that suggests movies based on **genre, viewer age, and story/theme similarity**. It combines clustering techniques with content-based similarity to deliver more accurate recommendations.

## Features & Methodology

- **Data Preprocessing**
  - `OneHotEncoder (OHE)` to encode movie genres.
  - `StandardScaler` to normalize user ages.
  
- **Clustering**
  - `KMeans` clustering on combined genre + age features.
  - **Optimal K = 5**, `n_init=50` for stability and robust clustering.

- **Recommendation Function**
  - Recommends movies with at least **2 overlapping genres**.
  - Weighted similarity: **80% genre similarity**, **20% age similarity**.
  - Supports **keyword-based searches** for better story/theme matching.

- **Performance**
  - ~**80% correct recommendations** on the current medium-sized dataset.

## Future Improvements

- Expand dataset with more movies and plot summaries.
- Use **NLP embeddings (BERT)** for semantic plot similarity.
- Combine **collaborative filtering** with content-based filtering.
- Implement **dynamic weighting** to balance genre, age, and plot similarity.
- Aim for **90%+ recommendation accuracy** with enhanced data and algorithms.

## Technologies Used

- Python, Pandas, NumPy
- Scikit-learn (`OneHotEncoder`, `StandardScaler`, `KMeans`, `cosine_similarity`)


## Example Usage

```python
recommendations = recommend_movie("Toy Story (1995)", MBC, MBC_F, top_n=5)
print(recommendations)
# Output: ["Bug's Life, A (1998)", "Toy Story 2 (1999)", "Chicken Run (2000)", ...]
