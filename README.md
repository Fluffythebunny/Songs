# Pugthym Manifest Format

This document describes the JSON format used for song manifests in Pugthym.  The manifest file (`manifest.json`) lists the songs available in a repository, along with metadata such as title, artist, BPM, and difficulty information.

## Manifest Structure

for some reason the audio does not load so make sure to have it so people can go to the repo and download the audio where u can load it locally
The manifest is a JSON object with the following properties:

* **`songs`**: *(Array, required)* An array of song objects, each representing a single song.

## Song Structure

Each song object within the `songs` array has the following properties:

* **`title`**: *(String, required)* The title of the song.
* **`artist`**: *(String, required)* The artist of the song.
* **`bpm`**: *(Number, required)* The beats per minute of the song.
* **`audioFile`**: *(String, required)* The path to the audio file for the song, relative to the manifest file.  Should be a `.mp3`, `.ogg`, or `.wav` file.
* **`chartFile`**: *(String, required)* The path to the chart file for the song, relative to the manifest file. Should be a `.json` file following the Pugthym Chart Format.
* **`difficulties`**: *(Array, required)* An array of difficulty objects, each representing a different difficulty level for the song.

## Difficulty Structure

Each difficulty object within the `difficulties` array has the following properties:

* **`name`**: *(String, required)* The name of the difficulty level (e.g., "Easy", "Normal", "Hard").
* **`level`**: *(Number, required)* A numerical representation of the difficulty level.  This can be any number, but it's recommended to use a consistent scale (e.g., 1-10).


## Example

```json
{
  "songs": [
    {
      "title": "Example Song",
      "artist": "Example Artist",
      "bpm": 120,
      "audioFile": "audio/example_song.mp3",
      "chartFile": "charts/example_song.json",
      "difficulties": [
        {"name": "Easy", "level": 3},
        {"name": "Normal", "level": 5},
        {"name": "Hard", "level": 8}
      ]
    }
  ]
}
```
