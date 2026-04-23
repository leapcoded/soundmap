# Event Sound Mapper

A web-based tool for planning event sound systems. Visualize sound propagation, place speakers, barriers, and site elements to optimize audio coverage.

## Features

- Interactive canvas for placing sound sources and site elements
- Real-time sound level calculations with visual heatmaps
- Support for barriers, zones, and reflections
- Upload site maps as background images
- Export high-resolution PNG maps
- Undo/redo functionality

## Usage

1. Open the tool in your browser
2. Adjust the pixels per meter scale
3. Place speakers (🔊) and barriers (🧱)
4. Add site elements like stages, bars, camping areas, etc.
5. Upload a site map image if desired
6. View real-time dB levels as you move the mouse
7. Download your sound map as a PNG

## How It Works

The tool simulates sound propagation using:
- Inverse square law for distance attenuation
- Beam width restrictions for directional speakers
- Absorption and reflection calculations for barriers and zones
- Visual heatmaps showing dB levels across the site

## Browser Compatibility

Works in any modern web browser with HTML5 Canvas support.