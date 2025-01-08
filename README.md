Here’s a **README.md** file for your Spotify Playlist project:

---

# Spotify Billboard Playlist Creator

This Python project creates a Spotify playlist of the **Billboard Hot 100** songs from a specified date. By scraping Billboard's website for song data and utilizing the Spotify API, the script generates a private playlist containing the songs that match the specified date.

---

## Features
- Scrapes **Billboard Hot 100** songs for a specific date.
- Searches Spotify for matching songs using the song titles.
- Creates a private playlist in your Spotify account with the found tracks.
- Securely handles API credentials with environment variables.

---

## Prerequisites

### 1. **Spotify Developer Account**  
To use the Spotify API, you need to:
- Register a Spotify Developer Account at [developer.spotify.com](https://developer.spotify.com/).
- Create an app in the **Dashboard** to get your `CLIENT_ID` and `CLIENT_SECRET`.

### 2. **Python and Libraries**  
Ensure you have Python 3.7 or later installed. Install the required libraries using:
```bash
pip install spotipy requests beautifulsoup4 python-dotenv
```

---

## Setup Instructions

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/spotify-billboard-playlist.git
   cd spotify-billboard-playlist
   ```

2. Create a `.env` file to store your Spotify credentials securely:
   ```
   CLIENT_ID=your_spotify_client_id
   CLIENT_SECRET=your_spotify_client_secret
   ```
   Replace `your_spotify_client_id` and `your_spotify_client_secret` with your app's credentials from the Spotify Developer Dashboard.

3. Update the **redirect URI** in your Spotify app settings:
   - Go to your Spotify Developer app dashboard.
   - Add the following redirect URI: `https://google.com`.
   - Save the changes.

4. Run the script:
   ```bash
   python spotify_playlist_creator.py
   ```

---

## How It Works

1. **Scraping Billboard Hot 100**  
   - The script takes a user input date (`YYYY-MM-DD`) and scrapes the Billboard Hot 100 chart for that day using `BeautifulSoup`.
   - It extracts song titles from the chart.

2. **Spotify Authentication**  
   - The script authenticates with the Spotify API using the `Spotipy` library.
   - It uses the `playlist-modify-private` scope to allow playlist creation.

3. **Song Matching and Playlist Creation**  
   - The script searches Spotify for each song using its title and year.
   - If a match is found, it adds the song's URI to a list.
   - A private playlist named after the Billboard chart date is created in your Spotify account, and the matched songs are added.

---

## Example Usage

1. Run the script and input a date:
   ```
   Which year do you want to travel to? Type the date in this format YYYY-MM-DD: 2000-08-12
   ```

2. The script will:
   - Scrape the Billboard Hot 100 chart from August 12, 2000.
   - Search Spotify for the songs from that chart.
   - Create a playlist in your Spotify account titled `2000-08-12 Billboard 100`.

3. Output:
   - Found songs are added to the playlist.
   - Songs not available on Spotify are skipped with a log message.

---

## Important Notes

1. **Billboard Scraping**:  
   - The script uses HTML structure specific to Billboard's website. If the structure changes, the scraper may break and require updates.
   
2. **Spotify API Rate Limits**:  
   - Be mindful of Spotify's API rate limits when searching for songs.

3. **Missing Songs**:  
   - Not all Billboard songs may exist on Spotify. These songs are skipped, and a message is printed.

4. **Environment Variables**:  
   - Store your Spotify credentials securely in the `.env` file. Never hardcode sensitive information in the script.

---

## Future Enhancements

- Add error handling for network issues or API rate limits.
- Allow users to select different playlists (e.g., Top 50 or Global).
- Implement support for multiple dates or a range of dates.
- Improve matching logic to handle misspelled or alternative song titles.

---

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.


