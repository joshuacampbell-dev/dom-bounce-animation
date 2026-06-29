# DOM Bounce Animation

A lightweight, zero-dependency vanilla JavaScript rendering loop demonstrating sub-pixel anti-aliasing and efficient viewport boundary management.

## Overview
This project is an exercise in managing state, dynamic viewport boundaries, and smooth 60FPS DOM manipulation without relying on external libraries or the HTML5 Canvas API.

## Key Technical Features
* **Hardware Acceleration:** Utilizes `will-change: transform` and `translate3d` to offload processing to the GPU and prevent main-thread blocking.
* **Performance Sync:** Implements `requestAnimationFrame` for screen-synchronized rendering at native refresh rates.
* **Sub-pixel Correction:** Applies coordinate rounding (`Math.round`) to eliminate visual shimmering and ghosting during high-contrast transitions.
* **Dynamic Boundaries:** Handles real-time window resizing to maintain mathematical collision integrity.
* **Asymmetric Trajectory:** Configured with 3:2 velocity vectors to generate a highly distributed, non-repeating path matrix.

## Asset Formatting & Setup
By default, the utility renders a responsive CSS-based shape fallback. To use a custom image asset:
1. Name your file `logo.png` and place it in the root directory.
2. **Critical:** Ensure the image asset is cropped tightly to the graphic. Any transparent padding in the PNG will be calculated as part of the physical bounding box, resulting in visually inaccurate boundary collisions.
3. The application will strictly enforce a 300x300 rendering dimension.

## License
Distributed under the MIT License.
