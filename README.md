# Hwush

An offline music player for Android, with a fluid animated look, a built-in turntable and an audio editor.

Hwush plays the music already on your phone. No account, no ads, no tracking. The only thing that ever uses the internet is the optional lyrics search.

## Player

- Library by songs, albums, artists, album artists, composers, genres, years and folders, with duplicate finder, smart playlists and a recycle bin
- Gapless playback and a true crossfade between songs
- Queue you can drag to reorder, save and undo
- Synced lyrics (`.lrc`) with word-by-word karaoke, a full-screen lyrics view, lyric image cards and lyrics fading in behind the app
- Find lyrics online from inside the app and save them to the song
- Ten-band precision equalizer, saved per album or artist, plus balance, mono, spatial sound and per-song volume and speed
- Speed and pitch sliders, A-B loop, bookmarks, ReplayGain, sleep timer and audiobook/podcast mode
- Auto DJ that builds sets by tempo and energy
- Notification and lock screen controls, widgets, a quick settings tile, Android Auto browsing, car mode and an alarm clock
- Listening stats, Wrapped, achievements and goals
- Tag editing, file renaming and ringtone cutting
- A **What's new** page with every update

## Fluid background

The colours of the playing song flow behind every screen. Drag a finger to push them around. In Settings you can pick the style (clouds, lava lamp, marble), speed, darkness, glow orbs, sparkle, and switch it off or limit it to playback to save battery.

## Turntables

Two decks you can scratch with a finger, a crossfader, filters, echo, stutter, reverse and cut buttons, and a 4x4 pad grid with 12 drum sounds and 4 chop pads cut from your songs. Record the performance as a `.wav`.

## Audio editor

A timeline editor (Browse → Audio editor) for working with your songs:

- Six tracks of clips from your songs. Move, split, trim, copy, fade and change the speed of clips
- Match one song's tempo to another, and read a song's tempo, energy and loudness
- Split a clip into vocals, instruments and bass. This is done on the phone from the stereo picture and pitch, so it is rougher than an AI service
- Mix the tracks with volume, pan, mute and solo, and export to `.wav`

The editor works on a copy in memory of up to about two and a half minutes per song, and does not save projects yet. Export before you leave.

## Wallpaper and lyrics behind the app

Pick your own picture, or the fluid colours of the playing song, as the background of the whole app. The bars and mini player are see-through. While a song with timed lyrics plays, one line at a time fades in behind the app.

## Building

Hwush has no local build step. A GitHub Actions workflow builds a signed release APK.

1. Put `hwush.zip` in the repository. The project files must be at the top level of the zip.
2. Push. The workflow unzips it into `project/` and builds.
3. Download the APK from the workflow run.

To build locally instead, open the project in Android Studio, or run `./gradlew assembleRelease`. Signing uses `app/hwush.jks`.

## Technical notes

- Kotlin 2.0, Jetpack Compose (Material 3), Media3 / ExoPlayer
- minSdk 26, targetSdk 34, package `com.hwush.player`
- All settings and library data live in a single JSON store on the device
- Turntables and the audio editor mix their own audio through `AudioTrack`; the player uses ExoPlayer
- Visuals are drawn on Canvas, so they run on Android 8 to 11 as well as newer versions

## Privacy

Everything stays on your device. The one network feature is lyrics search, which sends the song title and artist to [LRCLIB](https://lrclib.net) when you ask for it. Hwush asks for audio access to read your music, and the internet permission only for that search.

## Status

Hwush is a personal project under active development. Some parts, especially the audio editor, are young and may have rough edges.
