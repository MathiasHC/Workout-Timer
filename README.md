# Workout Timer

An analog workout timer in a single HTML file: no build step, no dependencies. Open `index.html` in a browser and press **Start**.

**Live:** <https://mathiashc.github.io/Workout-Timer/>

## Features

- **Analog dial.** One full turn of the hand is the whole workout. The dial redraws its scale for any duration, and a small dial shows the seconds.
- **Count up or count down.** Counting up, the hand shows elapsed time. Counting down, it shows the time left and runs backwards.
- **Get-ready countdown.** Pressing **Start** from zero counts down (10 seconds by default), beeps at 0 and then starts the timer. Set the length in the sidebar, where `0` turns it off. Resuming from **Pause** starts straight away.
- **Interval beeps.** A double beep every *n* minutes/seconds. Set the interval to `0:00` to turn them off. A longer tone always plays when the time is up.
- **Rounds.** With an interval set, enter a number of rounds and the duration becomes *interval × rounds*. The status line shows `Round 3 of 8`.
- **Settings sidebar.** Direction, duration, interval, rounds and get-ready sit in a sidebar on the left. It starts open on wide screens and slides over the dial on phones.
- **Light / dark switch** in the top-right corner. Your choice is remembered.
- **Keeps time in the background.** Beeps are scheduled on the Web Audio clock, so they stay on time even when the tab is in the background. Where the browser supports it, the screen stays awake while the timer runs.

Settings, theme and sidebar state are saved in the browser's `localStorage`.

## Running it

Open `index.html` directly, or serve the folder:

```sh
python3 -m http.server 8000   # then visit http://localhost:8000
```

On a phone, open the [live version](https://mathiashc.github.io/Workout-Timer/). It's served by GitHub Pages from `main`, and every push redeploys it.

## Notes

- Browsers only allow sound after you press something, so the first beep comes after **Start** has been pressed.
- Settings are locked while the timer is running or paused. Press **Reset** to change them.
