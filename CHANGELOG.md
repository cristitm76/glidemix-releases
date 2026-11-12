# GlideMix development history

GlideMix has been built in the open-source tradition on top of Audacity, one small step at a time.
Since the first build on **13 September 2026** there have been **350+ changes**. Here is what happened, week by week.
Installers and detailed notes for every public version are on the [Releases](../../releases) page.

---

## Public versions

### v1.2.8 Beta · 12 Nov 2026
- **Samples tab:** your own sample and sound-effect folders, scanned in the background into a separate sample list (40,000+ files in minutes, seconds after that). First folder level = category tiles, second = packs; BPM, key, loop/one-shot and bars read from the names; sortable, movable columns; thin waveforms; preview at the mix tempo (loops) or own speed (one-shots), Up/Down preview, shared preview volume; Show in Finder/Explorer; disks that are not connected keep their samples.
- **Sample line:** a SAMPLES button on every song lane opens a "Sample line" right under it (eye button to fold it, saved with the project). Drops onto it: loops snap to the nearest bar with their BPM as raw tempo and Follow song tempo on (half/double folded), one-shots land where dropped at their own speed; a drop never cuts a sample already there; several files line up. Samples dropped on a song lane are refused with a hint. Samples never count as songs (SONG counter, transitions, tempo line, Sounds like reference, lane picking).
- **Save as sample:** right-click a selection inside one song: a 24-bit WAV of exactly that range (the clip's own audio, no volume line or effects), named "<song> 8 bars 128 Am", saved by default in the Projects folder's Samples folder (system save window, last folder remembered), in the Samples tab at once.
- **Stems of a selection:** Stems as samples (drums, bass, vocals, other, all four) and in place: Remove drums / bass / vocals / other from the selected part only (short edge fades), or Split into stems (four stem lanes holding only that part, the song silent there). The whole song is separated once and cached, then the range is cut out. One undo step each.
- **Fixed:** stem lanes go under the song's sample line; the SONG counter no longer counts stem lanes; a sample folder added under another spelling of its path is not listed twice; sample lists from earlier test builds are read again correctly.

### v1.2.7 Beta · 11 Nov 2026
- **Volume Fade (MixMeister's Beatmix 8 bars) is the default transition** for new pairs and Mix Now: the outgoing song 0 dB at its OUT to -6 dB over 32 beats (straight), silent a quarter beat later; the incoming song silent until its IN, -6 dB on it, 0 dB 32 beats later. Volume only, no EQ. A stored old default (quick crossfade + bass swap) moves over once; a transition picked by hand stays.
- **Fades follow the anchors.** Dragging an OUT or IN anchor moves every song after it and writes the pair's transition again from the new anchor, clearing the old fade wherever it was left (also where it slid with the song on an IN drag). A linked anchor stops where the songs can no longer follow, so IN and OUT never come apart. Transition names survive undo.
- **Deep IN anchors:** a song whose IN lies far into it may start before the song it mixes out of; the pair is still a transition (it was taken for stem layers when the overlap was large). A fade cut short by the end of a song stops at the level reached instead of sliding to silence.
- **Right-click on an IN / OUT flag:** Volume Fade (MixMeister), GlideMix transition (crossfade + bass swap), turn the transition off/on.
- **Ghost waveform:** where the volume line is silent (before the IN, after the cut) the song is drawn faintly from its HD analysis. Drawing only.
- **Sounds like column in the main library** (sortable, closest first; unmeasured songs last) and a **"Sounds like: at least N %"** rule in the Related settings; click the set rating star again to clear the rating rule.
- **Fixed:** Delete/Backspace on the timeline lost out to the library's own Delete shortcut (it applied app-wide whenever a library row was selected); a deleted song left its empty lane behind under its name (now removed in the same undo step); lanes 2, 3, 4 came in twice as tall as lane 1 (a new lane copied the other's height before its Single wave doubling).

### v1.2.6 Beta · 11 Nov 2026
- **Sounds like.** During analysis every song gets a sound fingerprint of about 40 numbers: timbre (MFCC, mean and spread), brightness, the balance of five bands, noisiness and groove, measured on the song's loud main parts, not the intro or breakdowns. Stored in the library.
- **Related sorts by sound.** The Related rules (key, BPM and the others) still pick the songs; among them, the ones whose fingerprint is closest to the song under the playhead come first, a little lower for another compatible key or a few % of BPM away. The Related tab's new **Sounds like** column shows the share of the whole library that sounds less alike (100 % = the closest song of all).
- **Background measuring** for songs analysed before: one light pass per song (a decode, no beats or key) at the lowest priority, newest songs first, waiting while anything plays or songs are being analysed; songs on an unplugged disk are tried again next start.
- **LED meter** above the clock: 40 × 7 dots of the mix the audience hears (Play, or Perform while performing), in a colour sweep from red lows to violet highs; dark when stopped; right-click to hide.
- **Loop bar under the ruler:** loops are drawn, moved, stretched and switched on/off in the strip under the time numbers; a click on the numbers only moves the playhead.
- **Audio setup and Music library** moved beside the Workspace picker; the Workspace label is centred over its box. Fixed the top toolbars running off the window's edge when one grows after start-up.

### v1.2.5 Beta · 11 Nov 2026
- **Edit like in Ableton.** Z zooms to the selection, X goes back one step at a time, = and - zoom; ⌘/Ctrl+E splits (was ⌘I), ⌘/Ctrl+L loops the selection or clip, ⇧⌘/Ctrl+Shift+J crops, R reverses (Record moved to F9), ⌘/Ctrl+R renames, ⌘/Ctrl+1–4 finer grid, coarser grid, triplets, snap. A saved shortcut list moves to the new keys once, where it still had the old ones.
- **Right-click menus in Ableton's order** on a selection, a clip and the empty timeline: Cut, Copy, Paste, Duplicate, Delete; Zoom to selection / Zoom back; Split, Join, Split at silences; Loop, Crop, Reverse, Silence; Cut time, Paste time, Delete time; Snap to grid and a Grid submenu (1 Bar to 1/32, Narrow, Widen, Triplet).
- **Thin automation lines with values,** like Logic: a thinner line and small dots, and the value beside each point: dB on volume lines, % on effect lines, BPM on the tempo line.
- **Icon-only toolbar in category capsules:** levels and metronome; Sync, Keylock, Link; Snap; Tempo, Energy; Perform, Stop, Broadcast, Mix now; Arm, Re-enable (now a switch). New Keylock, Arm, Mix now and Reset view icons; every tooltip says what the button does.
- **⌘/Ctrl+A** selects all songs while the song list has the keyboard, the whole timeline otherwise.
- **Fixed:** a crash when zoomed in to single samples with clips just off screen (seen with 40 songs in a mix).

### v1.2.4 Beta · 10 Nov 2026
- Library preview fixes.

### v1.2.3 Beta · 10 Nov 2026
- **No more long freezes with a big library and many smart playlists.** A beat grid change (Alt+arrow keys or the Beatgrid editor), adding songs or starting up recounted every smart playlist with a full pass over the library each, on the main thread: up to half a minute with 70 playlists and 50,000 songs. Now the library is read once and the counting runs in the background, shared by every open song list.
- **Set IN and OUT anchors from the keyboard:** ⌥/Alt+I and ⌥/Alt+O at the playhead on the selected song (changeable under Shortcuts).
- **Rename a project** from its … menu on the Home page.
- **Fixed:** the Related tab's search box did nothing (it now narrows the related songs with the library's search terms); Windows showed "GlideMix 1.1 beta dev" in Task Manager.

