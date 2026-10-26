# Sorting Algorithm Visualizer

Watch Bubble, Selection, Insertion, Merge, Quick and Heap Sort run step by step.

**Live demo:** https://subhanishat89-spec.github.io/sorting-visualizer/

![Screenshot](screenshot.png)

## Features
- 6 algorithms with color-coded bars (comparing, swapped or written, pivot, sorted)
- Array size (10 to 150) and speed sliders
- Start, Pause/Resume, Step, Reset and New array buttons
- Presets: Random, Nearly sorted, Reversed, Few unique values
- Live stats: comparisons, swaps/writes, elapsed time
- Info panel with time and space complexity, stability and a short description
- Optional sound (bar value maps to pitch), off by default
- Keyboard shortcuts: Space, N, S, R
- Responsive layout, automatic dark mode, labeled controls and a color legend

## How it works
Each algorithm is a JavaScript **generator** (`function*`). It sorts the array in place and `yield`s a small operation (compare, swap, write, mark sorted, pivot) after every change. One runner pulls operations from the generator with `gen.next()`:

- **Run:** keep calling `next()` at the chosen speed.
- **Pause:** stop calling it. The generator remembers where it was.
- **Step:** call `next()` once.
- **Cancel:** drop the generator and cancel the animation frame, so runs never overlap.

The visual code never touches the algorithms, and the algorithms know nothing about drawing.

## Tech stack
HTML, CSS and vanilla JavaScript in a single `index.html`. Canvas for drawing, Web Audio API for sound, Google Fonts (Inter). No frameworks, no build step.

## Run locally
1. Clone the repo:
   ```bash
   git clone https://github.com/subhanishat89-spec/sorting-visualizer.git
   cd sorting-visualizer
   ```
2. Open `index.html` in any modern browser.

## Complexity

| Algorithm | Best | Average | Worst | Space | Stable |
|---|---|---|---|---|---|
| Bubble | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Selection | O(n²) | O(n²) | O(n²) | O(1) | No |
| Insertion | O(n) | O(n²) | O(n²) | O(1) | Yes |
| Merge | O(n log n) | O(n log n) | O(n log n) | O(n) | Yes |
| Quick | O(n log n) | O(n log n) | O(n²) | O(log n) | No |
| Heap | O(n log n) | O(n log n) | O(n log n) | O(1) | No |

## Future improvements
- Race mode: two algorithms on the same array side by side
- More algorithms (Shell, Counting, Radix)
- Random or median-of-three pivot for Quick Sort
- Shareable links with the chosen settings

## Author
Nishat Subha
