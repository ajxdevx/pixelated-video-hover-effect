# Pixelated Video Hover Effect

A full-screen video hero with an interactive pixelated grid deformation effect. Moving the cursor distorts the video with chromatic aberration using a custom Three.js shader.

**Author:** AJ  
**By:** [anassjid](https://github.com/ajxdevx)

## Preview

Hover over the hero section to see the grid warp and RGB channels split slightly for a glitch-style look.

## Tech Stack

| Package | Version |
|---------|---------|
| [three](https://threejs.org/) | 0.185.0 |
| [vite](https://vite.dev/) | 8.1.0 |

## Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/) (v18 or newer recommended)
- A video file named `hero-footage.mp4` in the project root

### Install

```bash
npm install
```

### Run locally

```bash
npm run dev
```

Open the URL shown in the terminal (usually `http://localhost:5173`).

## Project Structure

```
├── index.html      # Page markup and video element
├── script.js       # Three.js scene, shader, and mouse interaction
├── styles.css      # Layout and hidden scrollbar
├── hero-footage.mp4
└── package.json
```

## How It Works

1. A background `<video>` is sampled into a `VideoTexture`.
2. Mouse velocity drives a floating-point data texture that stores per-cell offsets.
3. A fragment shader reads those offsets to displace UV sampling and apply chromatic aberration.
4. The grid relaxes over time so the effect smoothly returns to rest.

## License

ISC