### v1.2.2 Beta · 10 Nov 2026
- **Tempo-synced plug-ins follow the beat.** VST3 and Audio Unit plug-ins (loopers, tape stops, beat gates, beat FX such as TimeStop, Maddix Rumble, Serato Hex FX, Trance Gate) now get the tempo (tempo lane glides too), the beat and the bar, counted from bar 1. Before, they loaded but did nothing.
- **Fixed:** AIR plug-ins (and others that carry their own Qt, Serato Hex FX too) crashing GlideMix a few seconds after opening (Mac); a crash when quitting with plug-ins like TimeStop or Hyperlift loaded.

### v1.2.1 Beta · 9 Nov 2026
- **Customize the toolbar, like Safari.** Right-click the toolbar (or its gear): drag buttons in, out and along it; Space and Flexible Space; icon and text, icon only or text only, with new GlideMix icons for SYNC, TEMPO, ENERGY, KEYLOCK, LINK, PERFORM, MIX NOW, ARM and RE-ENABLE; the default set puts it back. An emptied group leaves no gap.
- **Key column your way:** plain text, coloured text or coloured badges (Preferences > Music library).
- **Fixed:** empty tooltip boxes; submenus that opened only on a click; the transition dot at a clip's edge adding a new dot on every drag; track headers a few pixels below their timeline rows; the library sidebar flashing to the top while songs are analysed; Color > Intensity in the track header menu; square OK/Cancel buttons in popups.

