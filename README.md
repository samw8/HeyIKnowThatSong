# HeyIKnowThatSong

A song-guessing game. Pick any artist, hear one second of a random track from their
catalogue, and try to name it. Every miss buys you more audio: 1s, 2s, 4s, 7s, 11s, 16s.

**Play it:** https://samw8.github.io/HeyIKnowThatSong/

## Why I made it

I built this because of two things I love: music and Wordle. At some point I thought,
why not just build a combination of the two.

I love hearing new music, and I love trying to guess a song in the least amount of time
possible. I also love having a daily challenge to come back to, the way Wordle does it.
The two ideas came together so naturally, and I'm proud of how it turned out.

This is my first time building a project on my own, with some help from Claude along the way.

Music is something that should be adored and preserved, and I hope this adds to that
in some small way.

## How it works

- Search any artist, or pick one from the gallery on the front page.
- The game pulls their top tracks plus a handful of albums and builds a pool of playable previews.
- You get six guesses. The waveform shows how much of the 30-second preview you've unlocked
  and how much you've actually heard.
- Close spellings count — remaster tags, features, punctuation and small typos are all forgiven.
- Streaks and hit rate are saved locally in your browser.

## Running it

There's no build step and no dependencies. Open `index.html` in a browser and it works.

One caveat: the game talks to Deezer by injecting a `<script>` tag, because the Deezer API
sends no CORS headers. Some environments block third-party scripts — preview panes, in-app
browsers, and some ad blockers. If artist photos never load and search reports a connection
error, that's what's happening. Open the file in a normal browser tab or use the hosted link.

## Built with

Plain HTML, CSS and JavaScript in a single file. Canvas for the waveform, the Web Audio API
for decoding preview audio into peaks, `localStorage` for stats, and the
[Deezer public API](https://developers.deezer.com/api) for 30-second previews.
No account or API key required.

## Tweaking it

The knobs are all at the top of the `<script>` block:

| Constant  | What it does                                       |
|-----------|----------------------------------------------------|
| `STAGES`  | Seconds unlocked per guess — also sets guess count  |
| `TILES`   | How many artists show in the front-page gallery     |
| `ARTISTS` | The gallery pool                                    |
| `BARS`    | Waveform resolution                                 |

Colours live in the `:root` block at the top of the `<style>` tag.

## Licence

MIT — do what you like with it.
