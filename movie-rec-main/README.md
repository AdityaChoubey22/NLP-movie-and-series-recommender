# Movie Recommender 🎬

An AI-powered movie recommendation system featuring a **FastAPI** backend and a **Streamlit** frontend. The app uses TMDB (The Movie Database) API for movie metadata and a custom TF-IDF model for content-based recommendations.

## Features
- **Modern UI**: A vibrant, flowery design built with Streamlit.
- **AI Recommendations**: Uses TF-IDF cosine similarity to suggest movies based on content.
- **Live Search**: Autocomplete and suggestions powered by TMDB.
- **Detailed Info**: View movie posters, overviews, genres, and release dates.
- **Genre discovery**: Explore more movies within the same genre.

## Tech Stack
- **Backend**: FastAPI
- **Frontend**: Streamlit
- **Data Science**: Scikit-learn, Pandas, NumPy
- **API**: TMDB API

## Setup Instructions

### 1. Prerequisites
- Python 3.10+
- A TMDB API Key. You can get one for free at [themoviedb.org](https://www.themoviedb.org/documentation/api).

### 2. Environment Configuration
Create a `.env` file in the root directory and add your TMDB API Key:
```env
TMDB_API_KEY=your_api_key_here
```

### 3. Installation
It's recommended to use a virtual environment:
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment (Windows)
.\venv\Scripts\activate

# Activate virtual environment (Linux/Mac)
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 4. Running the Application

You need to run **two** services: the backend and the frontend.

#### Start the FastAPI Backend
```bash
uvicorn main:app --reload
```
The API will be available at `http://localhost:8000`. You can check the health at `http://localhost:8000/health`.

#### Start the Streamlit Frontend
In a new terminal (with the virtual environment activated):
```bash
streamlit run app.py
```
The web app will open in your browser at `http://localhost:8501`.

## Troubleshooting
- **Connection Timeout**: If the app fails to fetch movie data, ensure your internet connection is stable. The app is pre-configured to use `api.tmdb.org` for better reliability in some regions.
- **Missing Data**: Ensure the `.pkl` files (df, tfidf, etc.) are present in the root directory. These are required for the AI recommendation features.

## License
MIT
