# SPL Architect

A robust, browser-based 2D acoustic modelling and site planning tool designed for outdoor events, festivals, and temporary site designs. It provides real-time sound pressure level (SPL) heatmaps and scheduling overlays to assist in noise management, site layout, and barrier placement.

## Features

### Acoustic Modelling

The application allows users to define source parameters including speaker positions, peak SPL, dispersion angles, bass bias, and mounting heights. Environmental factors can be controlled globally, with settings for wind speed, wind direction, baseline noise floor, and ground surface type to calculate ground reflection and attenuation. Users can visualise sound propagation across Broadband, Low, Mid, and High frequency bands, incorporating frequency-specific air absorption. The tool uses the Maekawa formula to calculate insertion loss and diffraction over physical barriers based on the relative heights of the source and the obstacle. Additionally, zones and barriers have customisable absorption and reflection coefficients to approximate real-world materials like fabric, metal, wood, or crowds.

### Site Mapping & Layout

Site mapping integrates a built-in Leaflet map with Esri World Imagery tiles, allowing users to search for real-world locations and automatically sync the application scale to the map zoom level. Alternatively, custom site plan images can be uploaded with adjustable opacity behind the acoustic heatmap. Users can drag and drop functional zoning tools to define areas such as stages, camping, or dancefloors. Certain zones, like canopies, are treated as acoustically transparent, while custom exclusion zones block heatmap rendering entirely. An interactive ruler tool is also included to measure precise distances across the canvas.

### State & Export

The tool generates a presentation-ready, high-resolution PNG export of the site plan, which includes a trimmed satellite backdrop, heatmap, legend, and a compiled schedule table detailing SPL readings at every defined zone. Project management is handled via local JSON files for saving and loading site states. A complete undo and redo stack is maintained for non-destructive editing throughout the session.

## Technical Implementation

The application is built entirely in vanilla tech, requiring no build steps, bundlers, or backend infrastructure. The core consists of a single HTML file containing all CSS and JavaScript. Rendering is handled by the native HTML5 Canvas API, which manages the grid, items, heatmap calculations, and final PNG composition. Leaflet.js is used exclusively for handling the interactive map layer and querying geographic bounding boxes, while custom CSS variables ensure seamless dark and light mode switching.

## Usage

To use the application, open the HTML file in any modern web browser. Begin by setting the map and scale via the satellite location search or by uploading an image and using the scale slider. Place acoustic sources using the speaker tool and adjust their individual properties in the inspector. Draw zones to define specific site areas and view estimated SPL readings in the schedule panel. Place barriers like Heras panels or hay bales between noise sources and sensitive zones to observe diffraction and insertion loss. Finally, export the project to generate a clean PNG of the plan for documentation.

## File Structure

All logic, styling, and markup are self-contained within the main HTML file. The document is divided into specific sections managing constants, material presets, UI configurations, and central state. Core acoustic calculation engines handle the inverse square law, Maekawa formulas, and atmospheric absorption. Dedicated sections manage the Canvas drawing loops for the active workspace, the heatmap offscreen buffer, Leaflet tile coordinate mathematics, JSON persistence, and the high-resolution Canvas generation for PNG export.
