
[![Build Status](https://github.com/pavelkomarov/exportify/actions/workflows/deploy.yml/badge.svg)](https://github.com/pavelkomarov/exportify/actions)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/pavelkomarov/exportify/master)

Export your Spotify playlists for analysis or just safekeeping: [exportify.net](https://exportify.net)

<a href="https://pavelkomarov.com/exportify"><img src="screenshot.png"/></a>

This is a hard fork of [the original Exportify repo](https://github.com/watsonbox/exportify). I simplified and updated the code, instituted rate limiting (because back when I forked, the original didn't work for large playlists or for all playlists at once), got rid of tests I deemed unnecessary, fixed a parsing bug when album or artist(s) names contain commas, enhanced the set of features, added logout functionality, set up automatic deployment to github pages, provided an interactive python notebook to do something interesting with the data, fixed null object bugs in the event of missing data, made the table sortable, modified to display all playlists at once (rather than pagination), treated the special case of liked tracks, and added playlist images.

### Export Format

Track data is exported in [CSV](http://en.wikipedia.org/wiki/Comma-separated_values) format with the following fields:

- [Track ID](https://developer.spotify.com/documentation/web-api/concepts/spotify-uris-ids)
- Track Name
- Album Name
- Artist Name(s)
- Release Date
- Duration (ms)
- Popularity
- Added By
- Added At
- Genres
- Record Label
- Danceability
- Energy
- Key
- Loudness
- Mode (Major or Minor)
- Speechiness
- Acousticness
- Instrumentalness
- Liveness
- Valence
- Tempo
- Time Signature

### Analysis

Run the [Jupyter Notebook](https://github.com/pavelkomarov/exportify/blob/master/taste_analysis.ipynb) or [launch it in Binder](https://mybinder.org/v2/gh/pavelkomarov/exportify/master) to get a variety of plots about the music in a playlist including:

- Most common artists
- Most common genres
- Release date distribution
- Popularity distribution
- Your songs' distributions of Acousticness, Valence, etc.
- Time signatures and keys
- All songs plotted in 2D to indicate relative similarities


### Development

Developers wishing to make changes to Exportify should use a local web server. For example, using Python (in the Exportify repo dir):

```bash
python3 -m http.server
```

Then open [http://localhost:8000](http://localhost:8000).

### Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -m "message"`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
