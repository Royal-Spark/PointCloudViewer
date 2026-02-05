# Point Cloud Viewer

A browser-based point cloud visualization tool designed for drone survey data. View LAS point clouds alongside geotagged imagery with camera position overlays in both 2D map and 3D views.

**[Live Demo](https://yourusername.github.io/pointcloud-viewer-gh/)** *(update with your URL)*

![Screenshot](screenshot.png)

## Features

- **LAS Point Cloud Support** - Load and visualize LAS 1.2-1.4 files with RGB or height-based coloring
- **Geotagged Image Integration** - Extract GPS coordinates and camera orientation from drone imagery (EXIF/XMP)
- **Dual View Modes**
  - **2D Map** - Satellite imagery with directional camera markers
  - **3D Point Cloud** - Interactive WebGL visualization with orbit controls
- **Camera Position Overlay** - See where photos were taken in 3D space
- **FOV Visualization** - Display camera field-of-view cones and highlight visible points
- **Mobile Optimized** - Touch-friendly interface designed for iPad Safari

## Supported Formats

### Point Clouds
- LAS 1.2, 1.3, 1.4
- Point formats 0-10
- RGB color data (when available)
- Automatic height-based coloring for non-RGB data

### Imagery
- JPEG with GPS EXIF data
- Supports DJI and Parrot drone metadata (XMP)
- Extracts: GPS position, altitude, yaw/pitch/roll

## Usage

### GitHub Pages Deployment

1. Fork or clone this repository
2. Go to repository **Settings** > **Pages**
3. Set source to **Deploy from a branch**
4. Select **main** branch and **/ (root)** folder
5. Access at `https://yourusername.github.io/repository-name/`

### Local Usage

Simply open `index.html` in a modern browser. No server required.

### Loading Data

1. **Drop images/video** into the first drop zone
2. **Drop a LAS file** into the second drop zone
3. Use the **2D MAP / 3D CLOUD** toggle to switch views
4. Click the **hamburger menu** to show/hide the sidebar on mobile

## Controls

### 3D View
- **Rotate** - Click and drag (or one-finger drag on touch)
- **Pan** - Right-click drag (or two-finger drag)
- **Zoom** - Scroll wheel (or pinch)

### Render Options
- Point size adjustment
- White points mode
- Grid and axes visibility
- Camera marker size
- FOV cone visualization
- Point highlighting within FOV

## Browser Support

| Browser | Status |
|---------|--------|
| Safari (iOS/iPadOS) | Fully supported |
| Chrome | Fully supported |
| Firefox | Fully supported |
| Edge | Fully supported |

**Note:** Requires WebGL 2.0 and ES6 module support.

## Technical Details

### Dependencies (loaded via CDN)
- [Three.js](https://threejs.org/) v0.160.0 - 3D rendering
- [Leaflet](https://leafletjs.com/) v1.9.4 - 2D mapping

### Coordinate Systems
- LAS files are expected in a projected coordinate system (e.g., UTM)
- GPS coordinates from images are converted to UTM for alignment
- Three.js uses: X = East, Y = Up, Z = South

### Performance
- Point clouds are downsampled to 3M points max for smooth rendering
- Efficient binary LAS parsing
- Object URL management for image previews

## File Structure

```
pointcloud-viewer-gh/
├── index.html      # Single-file application
└── README.md       # This file
```

## License

MIT License - Feel free to use, modify, and distribute.

## Acknowledgments

- Esri World Imagery for satellite basemap
- Three.js community for WebGL examples
- LAS specification by ASPRS