### v1.2.0 Beta · 9 Nov 2026
- **A new, modern look.** Rounded buttons, fields, lists and menus; every panel is its own rounded card with a small gap around it. Buttons are pills: purple when on, a thin outline when off.
- **A display at the top:** clock, key, energy and place in the mix (song 2 of 4) of the song under the playhead, processor and disk use, a light that is green while playing.
- **Toolbar in groups,** each in its own capsule: play controls, editing tools, SYNC/TEMPO/ENERGY/KEYLOCK, LINK/PERFORM, MIX NOW/ARM.
- **New knobs and faders:** flat knobs with a thin arc in the channel's colour (hover or turn for the value); slim faders with see-through glass caps, also on track volume, zoom sliders and the meter.
- **See-through menus** with a soft blur behind them (Mac; Windows 11 menus and lists), drawn by the system.
- **Library toolbar on top:** New, All, Select All, Analyze, Match and Related in one row with the Key Wheel; the search below.
- **Light theme in GlideMix purple** instead of pale lavender. Smaller touches: rounded dialog buttons, ROOM/CUE pills, the Workspace name above its picker, LOW/MID/HIGH/COLOR pills on each track.

### v1.1.33 Beta · 9 Nov 2026
- **Match.** A library button that lights the Key cell green for songs that mix with the song under the playhead (the incoming song in a transition), in every list, following the playhead.
- **Related.** A tab with the full song table for the songs that go with the song under the playhead: same key first, then the closest BPM; sorting, drag and double-click as in the library.
- **Match and Related rules** (gear next to Match), shared by both: BPM ± % with half/double tempo, key width, energy, year, date added, history (songs played around it in GlideMix's History), same artist (also "feat." in titles), genre, composer, remixer, label, colour, rating (stars), comment text, any tag column, file format.
- **Charcoal theme.** Following the system now means Charcoal on a dark Mac or PC; the previous dark theme stays, renamed Grey.
- **Sorting:** a third click on a column header goes back to the view's own order. A new or opened project shows the Music library tab first.
- Fixed: black pencil and plus icons in the Workspace menu.

### v1.1.32 Beta · 9 Nov 2026
- **A faster library.** The song list holds the whole collection in memory and asks the database only for the order of a view, so there are no more 2000-song pages: scrolling to the end, sorting (20-100 ms on 36,000 songs) and searching (about 30 ms) no longer stall. Edited songs are re-read one by one; rows are recycled while scrolling. rekordbox XML, Lexicon and the DJ apps show every song too.
- **Select All -> Analyze** reaches every song in the list; never-analysed songs go first and the Analyze count goes down live.
- **Import from Rekordbox XML** shows a small progress window and what it found.
- Mac: quitting while the DJ apps were still being read could crash GlideMix. Fixed.

### v1.1.31 Beta · 8 Nov 2026
- **Windows: freezes with network drives fixed.** Since 1.1.29 GlideMix checked all drives every few seconds for DJ libraries, on the main thread; a mapped network drive that was offline or not ready held the window up until the network timeout. Now only local drives (internal, USB, SD card) are checked, in the background. A DJ library on a network share is still read when its folder is added in Preferences > Library > Other DJ Apps.

### v1.1.30 Beta · 8 Nov 2026
- **Crash fix (Mac):** hovering a track header's volume fader closed GlideMix. Its value tip was tied to a part of the fader the DJ look had replaced; it now sits on the fader cap again and follows it while you drag (on Windows too).
- Pop-up tips whose control has just gone away are skipped instead of opened.
- Crash reports show where a crash really happened.

### v1.1.29 Beta · 8 Nov 2026
- **Waveforms like the Beatgrid editor.** The timeline and the library now draw every song with the Beatgrid editor's colours and shape (same band split, colours and peak/core look). Each song's picture is redone once, in the background.
- **Your DJ apps on every drive.** Engine DJ, Serato and VirtualDJ libraries kept on other drives (SD card, USB) are read too; a drive plugged in later shows up by itself.
- **Preferences > Library > Other DJ Apps:** show or hide each app, and add folders where an app keeps its library.
- **Stems share one transition:** one pill for a song and its stems; every change reaches all of them, one Undo.
- **Low, Mid, High and Color** lines from the track header glow like the pill's lines.
- Small fixes: an empty library says how to add music; the key wheel no longer moves the sidebar; Windows stems always run on the processor; About shows the VST Compatible logo and credits Ableton Link.

### v1.1.28 Beta · 8 Nov 2026
- **Ableton Link.** Turn on LINK in the toolbar and GlideMix shares your mix's tempo, beat and play/stop with other Link apps on the network. Resolume, TouchDesigner and other VJ software follow the mix, glides included.
- **Your other DJ apps, in GlideMix.** Engine DJ, Traktor, Serato, VirtualDJ and djay appear in the library with their songs and playlists (read only). Songs they already analysed keep their beat grid and key, so GlideMix doesn't work them out again.
- **Mixed In Key:** the key and energy in the comment ("8A - Energy 7") are read. Comments are kept, and Edit Tags has Key, Energy and Rating.
- **Low, Mid, High and Color buttons** in every track header show each line over the whole song.
- **Library:** the list goes past 2,000 songs; counts on smart playlists, Duplicates and Analyze; Back after Show in Library; save a search as a smart playlist; columns for any file tag (Mood, Label, Remixer…); arrow keys in the song list; a preview volume.
- **Playlists:** right-click > Export as M3U8 Playlist.
- **Automation:** right-click a point > Set value… (Set tempo… on the tempo line), and Shift-click several points to move them together.
- Small fixes: the key shows in the clip header; a library scan no longer makes GlideMix stall; the + menu for closed tabs no longer overlaps; the song count above the list is right for smart playlists and other lists.

### v1.1.27 Beta · 7 Nov 2026
- **Adding a song no longer resets your transitions.** Before, adding a song at the end of a mix reset every transition to the default and could move songs. Now only the new song moves and gets a transition. Everything you shaped by hand stays.
- **No more sudden quits when the project can't be backed up.** If GlideMix can't write its automatic backup (disk full, or the file is in use by a sync or antivirus tool), it now warns you instead of closing.
- **Easier to grab:** bigger points, the nearest one is picked, and points on the IN/OUT lines can be dragged.
- **Cleaner:** no more clusters of dots. Each fade shows only its corners.
- **Press and drag** on a line adds a point and moves it in one go.
- **All lines work like the volume line:** 100% sits at about three-quarters height, and above it boosts.
- **Transition lines** get dots in their own colour.
- **The vertical ruler** now shows the volume scale in dB, lined up with the volume line.
- **Click a song's waveform** to preview it from that spot. While your mix plays, it starts on the same beat of the bar, at the mix's tempo.
- **Analysis continues by itself** after GlideMix is closed or stops unexpectedly. A file that stops it twice is skipped.
- **Songs added during analysis** are now analysed in the same run.
- **Mouse wheel zooms the timeline:** an option in Preferences > Waveforms. Hold Cmd or Ctrl to scroll the tracks.
- **Phrase ribbon on or off:** a new switch in Preferences > Waveforms.
- **Space** plays the song in the Beat grid editor while you work in it.
- **Your own transitions** come first in the menus. "Show in menus" hides the ones you don't use.
- **Quick Links:** every folder can be removed. + adds it back.
- **A + beside the Music library and Project tabs** opens a closed tab again.
- A point near the end of a song now opens its own menu, not the track menu.
- A line that is flat to the end of a song stays flat when you move the point before it.
- Volume points sit above the phrase ribbon, where they can be clicked.
- The effects panel no longer shows a "Watch video" link.

### v1.1.26 Beta · 4 Nov 2026
- **Export is much faster.** A 16-minute mix now takes under 30 seconds on our Mac.
- **Plug-ins:** fixed a bug that could slow the app down or stop it working.
- **Stems:** fixed an install failure on some Macs.
- **MP3 exports** no longer clip at normal bitrates.
- **Starts cleaner:** you get to your music with fewer questions. The plug-in check waits for your first Add effect, and the licence window for your first export.
- A dot marks songs already in your project.
- The list shows its song count and total length, for searches and playlists too.
- Hover the search box to see its filters, like genre:house bpm:>125.
- Right-click a song on the timeline for Show in Library.
- The library now keeps its last four backups.
- Home shows how many songs each project holds.
- The File menu says Save project and Save project as.
- The transition pill shows the transition's name.
- One Undo fully reverses Mix Now, including the OUT marker and the transition's name.
- Closing the window on a Mac now really quits GlideMix.
- The demo's export is now a proper 44.1 kHz MP3.
- A plug-in that crashes during its check no longer brings up a crash message.
- Cleaner wording on the first-run screens and in messages ("1 file", not "1 file(s)").

### v1.1.25 Beta · 2 Nov 2026
- **Tempo line:** BPM markers at every transition, so you can see the tempo without scrolling back. Points and markers follow your theme color.
- **Reset** on the tempo line now returns every track to its real BPM, and the Project tab shows the tempo each song really plays at.
- **Import From File Tags** works: right-click songs > Metadata. Changed a tag in another app? Pull it into your library.
- **ReplayGain:** tags are read when songs are added, and Import From File Tags fills in songs already in your library.
- **Show in Library:** right-click a Project tab song to find the track, its album or its artist. Playlist songs get Show in Library too.
- **Search related Tracks:** no more stuck filters. The search shows on the key wheel or in the search box, and one click clears it.
- **Drag preview:** dragging a song onto the timeline now shows artist and title.

### v1.1.24 Beta · 2 Nov 2026
- We’ve polished the canvas and vaporized the bugs, making your GlideMix exports and artworks smoother than ever. Those glitches thought they were art, but we treated them like a bad sketch. Canvas cleared, bugs deleted. 🎨💥

### v1.1.23 Beta · 1 Nov 2026
- **Help > What's new**: read the What's new window again whenever you want.
- **Cancel stops the whole range**: pressing Cancel while a range of songs loads now stops the load and keeps the songs already in the mix.

### v1.1.22 Beta · 1 Nov 2026
- **Big mixes stay usable**: with 30 songs or more, lanes, track headers and sliders no longer drift apart when you change the track view, zoom or scroll, and you keep your place while lanes change height.
- **Reset view** button in front of the zoom sliders: lanes at their default height, the first songs readable.
- **Load a whole range from the library**: Shift-select, right-click, Load to > Project. The songs join the end of the mix in the same order, each one blended into the next.
- **The Project tab looks like the library**: cover art, waveform, key, genre, energy, duration and rating, with the transition pinned on the right.
- **What's new**: GlideMix tells you what changed the first time it starts after an update.
- **Single wave** is the default track view on a fresh install.

### v1.1.21 Beta · 1 Nov 2026
- **The Project tab**: your mix as a playlist next to Music library. Drag a row to reorder and the whole mix follows, IN on OUT, in one Undo. Click a row to zoom to that song. Pick each transition from its row; it's saved with the project.
- **Songs snap in every time**: a double-clicked song always joins the end of the mix with a transition, and a deleted song leaves no gap.
- **No more silence between songs**: the IN sits where the music really starts and the OUT stays on music that's still loud. The new song is at full volume on its IN and the old one leaves after its OUT.
- **Volume lines on from the start**, without looking for the automation button.
- **A huge library opens fast**: sorting 38,000 songs went from a two-minute freeze to a fraction of a second.
- **Plugins**: one that crashes GlideMix while loading, opening its window or playing is turned off on the next start, with a message naming it. VST3 knob changes while stopped are kept, and plugin names with accents show correctly.

### v1.1.20 Beta · 28 Oct 2026
- **Songs with special characters drop onto the timeline again**: with an effect on the master track, songs whose file names had accents, emoji or special spaces silently failed to land.
- **Much less CPU during playback**: only an open transition window follows the playhead now (about 100% → 36% on a test mix).
- Fixed a crash when closing a master effect's window. Known issue: AIR Music Technology plugins crash GlideMix; don't use them for now.

### v1.1.19 Beta · 28 Oct 2026
- **Transition window knobs you can play**: High, Mid, Low, Color and a real VOL fader change the sound while you turn them, record the move while the mix plays, and each move is one undo step. Fixed a crash on save after EQ moves.
- **BEATMATCH pills stay on their transition** after zooming; **the music keeps playing** when you drag the playhead elsewhere; **one copy per library drop**.
- **DJ-style knobs and faders** in the track headers, zoom and library sliders; **Single wave by default**; Preferences → Reset keeps your licence.

### v1.1.18 Beta · 27 Oct 2026
- **Songs land as one clip again**: adding a song never splits it by itself any more, and no piece ends up minutes away. Split a song whose beats really jump by hand: right-click → **Split at grid jumps**.
- **Phrase colours for Lexicon songs on any computer**, worked out in the background where rekordbox has none (for example Windows).
- **View → Track view**: every song as Waveform, Spectrogram, Multi-view, Half-wave or Single wave, also in Preferences → Waveforms.
- **The same Color and Track visualization menus** on a song and on its track name; the stems download just counts its steps.

### v1.1.17 Beta · 26 Oct 2026
- **Songs that jump off their beat grid stay on the beat**: a song whose beats move part-way (a demo stitched from loops, an edit, a mashup) is split just before the jump when you add it with Sync on, and the later part slides back onto the bar.
- Fixed: Undo and Redo after double-clicking a song into an empty project brought it back off the bar.

### v1.1.16 Beta · 26 Oct 2026
- **Loops the Logic way**: drag across the top half of the ruler to draw a loop; it plays at once. Right-click a selection → **Loop** (Shift+L) or **Split**.
- **Cmd+D / Ctrl+D repeats the selection** right after itself on the same track, in whole bars with Sync on; press again to keep going.
- Fixed "Connection to project file is null" when pressing Play after starting a new project.

### v1.1.15 Beta · 26 Oct 2026
- **The transition as a DJ mixer**: a 2-channel mixer laid out like a Pioneer DJM, with HI / MID / LOW and KILL, COLOR, channel faders and a crossfader with Smooth / Constant / Cut curves.
- **BEAT FX** with LEVEL/DEPTH and ON/OFF; **REC** writes your knob and fader moves into the transition while it plays.
- Choose the mixer or the classic transition window in Preferences → Transitions.

### v1.1.14 Beta · 25 Oct 2026
- **S-curves** on volume and FX automation, and crossfades drawn as one smooth line per song; no stray automation points left on screen.
- **Right-click the transition pill** to switch a transition off (grey) and on again; **transition effects** stay inside the transition, each with on/off, amount and remove (also fixed on Windows).
- Master effects with look-ahead stay in time with the playhead and exports; smooth track-height zoom; a double right-click in the library no longer adds a song.

### v1.1.13 Beta · 25 Oct 2026
- **Energy like level meters**: green when calm, yellow as it builds, red at the peak; the tempo line in the volume line's yellow.
- Library: **key badges** in the key wheel's colours, **energy LED blocks**, **zoom sliders** for text size and row height.
- **Analysis uses: Performance / Normal / Power saving**, like rekordbox; a steady progress line while analysing.

### v1.1.12 Beta · 25 Oct 2026
- **Much faster analysis:** on the Mac the beat grid runs on the graphics chip (Core ML) with the full beat model; 288 songs in 4 min 42 s on our test Mac (rekordbox 7: about 20 minutes). Windows uses all free cores per song.
- **Status line** at the bottom: what GlideMix is doing (scan, "Analysing 7 of 20 · time left", Stop), what the button under the mouse does, and a notice when a new version is out.
- Five outlined rating stars like rekordbox; Help → GlideMix Manual; folder choosers open in Music on Windows.

### v1.1.11 Beta · 25 Oct 2026
- Songs without an energy rating (e.g. from rekordbox) get one automatically once they are on the timeline.
- Lexicon songs show their energy rising and falling in the ENERGY view, not one flat block.

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
