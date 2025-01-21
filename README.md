# Spotify Data Analysis

This project analyzes different features of popular songs and artists, and compares popularity on different platforms including Tik Tok and YouTube. Using Python libraries like `pandas`, `matplotlib`, and `seaborn`, the analysis explores correlations, trends, and patterns in the dataset.

## Features
- **Correlation Analysis**: Examine relationships between TikTok views, likes, posts, and platform metrics such as Spotify streams and YouTube views.
- **Visualization**: Generate insightful plots, including scatter plots, bar charts, and pie charts.
- **Top Track Analysis**: Identify and visualize the top tracks and artists by Spotify streams.
- **Comparative Analysis**: Compare Spotify popularity with airplay spins using scatter plots.
- **Tag Frequency Analysis**: Analyze and visualize the frequency of tags associated with tracks using histograms and word clouds.

## Dataset
The dataset contains information about:
- Spotify Streams
- TikTok Metrics (Views, Likes, Posts)
- YouTube Views
- Airplay Spins
- Song Release Dates

Ensure the dataset is cleaned and preprocessed before running the scripts.

## Requirements
- `pandas`
- `matplotlib`
- `seaborn`
- `hvplot`
- `requests`
- `dotenv`
- `pickle`
- `wordcloud`

## Notebook: musicPy.ipynb

The `musicPy.ipynb` notebook performs the following steps:

### Data Wrangling
1. **Imports necessary modules**: `pandas`, `hvplot.pandas`, `matplotlib`, `pprint`, `kagglehub`, `os`, `requests`, `pickle`, `dotenv`.
2. **Downloads and loads the Spotify dataset**: Uses `kagglehub` to download the dataset, cleans up column names, and saves the cleaned DataFrame to a pickle file.
3. **Authenticates with the Spotify API and updates the DataFrame with Spotify IDs**: Retrieves Spotify IDs for tracks and updates the DataFrame.
4. **Retrieves Last.fm tags for Spotify tracks**: Queries the Last.fm API to get the top tags for each track and updates the DataFrame.
5. **Tries to retrieve Last.fm tags for tracks that are missing them using the Spotify API**: Uses the Spotify API to get track information and queries the Last.fm API to get the top tags.

### Data Cleaning
1. Drops rows with missing `spotify_id`.
2. Converts specified numerical columns to numeric types by removing commas, replacing 'nan' strings with NaN values, and converting to numeric.
3. Creates a new DataFrame for rows with missing `lastfm_tags`.
4. Removes tracks with no `spotify_id`.
5. Removes tracks with no `lastfm_tags`.
6. Retains only the first 10 elements of the `lastfm_tags` list.
7. Resets the index and renames the index column to `original_rank`.
8. Displays the data types of the columns in `spotify_df`.

### Analysis
1. **Plots a histogram of the top 100 tags**: Uses `matplotlib` to create a bar plot of the top 100 tags by frequency.
2. **Plots weighted tag frequency histograms**: Defines a function `plot_weighted_tag_frequency` to plot histograms of tag frequency weighted by the rank of its representatives.
3. **Generates word clouds for tag frequency and weighted frequency**: Defines a function `plot_word_clouds` to create word clouds for tag frequency and weighted frequency.
4. **Compares explicit and clean versions of tracks**: Filters the DataFrame to include tracks with both explicit and clean versions, and plots comparisons for various metrics.

## Usage
To run the analysis, ensure you have the required libraries installed and the dataset downloaded. Open the `musicPy.ipynb` notebook and execute the cells sequentially.
