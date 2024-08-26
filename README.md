# Spotify Playlist Data Extraction and Recommendation System

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [1. Spotify API Authentication](#1-spotify-api-authentication)
  - [2. Fetching Playlist Data](#2-fetching-playlist-data)
  - [3. Preprocessing Data](#3-preprocessing-data)
  - [4. Generating Recommendations](#4-generating-recommendations)
    - [Content-Based Recommendations](#content-based-recommendations)
    - [Hybrid Recommendations](#hybrid-recommendations)
- [Example](#example)
- [Contributing](#contributing)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact)

## Introduction

This project is a **Spotify Playlist Data Extraction and Recommendation System** designed to extract data from Spotify playlists and generate song recommendations based on content-based filtering and hybrid models. The system utilizes the Spotify API to gather track information, including audio features, and then applies machine learning techniques to recommend songs based on user input.

## Features

- **Data Extraction**: Extracts detailed information from Spotify playlists, including track name, artists, album, popularity, release date, and audio features.
- **Content-Based Filtering**: Recommends songs similar to a given input song based on audio features like danceability, energy, loudness, etc.
- **Hybrid Recommendation System**: Combines content-based filtering with popularity weighting to suggest songs that are both similar and popular.
- **Scalability**: Can be extended to include more advanced recommendation techniques and additional features.

## Installation

To run this project locally, follow these steps:

**Clone the repository**:
   ```bash
   git clone https://github.com/your-username/spotify-recommendation-system.git
   ```

**Set up your Spotify API credentials:**
- Create an app on the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/applications).
- Copy your `Client ID` and `Client Secret`.
- Replace the placeholders in the `CLIENT_ID` and `CLIENT_SECRET` variables in the code with your credentials.

## Usage
- **Spotify API Authentication**
Before fetching any playlist data, authenticate your application using Spotify API credentials. This is done automatically in the script, but you need to ensure that your CLIENT_ID and CLIENT_SECRET are correctly set.

- **Fetching Playlist Data**
Use the get_trending_playlist_data function to extract data from a Spotify playlist. The function returns a DataFrame with detailed track information, including audio features.

- **Preprocessing Data**
The extracted data is preprocessed using Min-Max scaling to normalize the audio features, making it suitable for recommendation algorithms.

- **Generating Recommendations**
  - **Content-Based Recommendations**
Use the content_based_recommendations function to generate song recommendations based on the similarity of audio features to a given input song.

  - **Hybrid Recommendations**
The hybrid_recommendations function combines content-based filtering with a popularity weighting to recommend songs that are both similar and have higher popularity scores.

## Example
Here is an example of how to use the system:
```python
# Import the required modules
from your_script import get_trending_playlist_data, hybrid_recommendations

# Fetch data from a Spotify playlist
playlist_id = '37i9dQZF1DX76Wlfdnj7AP'
music_df = get_trending_playlist_data(playlist_id, access_token)

# Generate hybrid recommendations for a specific song
input_song_name = "Not Like Us"
recommendations = hybrid_recommendations(input_song_name, num_recommendations=5)

# Display the recommended songs
print(recommendations)
```
This will output a DataFrame containing the recommended songs with details such as track name, artists, album name, release date, and popularity.

## Contributing

Contributions are welcome! If you have any ideas, suggestions, or bug reports, feel free to open an issue or submit a pull request.

To contribute:
- Fork the repository.
- Create a new branch for your feature or bugfix (git checkout -b feature-name).
- Commit your changes (git commit -am 'Add new feature').
- Push to the branch (git push origin feature-name).
- Open a pull request.
Please ensure your code adheres to the existing code style and includes appropriate documentation.

## Acknowledgements

This project relies on several open-source libraries and APIs:
- [Spotipy](https://spotipy.readthedocs.io/) for Spotify API interactions.
- [Scikit-learn](https://scikit-learn.org/) for machine learning functionalities.
- Pandas for data manipulation.
- [Spotify API](https://developer.spotify.com/documentation/web-api/) for accessing playlist data.

