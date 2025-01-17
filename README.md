
# Spotify Data Analysis

This project analyzes different features of popular songs and artists, and compares popularity on different platforms including Tik Tok and YouTube. Using Python libraries like `pandas`, `matplotlib`, and `seaborn`, the analysis explores correlations, trends, and patterns in the dataset.

## Features
- **Correlation Analysis**: Examine relationships between TikTok views, likes, posts, and platform metrics such as Spotify streams and YouTube views.
- **Visualization**: Generate insightful plots, including scatter plots, bar charts and pie charts.
- **Top Track Analysis**: Identify and visualize the top tracks and artists by Spotify streams.
- **Comparative Analysis**: Compare Spotify popularity with airplay spins using scatter plots.

## Dataset
The dataset contains information about:
- Spotify Streams
- TikTok Metrics (Views, Likes, Posts)
- YouTube Views
- Airplay Spins
- Song Release Dates

Ensure the dataset is cleaned and preprocessed before running the scripts.

## Requirements
Install the following Python libraries:
- pandas
- matplotlib
- seaborn

```bash
pip install pandas matplotlib seaborn
```

## Usage

### 1. Load the Dataset
Go to https://www.kaggle.com/datasets/nelgiriyewithana/most-streamed-spotify-songs-2024 to download the file
```python
file_path = 'your_dataset_path_here.csv'
data = pd.read_csv(file_path)
```

### 2. Generate Visualizations
Run the Python script to produce:
- Correlation matrices
- Scatter plots (e.g., TikTok Views vs Spotify Streams)
- Histograms (e.g., song release year distribution)
- Top 10 tracks by Spotify streams

### 3. Compare Metrics
Add columns like `spotify_popularity` and `airplay_spins` to analyze their relationships visually.

### Example: Top 10 Tracks by Spotify Streams
```python
plt.barh(top_10_tracks['track'] + ' - ' + top_10_tracks['artist'], top_10_tracks['spotify_streams'])
plt.xlabel('Spotify Streams')
plt.title('Top 10 Tracks by Spotify Streams')
plt.show()
```

### Example: Spotify Popularity vs Airplay Spins
```python
plt.scatter(clean_df['spotify_popularity'], clean_df['airplay_spins'])
plt.xlabel('Spotify Popularity')
plt.ylabel('Airplay Spins')
plt.title('Spotify Popularity vs Airplay Spins')
plt.show()
```

## Contributions
Contributions are welcome! Feel free to fork the repository, open issues, or submit pull requests.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

