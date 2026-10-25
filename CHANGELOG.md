# GlideMix development history

GlideMix has been built in the open-source tradition on top of Audacity, one small step at a time.
Since the first build on **13 September 2026** there have been **350+ changes**. Here is what happened, week by week.
Installers and detailed notes for every public version are on the [Releases](../../releases) page.

---

## Public versions

### v1.1.10 Beta · 25 Oct 2026
- The rekordbox XML file chooser opens in Documents (or the last XML's folder); on Windows it opened in a system folder.

### v1.1.9 Beta · 25 Oct 2026
- **rekordbox XML opens like Lexicon**: the song count beside Rekordbox XML, playlists and folders beneath it.
- A **progress bar ("Loading 42%")** while a big XML is read; a clear message when the file isn't a rekordbox XML.
- Copying rekordbox songs into the Music Collection is now **Copy Rekordbox XML into Music Collection…**.

### v1.1.8 Beta · 24 Oct 2026
- **Find Duplicates**: songs that are in the collection more than once, best copy first, and Select extra copies.
- **Smart Playlist generator**: one smart playlist per genre, key or energy level in one go.
- The sidebar marks the playlists that contain the selected song; lists remember their sort and scroll position.
- Folders added in Preferences are scanned at once; cue markers show right after analysis; better high-energy ratings.
- New website **[glidemix.com](https://glidemix.com)**, linked from the Help menu.

### v1.1.7 Beta · 22 Oct 2026
- **Energy 1–10**: a column after BPM, sortable and in Smart Playlists; Lexicon songs keep Lexicon's energy.
- **Energy of the mix** behind the tempo line (ENERGY button), blue to red.
- **Watch folders**: new songs in your music folders are added and analysed automatically.
- **Cue points** on the library waveforms, and phrase hot cues in the rekordbox XML export.

### v1.1.6 Beta · 21 Oct 2026
- **Smart Playlists**: rules that pick tracks from your collection, Lexicon or rekordbox (harmonic key and BPM ± % included).
- **Export to Folder**: a playlist's songs in order, with a track list and an .m3u8.
- **Export to rekordbox XML**: tags, stars, colors, beat grids and playlists, for rekordbox and Lexicon.

### v1.1.5 Beta · 19 Oct 2026
- **Tracklist** with every export: a timestamped .txt for Mixcloud and show notes, plus a .cue sheet.
- Demo: a "Glide Mix demo" voice every 2 minutes instead of silent gaps; demo exports are MP3 96 kbps, up to 20 minutes.

### v1.1.4 Beta · 18 Oct 2026
- **Learn** page on Home: getting started, what's new, shortcuts, Discord, support, licence.
- LATCH removed again: ARM records knob moves as before, simpler for DJs.
- Meters start in the **gradient** style (green, yellow, red), like a DJ mixer.

### v1.1.3 Beta · 18 Oct 2026
- **Loudness report** after every export: LUFS, true peak, peak, and what streaming sites do with it.
- **True-peak limiter** on every output: mixes stay under -1 dBTP, so MP3s made from them don't distort.
- **S-curve tempo glides** between songs at different tempos; right-click a tempo point to choose.
- **Fade shapes** for transitions: equal power, linear, S-curve, early, late.
- **LATCH** next to ARM: your last knob value keeps recording until you stop.

### v1.1.2 Beta · 18 Oct 2026
- **One licence, everything included**: GlideMix – €49 (one-time, 3 computers, all 1.x updates).

### v1.1.1 Beta · 18 Oct 2026
- **Better sound on 2-core PCs**: a high-quality sample-rate converter replaces a cheap one that dulled hi-hats and cymbals (playback and export).

### v1.1.0 Beta · 18 Oct 2026
- **GlideMix is in Beta.** Free demo download; a licence (GlideMix €29, Pro €49, one-time) removes the demo limits.
- **Help → Licence…**: buy, enter your key, or free this computer for another one.
- **Source code** of every release as one archive, next to the installers.

### v1.0.9 · 18 Oct 2026
- **Edit Tags**: right-click a song (or several) → Edit Tags…: title, artist, album, genre, year, comment and more.
- Tags are **saved into the music files**, so rekordbox and Lexicon pick them up after re-reading the tags.
- Edits on Lexicon and rekordbox songs show in GlideMix right away; their own databases stay untouched.
- About → credits: a **Works with** section for rekordbox and Lexicon.

### v1.0.8 · 18 Oct 2026
- **Ratings and colors work again** in the library: stars and colors show up the moment you set them.
- Rate and color **Lexicon and rekordbox songs** too (stored in GlideMix; their own databases stay untouched).
- **Select Color** offers rekordbox's 8 track colors, each with its color circle.

### v1.0.7 · 14 Oct 2026 (Mac & Windows)
- Fixed a crash when pressing **Perform** or **Stop** (mostly Windows).
- Windows gets everything from v1.0.6.

### v1.0.6 · 13 Oct 2026
- **Exports sound exactly like playback**, with the limiter, tempo line and automation: no more clipping.
- Optional **automation lanes** of their own under a track, saved with the project.
- Library drags never stick to the mouse; GlideMix's folder moved from Documents to Music.

### v1.0.5 · 12 Oct 2026
- **Single wave**: a stereo track drawn as one waveform in half the height.
- Fixed a crash while adding songs (Mac).

### v1.0.4 · 12 Oct 2026
- **Mac updates install themselves** (Sparkle); updater apps can see GlideMix.
- Stop button right beside PERFORM; stem lanes named by stem (Drums, Bass, Vocals, Other).

### v1.0.3 · 11 Oct 2026
- **Help → Keyboard shortcuts**: the full list, searchable, with an editor.
- No more empty band on notched MacBook screens; full screen fixed.

### v1.0.2 · 11 Oct 2026
- **Much faster analysis**: rekordbox and Lexicon grids are used first.
- Double-click a song to add it to the end of the mix.
- Windows: no blink after a drop, GlideMix icon everywhere.

### v1.0.1 · 11 Oct 2026
- **Built-in updates**: GlideMix checks for new versions itself. Windows updates install silently.
- A new phrase model trained on 35,000 tracks.

### v1.0.0 Early Preview · 5 Oct 2026
- First tester build under the name **GlideMix**, for macOS and Windows.

---

## Before the first public version

### 4–6 Oct 2026: analysis, automation and Windows
- New beat-grid detection and the **GlideMix Phrase Detector** (intro, chorus, drop, outro) built into the app.
- **Plugin automation the Ableton way**: any knob of any VST3/AU plugin, every line visible at once, **Arm** to record moves.
- Master safety limiter; tempo glides between songs.
- Windows: crackle-free playback, every audio format, non-ASCII file names, tuned for small PCs.
- Library like rekordbox: drag playlists and folders, Quick Links, Analyze/History/Recordings views.
- Quick Start manuals for testers (Mac and Windows).

### 26 Sep – 29 Sep 2026: GlideMix is born
- The app gets its name: **GlideMix**.
- **Stems**: split a song into drums, bass, vocals and other.
- **Transitions with effects**: filter sweeps, risers, downsweeps, echo and reverb outs, mixer beat effects.
- HD color waveforms on the timeline and in the library.
- Cover art for rekordbox and Lexicon tracks; key detection for every format.
- **Broadcast**: song titles sent to Shoutcast/Icecast as Artist – Title.
- Self-contained installers with FFmpeg and the key analyzer inside.
- A full **Preferences audit**: 28 pages reduced to the 12 that matter, in the order a DJ works.

### 20 Sep – 22 Sep 2026: performing and broadcasting
- **Perform** grows up: red audience playhead, Stop button, separate room and headphone meters and levels.
- rekordbox's color waveform, per clip at full resolution; Snap to Beat and Smart snap.
- **Live broadcasting** to Icecast and Shoutcast (v1 and v2), with stream meters and auto-reconnect.
- **Mix Now** with phrase-matched landings and bass-swap transitions; a transition builder.

### 15 Sep 2026: the new engine
- A new **playback engine** built for DJ mixing: keylocked time-stretch per clip, effects with automation, multi-core.
- **Beat grid editor** in the style of rekordbox's GRID/PHRASE EDIT, with its own deck and metronome.
- **IN/OUT anchors** with magnetic snap, transition presets, **Mix Now**.
- **Perform**: the mix on outputs 1–2, the headphone preview on 3–4.

### 13–14 Sep 2026: the first build
- The DJ library: analysis, preview, key wheel, beat grids, alignment.
- **Lexicon** and **rekordbox XML** in the sidebar, with playlists, beat grids, cue points and phrases.
- Tempo line under the ruler, SYNC, KEYLOCK, BEATMATCH crossfades, half/double tempo.
- 24 built-in DJ effects, tempo- and beat-synced, with presets.
- The cloud, sign-in and store parts of Audacity removed: GlideMix works fully offline.
