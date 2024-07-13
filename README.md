# Spotify-Recommendation-System

##	Dataset Sources and Preprocessing
Our dataset combines a Kaggle dataset with the AIcrowd Million Playlist Dataset (MPD)1, sourced from Spotify's more than 4 billion public playlists. The MPD comprises 1 million playlists with over 2 million unique tracks by nearly 300,000 artists, making it the largest publicly available dataset of music playlists globally. The playlists were created by US Spotify users from January 2010 to November 2017.

We referenced the format and code from the Kaggle notebook titled "Music Recommendation System using Spotify Dataset”2. We expanded the dataset from 170,653 rows to 332,594 rows using the MPD set as supplement. As MPD was playlist data, a lot of the tracks were used multiple times. To 

To fill gaps in the MPD, we supplemented missing columns using the Spotify API. Client credentials were created from the Spotify developer dashboard, using client credentials flow only the client_id and client_secret is needed. We retrieved various attributes such as release dates and popularity scores for tracks, as well as popularity and genre for artists. We also obtained several audio features like danceability, energy, and tempo.  Specific API calls and variables used are listed below:
•	tracks: track_uri, release_date, track_popularity
•	artists: artist_uri, artist_popularity, artist_genre
•	audio_features: danceability, energy, key, loudness, mode, speechiness, acousticness, instrumentalness, liveness, valence, tempo, id, duration_ms, explicit
Some of the challenges in this stage were API rate limits, unclear column names, and Spotify authentication flows. Spotify's API rate limit is calculated based on the number of calls that your app makes to Spotify in a rolling 30 second window. We ran into Spotify API rate limits multiple times and were not able to obtain the full data in the MPD due to this as we did not have enough time. Only roughly a third of the MPD dataset is used. As data returned by the API were without column names, we had to manually check columns which was mildly annoying. Spotify API credential flows were quite confusing, as there is authentication code flow, client credentials flow, and Spotify OAuth. Client credentials flow was utilized for its simplicity.
