# HuskyPath

HuskyPath is a UW campus navigation prototype for previewing walking routes between campus buildings. It uses a real OpenStreetMap base layer and pedestrian routing from Valhalla so route previews follow actual campus paths instead of a placeholder map.

## Features

- Selectable start and destination points around the UW Seattle campus
- Real OpenStreetMap rendering with campus markers
- Pedestrian route geometry and step-by-step directions
- Route options for fastest, accessible, and simpler walking paths
- Building details for hours, bathrooms, accessibility, and services
- Responsive UI based on the HuskyPath Figma direction

## How It Works

React owns the current start, destination, and route option. When those values change, the app sends the selected coordinates to Valhalla's pedestrian routing endpoint and stores the returned distance, duration, route shape, and directions. Leaflet then draws that shape on top of OpenStreetMap.

More detail is in [docs/architecture.md](docs/architecture.md).

## Local Development

```bash
npm install
npm run dev
```

## Checks

```bash
npm run lint
npm run build
```

## Deployment

The repository includes a GitHub Pages workflow. Pushes to `main` build the Vite app and publish the `dist` output.
