# Spotify_Cluster_Analysis
A k-means analysis of how Spotify groups songs.

## Dataset

This project uses the Kaggle dataset `SpotifyFeatures.csv`.

This can be found at https://www.kaggle.com/datasets/zaheenhamidani/ultimate-spotify-tracks-db?resource=download 

## How to Run: 

1. Download the dataset from Kaggle.
2. Upload `SpotifyFeatures.csv` into the Colab session when prompted.
3. Run the cells from top to bottom.

## Introduction

Spotify has more than 100 million songs by 8.4 million artists, and 60,000 new songs are added per day. To help users discover new music, it has more than 1,500 AI-generated playlists, with names like Bossa Pop, Get Turnt, New Noise, You & Me, and Terra Incognita. In my experience, the songs in these playlists work well together and create different vibes for listeners to enjoy based on their current mood. I wondered how Spotify makes these playlists: what similarities do the songs have, and which features are the most important factors that group certain songs together?

I was overjoyed to find a Kaggle dataset on 232,725 Spotify songs with 18 features. These features gave insight on what makes certain songs go together. The most consequential are as follows:

-- Genre

-- Popularity

-- Acousticness

-- Danceability

-- Energy

-- Instrumentalness

-- Key

-- Liveness

-- Loudness

-- Mode

-- Speechiness

-- Tempo

-- Time Signature

## Why K-means?

Since the goal was to group songs into playlists based on shared characteristics, I thought an unsupervised grouping algorithm, K-means, would be best. Unlike correlation and classification problems that use supervised learning, grouping songs into playlists has no one "right" answer.

## Overall Program

-- Separated categorical and numerical features

-- Performed binary encoding, circular encoding with sine and cosine, and one-hot encoding on the categorical features

-- Used a StandardScaler() object to scale the numerical features

-- Used the K-means elbow method to select the appropriate K (9)

-- Ran K-means on the data to group the songs into 9 clusters

-- Performed principal component analysis to display the nine-dimensional data on an x-y coordinate plane

-- For each cluster, found the 20 data points closest to the centroids to find the most quintessential songs of the cluster

-- Found these songs on Spotify and manually built nine playlists

## Which Features Mattered Most?

-- Maximum z-score was assessed by evaluating each feature's z-score in each cluster and selecting the z-score farthest from the mean.

-- Speechiness, with a maximum z-score of 4, had the most pronounced impact on group formation far from the overall mean.

-- Instrumentalness and liveness, with a maximum z-score of 2.5, had a high impact.

-- Loudness, with a maximum z-score of 2, had a significant impact.

## Average versus Niche

-- Clusters 6 and 8 most matched the overall song profile, with z-score ranges of 1.5. With a combined 55 percent of all songs, they indicated the kinds of songs most common on Spotify. The most common genres in these clusters were hip hop, rap, pop, dance, folk, indie, and soul. Clusters 6 and 8 had the greatest popularity, with z-scores of 1 and 0.5. The features that most united Clusters 6 and 8, as measured by z-score differences, were lower-than-average instrumentalness, tempo, liveness, and speechiness.

-- Clusters 4 and 0 were the most niche, with z-score ranges of 6.5 and 5.5. Combined, they comprised 13 percent of all songs. The most common genres in these clusters were comedy, soundtrack, and classical. The features that most united Clusters 4 and 0, as measured by z-score differences, were lower-than average tempo, popularity, and valence and higher-than-average acousticness.

## Counterintuitive Genre Pairings

-- Cluster 2: world, blues, ska, and electronic might seem completely different on paper, but they had similar liveness.

-- Cluster 3: ska, alternative, children's, anime, rock, country, and electronic are all over the map culturally, but they had similar tempo.

-- Cluster 7: electronic and jazz seem different, but they had a similar minor mode and instrumentalness.

By using algorithms to quantitatively assess songs, Spotify gives listeners an experience deeper than traditional ideas of genre, helping them enjoy music that goes well together and find something new.

## See the project file for operational information and insights from the data!
