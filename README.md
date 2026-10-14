# Hwush

A native Android music player that works fully offline. No ads, no tracking, no account, no internet needed.

Hwush plays the music already on your phone and cares about the things that make a player feel good to use: clean tags and covers even when your files are named `19283728492.flac`, synced lyrics, a lock screen player, a glassy now-playing screen, and smooth animations.

> Hwush is a young, actively developed project. It is built and tested by one person on a phone, so expect rough edges. Bug reports are very welcome.

## Download

Get the latest APK from the [Releases](../../releases) page, open it on your phone and allow "install from this source" when Android asks.

Requires Android 8.0 or newer. Phones and tablets are supported, and tablets in landscape get their own layout with the player always visible.

Updates install over the previous version and keep your playlists, favourites and settings.

## Features

**Library**
- Songs, albums, artists, genres, years and a folder tree you can browse
- Search, sorting, and hiding songs or whole folders
- Duplicate finder
- Ratings, favourites and multi-select
- Edit title, artist, album and cover inside Hwush (your audio files are never modified)
- Home screen with recently played, most played and recently added, with sections you can reorder or hide
- Bottom tabs you can reorder or hide

**Playlists**
- Your own playlists with custom cover images
- Smart playlists that fill themselves from rules you choose (rating, plays, genre, artist, recently added, not played for a while)
- Pin playlists to the top
- Grid or list view

**Playback**
- Gapless playback, queue editing, shuffle and repeat
- Speed and pitch controls that work independently, with no chipmunk effect
- Equalizer, bass boost and loudness, with per-song sound settings
- ReplayGain volume normalising
- Fade between songs, and an experimental overlapping crossfade
- Sleep timer
- A-B loop and bookmarks inside a song
- Remembers where you stopped in long tracks
- Optional shake to skip and Bluetooth or headphone auto-resume

**Lyrics**
- Synced `.lrc` lyrics with a karaoke style highlight
- Pick a `.lrc` file per song, or a lyrics folder
- Built-in lyrics editor with a "stamp line" button for timing
- Share lyrics as a picture with the cover

**Looks**
- Accent colours from your wallpaper, the album art, or your own pick
- Light, dark and pure black themes, plus Classic, Rich and Mono surface styles
- Glassy now-playing screen with a blurred cover, a reflection and an adjustable glass strength
- Optional visualizer, spinning disc cover and car mode
- Custom bundled fonts and an opening animation
- Gestures: swipe the cover to skip, double-tap to play or pause, swipe song rows to queue them

**Everywhere else**
- Own notification with cover and controls
- Lock screen player
- Home screen widgets in a bar and a big square size
- Share songs to other apps
- Ringtone cutter that saves a clip you can set as your ringtone
- Listening stats and a "wrapped" style story of your most played music
- Backup and restore of your playlists and settings

## Permissions

| Permission | Why |
| --- | --- |
| Audio files (read media audio) | To find and play your music |
| Notifications | To show the playback controls |
| Display over other apps | Only for the lock screen player on Android 10 and newer |
| Microphone (record audio) | Only if you switch on the visualizer. Android uses this permission for the audio visualizer API. Hwush only reads the audio it is playing and never records anything |

Hwush has no internet permission and sends nothing anywhere.

## Building from source

The project is a standard Android Gradle project written in Kotlin with Jetpack Compose and Media3.

- Kotlin 2.0, Jetpack Compose, Media3 (ExoPlayer and MediaSession)
- `minSdk` 26, `targetSdk` and `compileSdk` 34

This repository builds the APK with GitHub Actions. Upload the project zip, the workflow unpacks it, builds a release APK and publishes it on the Releases page.

To build locally: open the project in Android Studio, or run

```
gradle :app:assembleRelease
```

## Support

Hwush is free. If you like it and want to say thanks, you can [buy me a coffee on Ko-fi](https://ko-fi.com/hwush).

## Feedback

Found a bug or have an idea? Open an issue on this repository. Please include your Android version and phone model.
