# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

HopRadar is a single-page web application for exploring and comparing hop characteristics using radar charts. The entire application is contained within `index.html` - a self-contained file with embedded CSS and JavaScript.

## Architecture

**Single-File Architecture**: The app uses no build tools or dependencies beyond Chart.js CDN. Everything is contained in `index.html`:

- **HTML Structure**: Contains the layout with control panel (left) and chart panel (right)
- **CSS Styling**: Dark theme with CSS custom properties for colors and responsive grid layout
- **JavaScript Logic**: Data parsing, chart management, filtering, and UI interactions
- **Data**: Hop characteristics stored as embedded CSV string with 14 aroma attributes (0-10 scale)

**Key Components**:
- CSV parser for hop data (lines 206-232)
- Chart.js radar chart configuration (lines 280-335) 
- Filter system for searching hops by name/country/style (lines 263-272)
- Metadata display for selected hops (lines 245-252)

## Development Commands

Since this is a static HTML file with no build process:

**Development**: Open `index.html` directly in a browser - no server required
**Testing**: Manual testing in browser (no automated test suite)
**Deployment**: Copy `index.html` to any web server or use as static file

## Key Data Structure

Hops are stored with these properties:
- Basic info: `nome` (name), `pais` (country), `Estilos` (recommended beer styles array)
- 14 aroma attributes (0-10 scale): Chá, Cítrico, Verde, Caramelado, Amadeirado, Picante, Mentolado, Herbal, Vegetal, Floral, Fruta Verde, Fruta Vermelha, Fruta Amarela, Fruta Doce

## Code Conventions

- Portuguese language for UI text and comments
- CSS custom properties for theming (`--bg`, `--brand-left`, `--brand-right`, etc.)
- Chart.js v4.4.3 via CDN
- Embedded CSV data parsing with quote handling for beer styles field
- Responsive design with CSS Grid (320px sidebar, flexible chart area)

## Common Modifications

**Adding New Hops**: Edit the CSV string starting at line 147
**Styling Changes**: Modify CSS custom properties in `:root` (lines 10-18) 
**Chart Configuration**: Update Chart.js options object (lines 307-334)
**Filtering Logic**: Modify the `applyFilter()` function (lines 264-272)