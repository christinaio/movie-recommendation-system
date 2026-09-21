# Movie Recommendation System with Python and Prolog

A hybrid movie recommendation system combining Python with Prolog-based symbolic reasoning to generate personalized movie recommendations.

## Overview

This project explores a hybrid recommendation approach that combines content-based movie similarity with user rating information.

Movie characteristics are represented as Prolog facts, while similarity rules are defined in a Prolog knowledge base. Python communicates with Prolog through PySwip to retrieve similar movies and uses user ratings to assign preference scores and generate personalized recommendations.

The recommender is evaluated using Precision, Recall, and F1-score.

## How It Works

The recommendation pipeline consists of three main stages:

1. **Knowledge Base Construction**  
   Movie genres are converted into Prolog facts and stored in a knowledge base.

2. **Content-Based Recommendation**  
   Prolog rules identify similar movies based on shared genres.

3. **Personalized Recommendation**  
   User ratings are converted into preference weights and propagated to similar movies to generate recommendation scores.

## Technologies

- Python
- Pandas
- NumPy
- SWI-Prolog
- PySwip
- Scikit-learn
- tqdm
- Jupyter Notebook

## Project Structure

```text
movie-recommendation-system/
│
├── data/
│   ├── movies_metadata.csv
│   ├── train_ratings.csv
│   └── test_ratings.csv
│
├── db.pl
├── movie_recommendation_system.ipynb
└── README.md
```

## Evaluation

The recommender was evaluated using two different training sample sizes. Each experiment was repeated 10 times.

| Training Ratings | Precision | Recall | F1-score |
|-----------------:|----------:|-------:|---------:|
| 10 | 0.517 | 0.742 | 0.594 |
| 30 | 0.513 | 0.936 | 0.662 |

Increasing the number of training ratings from 10 to 30 substantially increased Recall and improved the F1-score, while Precision remained relatively stable.

The results suggest that additional user-rating information helps the recommender identify a larger proportion of movies associated with positive user preferences. However, the lower Precision indicates that the system also generates false-positive recommendations.

## Installation

Python dependencies can be installed with:

```bash
pip install pandas numpy pyswip scikit-learn tqdm jupyter
```

SWI-Prolog must also be installed separately for PySwip to communicate with the Prolog knowledge base.

On macOS with Homebrew:

```bash
brew install swi-prolog
```

## Running the Project

Clone the repository, install the required dependencies, and open:

```text
movie_recommendation_system.ipynb
```

Run the notebook from top to bottom to construct the Prolog knowledge base, generate recommendations, and reproduce the evaluation.

## Conclusion

This project demonstrates how symbolic reasoning can be combined with user preference data to build an interpretable recommendation system.

The Prolog component provides explicit rules for movie similarity, while Python handles data processing, recommendation scoring, and performance evaluation. Future improvements could incorporate additional movie features and more advanced recommendation techniques to improve recommendation precision.
