# Simple-Recommendation-System

# Overview
### Movie Recommendation System
the porpuse of this project is to build a content-based recommender using pure numpy and pandas
### Grocery Recommendation System
A market basket analysis system that suggests frequently purchased grocery items together using a transaction matrix (also known as one-hot encoded) and using two main metrics


# Key Features
### Movie Recommendation System:
  - dual search mode:
    - Search by movie title (finds similar movies)
    - Search by preferences (genre/director/actor)
  -  IMDB rating and meta score filtering
  -  Cosine Similarity:
    -  measures the similarity of the recommended movie to input movie or features
    -  Ranks recommendations by match score

### Grocery Recommendation System:
  - uses a transaction matrix for recommendation
  - calculates how aften are items purchased together
  - uses lift or confidence metrics to avoid random correlations
  - Works with single or multiple input items


# How It Workds?
Core Concept: Feature Matrix Representation
Both recommendation systems employ a binary matrix representation approach where:
  - Rows represent individual items (movies or grocery products)
  - Columns represent features (movie metadata or purchase indicators)
  - Values are binary encoded (1 = presence of feature, 0 = absence)
Search Mechanism:

For movie recommendations, the system:

  - Creates a comparison vector from user input
  - Computes cosine similarity between this vector and all movies
```python
    dot_product = features.dot(comparison_vec)
    norm_features = np.linalg.norm(features)
    norm_comparison = np.linalg.norm(comparison_vec)
    similarity_score = dot_product / (norm_features * norm_comparison)
```
For grocery recommendations:

  - Builds a transaction matrix showing customer purchases
  - Calculates item co-occurrence frequencies
  - Applies lift metric to find meaningful patterns
```python
occurrence = np.dot(transaction_matrix.T, transaction_matrix)
```


# setup
## 1- clone repositore
```bash
git clone https://github.com/Lord-Mahdi1383/Simple-Recommendation-System.git
cd Simple-Recommendation-System
```

## 2- install requirements
```bash
pip install -r Requirements.txt
```
