# Hybrid Movie Recommender System
![Status](https://img.shields.io/badge/Status-Completed-success)
![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Recommender%20Systems-brightgreen)
![TMDB](https://img.shields.io/badge/Data-TMDB%20API-orange)
![MovieLens](https://img.shields.io/badge/Data-MovieLens-red)
![License](https://img.shields.io/badge/License-Academic-lightgrey)

---

## Project Overview

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/79d297f7-a546-4b5d-95f6-a0fda7d1db9c" />

This project implements a **Movie Recommender System** using **Content-Based Filtering**, **Collaborative Filtering**, and a **Hybrid Recommendation approach**. The system focuses on **high-rated movies released between 2015 and 2025** and leverages both movie metadata and user–movie interaction data to generate accurate and personalized recommendations.

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/98636fca-5318-45fe-b0a5-4f98a954e634" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/89eb8b8c-4421-4b67-8ad0-20b3689479b9" />

---

## Objectives

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0073a42f-a78d-4087-a35f-a0ff7b5de7a2" />

- Build a **content-based recommender** using movie metadata  
- Build a **collaborative filtering model** using user ratings  
- Combine both approaches into a **hybrid recommender system**  
- Evaluate recommendation quality using ranking-based metrics  

---

## Dataset Description

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0b635435-efb6-4a6e-8b62-03b3975cf689" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/2f691162-cf01-4951-8923-822edd82dc1e" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/5b425bb0-a0fc-47dd-a35a-0e06b43981f6" />



### Data Sources
- **TMDB API** – Movie metadata (titles, overview, genres, cast, keywords)
- **MovieLens Dataset** – User–movie rating interactions
- **IMDb (Scraping)** – Scraping pipeline implemented (reviews optional)

### Filtering Criteria
- Release years: **2015–2025**
- Minimum rating: **6.0**
- Minimum vote count: **50**

### Generated Files
| File Name | Description |
|----------|------------|
| `movies_2015_2025.csv` | Raw movie metadata from TMDB |
| `movies_tmdb_enriched.csv` | Enriched metadata (genres, cast, keywords) |
| `ratings_for_cf.csv` | User–movie ratings for collaborative filtering |
| `movies_master.csv` | Final dataset with combined textual features |

---

## Methodology

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/45ee79c9-8aee-4430-9c32-c555466b0bd5" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/06e7d8dc-725e-4515-9450-93c3ed7e54bd" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/f2b517c2-a261-4125-9687-5fb4b4f6df57" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/3ec4d4dd-64ec-4eef-b14a-512dfe507e8c" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/a0f31e71-846b-4e07-8c22-0fcd12eeb0c9" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c0541a37-0a3a-46c3-83ba-3c1f8823b9b4" />

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/aeb13e59-33c1-47a6-a7c5-266ebd8ffc81" />


### 1. Content-Based Filtering
- Feature engineering using movie **overview, genres, keywords, cast**
- Unified text feature: `combined_text`
- **TF-IDF vectorization**
- **Cosine similarity** for movie-to-movie recommendations

### 2. Collaborative Filtering
- User–item interaction matrix from MovieLens
- **Matrix factorization (SVD)** using Surprise library
- Personalized rating prediction

### 3. Hybrid Recommendation
- Weighted fusion of content-based and collaborative scores  
- Fusion parameter **α** controls contribution of each model  

```

Final Score = α × Content Score + (1 − α) × Collaborative Score

```

---

## Evaluation Metrics

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/431fd9a5-71ed-4ebc-84dc-ea2c9617fd0a" />

The system was evaluated using ranking-based and prediction metrics:

- **HitRate@5**
- **HitRate@10**
- **MRR@5**
- **RMSE** (for collaborative filtering)

### Performance Highlights

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/4f9b0584-6e10-4240-a94c-a0133a83b848" />

- **HitRate@10 ≈ 0.95**
- **HitRate@5 ≈ 0.92**
- **MRR@5 ≈ 0.90**
- Best performance achieved at **α ≈ 0.7–0.9**
- Hybrid model significantly outperformed collaborative-only (Surprise) baseline

---

## Tools and Technologies

- **Programming Language:** Python  
- **Libraries:** Pandas, NumPy, Scikit-learn, Surprise  
- **Data Sources:** TMDB API, MovieLens  
- **Web Scraping:** BeautifulSoup  
- **Visualization:** Matplotlib  
- **Environment:** Kaggle, Jupyter Notebook  
- **Version Control:** Git, GitHub  

---

## Ethical Considerations

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/0453caa2-0872-442d-b940-73f55f91276c" />

- Only **public and academic datasets** were used  
- Ethical and rate-limited web scraping  
- No personal or sensitive user data collected  
- Project developed strictly for **educational purposes**

---

## Future Work

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/362eb3b6-fbda-4835-a488-cf597d058a2c" />

- Deep learning–based recommenders (Neural CF, embeddings)
- Real-time user feedback integration
- Web or mobile application deployment
- Larger and multilingual datasets

---

## Authors

- **Awais Asghar**
- **Ahmad Hussain**
- **M. Hammad Sarwar**

---

## ⭐ Acknowledgments

- TMDB for providing the movie metadata API  
- GroupLens Research for the MovieLens dataset  

---

⭐ If you find this project useful, feel free to the repository ⭐

<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/8c53383a-1aa5-4332-ab7c-4496510edbf0" />
