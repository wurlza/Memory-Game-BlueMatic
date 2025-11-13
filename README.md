# Memory Game - BlueMatic Technical Assessment

## Build Overview

This is an interactive HTML5 memory game built for programmatic display placements. The game features a tile-matching mechanic with smooth animations, performance optimizations, and accessibility features.

### Notable Decisions

1. **Pure HTML/CSS/JS Implementation**: No external libraries to keep the bundle size minimal
2. **CSS Grid for Layout**: Provides responsive tile arrangement across different ad sizes
3. **CSS Transforms for Animations**: Hardware-accelerated flip animations for smooth performance
4. **Accessibility Features**: Keyboard navigation, focus indicators, and semantic HTML
5. **Modular Game State**: Centralized state management for clean code structure


## Setting Clickthrough in GWD

To set the clickthrough URL in Google Web Designer:

1. Open the HTML file in GWD
2. Select the exit button element (with class `btn-exit`)
3. In the Properties panel, add a "Tap Area" component
4. Set the clickthrough URL in the Tap Area properties
5. The exit event will be automatically tracked via the `bm_exit_click` custom event

## Known Limitations

1. **Asset Size**: Current implementation uses emoji symbols instead of images to stay within file size limits
2. **Browser Support**: CSS Grid and transforms require modern browsers
3. **Mobile Performance**: Animation smoothness may vary on lower-end devices

## Analytics Events

The following custom events are dispatched:

- `bm_game_start`: When the first tile is flipped
- `bm_pair_match`: After each pair attempt with `{ pairsFound, attempts }` detail
- `bm_game_complete`: When all pairs are found with `{ attempts, timeMs }` detail
- `bm_exit_click`: When the exit CTA is clicked

## Preview Instructions

To preview locally:

1. Extract the ZIP file
2. Open any of the HTML files in a modern web browser
3. For best results, use a local server (e.g., `python -m http.server 8000`)

## Asset Sources

- Icons: Unicode emoji characters (license-free)
- Fonts: System fonts (Arial) for maximum compatibility
- Colors: Custom CSS gradients

## Performance Notes

- Initial load: ~15KB (well under 200KB limit)
- No external requests
- CSS animations optimized with `transform` and `opacity`
- Minimal DOM manipulations to prevent layout thrashing

Game Features

## Core Gameplay

Flip tiles to find matching pairs

Track attempts and completion time

Visual feedback with animations

Responsive design for 300x250, 300x600, 320x480

## Enhanced Features
3 Difficulty Levels: Easy (6 pairs), Medium (8 pairs), Hard (12 pairs)

Scoring System: Dynamic score based on time + attempts

Theme Toggle: Light/dark mode

Sound Controls: Toggle sound effects

Best Scores: Persistent storage per difficulty

Smooth Animations: Pulse, shake, and flip effects

Technical Implementation
Architecture
Pure HTML/CSS/JS - no external dependencies

CSS Grid for responsive layout

CSS Custom Properties for theming

Local Storage for best scores

Performance
CSS transforms for hardware acceleration

Minimal DOM manipulations

Optimized assets (emoji icons, placeholder sounds)

Initial load: ~20KB (under 200KB limit)

Accessibility
Full keyboard navigation (tab, enter, space)

Clear focus indicators

WCAG compliant contrast ratios

Semantic HTML structure

Setting Clickthrough in GWD
Open HTML in Google Web Designer

Select exit button (class btn-exit)

Add "Tap Area" component in Properties panel

Set clickthrough URL in Tap Area properties

Exit event automatically tracked via bm_exit_click

Analytics Events
All events use window.dispatchEvent(new CustomEvent(...)):

bm_game_start - First tile flip

bm_pair_match - After pair attempt
{ pairsFound: number, attempts: number }

bm_game_complete - All pairs found
{ attempts: number, timeMs: number, score: number }

bm_exit_click - Exit CTA clicked

Configuration
Difficulty Settings
Easy: 4×3 grid, 6 pairs

Medium: 4×4 grid, 8 pairs

Hard: 4×6 grid, 12 pairs

Game Parameters
Flip animation: 500ms

Mismatch display: 1000ms

Score: Time bonus + Attempt bonus

Browser Support
Chrome 60+

Firefox 55+

Safari 12+

Edge 79+

Known Limitations
Sound: Placeholder base64 audio - replace with optimized files in production

Icons: Using emoji instead of images for size constraints

Mobile: Animation performance may vary on low-end devices

Preview
Quick Start
Extract ZIP

Open HTML files directly in browser

Asset Sources
Icons: Unicode emoji (license-free)

Fonts: System fonts (Segoe UI, Tahoma)

Colors: Custom CSS gradients

Sounds: Placeholder - replace with licensed effects

Testing Checklist
Game loads in all three ad sizes

Smooth tile animations

Correct match detection

Timer starts on first flip

Game completion works

Analytics events fire

Keyboard navigation

Theme toggle

Sound toggle

Difficulty selection

Best scores persist

Responsive design

Stretch Goals Implemented
✅ Difficulty selector
✅ Sound effects with mute toggle
✅ Persistent best scores
✅ Color themes (dark/light)

