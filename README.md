#  Movie Recommendation System

A  **Content-Based Movie Recommendation System** built with **FastAPI** backend and **Streamlit** frontend, powered by **TF-IDF** similarity and **TMDB API**.

##  Live Demo
- **Frontend:** Streamlit Web App
- **Backend API:** [https://movie-rec-466x.onrender.com](https://movie-rec-466x.onrender.com)

##  Features
-  **Search Movies** - Real-time movie search with autocomplete suggestions
-  **Content-Based Recommendations** - TF-IDF cosine similarity algorithm
-  **Genre-Based Recommendations** - Similar movies based on genre
-  **Home Feed** - Trending, Popular, Top Rated, Now Playing, Upcoming movies
-  **Movie Details** - Full movie info with poster, backdrop, overview, genres
-  **Beautiful UI** - Modern, responsive poster grid layout

##  Tech Stack

### Backend
- **FastAPI** - High-performance Python API framework
- **TMDB API** - Movie metadata and images
- **Scikit-learn** - TF-IDF Vectorizer
- **Pandas & NumPy** - Data processing
- **Uvicorn** - ASGI server

### Frontend
- **Streamlit** - Interactive web application
- **HTTPX** - Async HTTP client

### ML/Algorithm
- **TF-IDF (Term Frequency-Inverse Document Frequency)** for text vectorization
- **Cosine Similarity** for finding similar movies

##  Project Structure
```
movie-rec-main/
 main.py              # FastAPI backend server
 app.py               # Streamlit frontend app
 movies.ipynb         # Jupyter notebook for model training
 df.pkl               # Processed movie dataframe
 tfidf.pkl            # TF-IDF vectorizer
 tfidf_matrix.pkl     # Pre-computed TF-IDF matrix
 indices.pkl          # Movie title to index mapping
 movies_metadata.csv  # Raw movie dataset
 requirements.txt     # Python dependencies
 runtime.txt          # Python version for deployment
```

##  Getting Started

### Prerequisites
- Python 3.10+
- TMDB API Key (get it from [themoviedb.org](https://www.themoviedb.org/settings/api))

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/dev200413y/moveis-_recommendation.git
cd moveis-_recommendation/movie-rec-main
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Set up environment variables**
```bash
# Create .env file
echo TMDB_API_KEY=your_api_key_here > .env
```

4. **Run the FastAPI backend**
```bash
uvicorn main:app --reload --port 8000
```

5. **Run the Streamlit frontend** (in another terminal)
```bash
streamlit run app.py
```

##  API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/health` | GET | Health check |
| `/home` | GET | Home feed (trending/popular/top_rated) |
| `/tmdb/search` | GET | Search movies by keyword |
| `/movie/id/{tmdb_id}` | GET | Get movie details |
| `/recommend/tfidf` | GET | TF-IDF based recommendations |
| `/recommend/genre` | GET | Genre based recommendations |
| `/movie/search` | GET | Bundle: Details + TF-IDF + Genre recs |

##  How It Works

1. **Data Preprocessing**: Movie metadata is cleaned and processed
2. **TF-IDF Vectorization**: Text features are converted to TF-IDF vectors
3. **Similarity Calculation**: Cosine similarity finds similar movies
4. **TMDB Integration**: Real-time movie posters and details from TMDB API
5. **Hybrid Recommendations**: Combines content-based (TF-IDF) + genre-based filtering

##  Screenshots

-  Home Page with trending movies
-  Search with autocomplete suggestions
-  Movie details with recommendations

##  Author

- **GitHub:** [@dev200413y](https://github.com/dev200413y)

##  License

This project is open source and available under the MIT License.

---
 **Star this repo if you found it helpful!**
