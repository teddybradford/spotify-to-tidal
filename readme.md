A command line tool for importing your Spotify playlists into Tidal. Due to various performance optimizations, it is particularly suited for periodic synchronization of very large collections.

## Installation

Clone this git repository and then run:

```bash
python3 -m pip install -e .
```

or for Homebrew-managed python3:

```bash
brew install pipx
pipx install -e .
```

and make sure `~/.local/bin` is included in your PATH environment variable.

## Setup

1. Rename the file `example_config.yml` to `config.yml`
2. Go to [developer.spotify.com](https://developer.spotify.com/documentation/general/guides/authorization/app-settings/) and register a new app
3. Copy and paste your client ID and client secret into the Spotify part of the config file
4. Copy and paste the value for `redirect_uri` from the config file into the `Redirect URI` field for your developer.spotify.com app and press ADD
5. Enter your Spotify username in the config file

## Usage

To synchronize all of your Spotify playlists with your Tidal account run the following from the project root directory. Windows ignores python module paths by default, but you can run them using `python3 -m spotify_to_tidal`

```bash
spotify_to_tidal
```

You can also just synchronize a specific playlist by doing the following:

```bash
spotify_to_tidal --uri 1ABCDEqsABCD6EaABCDa0a # accepts playlist id or full playlist uri
```

or sync just your Liked Songs (favorites) with:

```bash
spotify_to_tidal --sync-favorites
```

or sync just your saved albums with:

```bash
spotify_to_tidal --sync-albums
```

See example_config.yml for more configuration options, and `spotify_to_tidal --help` for more options.
