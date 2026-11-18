# Movie Recommender CF vs MF

Rating prediction and movie recommendation using **User-Based Collaborative Filtering**,
**Item-Based Collaborative Filtering**, and **Matrix Factorization** on the MovieLens 100K dataset.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shortahairlover/MovieRecommender-CFvsMF/blob/main/tugas_rekomendasi.ipynb)

Group assignment for the Recommender Systems course, Informatics Undergraduate Program, School of Computing, Telkom University.

## Group 5

| Name | Student ID |
|---|---|
| Naufal Rafif Hidayat | 103012300403 |
| Muhammad Alivio Putra | 103012300098 |
| Akbar Jundi Pradita | 103012300081 |
| Raffa Anung El Haqqi | 103012300163 |
| Naufal Thafhan | 103012300284 |

## Dataset

[MovieLens 100K](https://grouplens.org/datasets/movielens/100k/) by GroupLens Research:
100,000 ratings (1 to 5 scale) from 943 users on 1,682 movies.
The dataset is downloaded automatically when the notebook runs.

## Methods

| Method | Details |
|---|---|
| User-Based CF | Pearson correlation (cosine on mean-centered data), k = 30 neighbors |
| Item-Based CF | Adjusted cosine similarity, k = 30 neighbor items |
| Matrix Factorization | Stochastic gradient descent with biases, K = 20 latent factors |

Evaluation metrics: MAE, MSE, RMSE, NMSE, and NDCG@10.

## Results

5-fold cross-validation (mean):

| Method | MAE | RMSE | NMSE | NDCG@10 |
|---|---|---|---|---|
| User-Based CF | 0.7310 | 0.9371 | 0.2196 | 0.9162 |
| Item-Based CF | 0.7294 | 0.9340 | 0.2181 | 0.9132 |
| Matrix Factorization | **0.7259** | **0.9186** | **0.2110** | **0.9187** |

Matrix Factorization achieves the best score on every metric.
The full discussion is available in the [report](report/Laporan%20Sistem%20Rekomendasi.pdf) (in Indonesian).

## Repository Structure

```
├── tugas_rekomendasi.ipynb   Main notebook (code, results, and analysis)
├── report/                   PDF report
├── assets/                   Charts, evaluation results (CSV), diagrams, code images, and formulas
└── requirements.txt          Python dependencies
```

## How to Run

**Google Colab:** click the "Open in Colab" button above, then select Runtime > Run all.

**Local:**

```bash
pip install -r requirements.txt
jupyter notebook tugas_rekomendasi.ipynb
```

Running the whole notebook takes about 9 minutes.
