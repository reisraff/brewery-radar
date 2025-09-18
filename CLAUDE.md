# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Brewery Radar** is a comprehensive single-page web application for brewers and beer enthusiasts. It provides multiple tools for exploring hop and yeast profiles, brewing calculations, and beer parameter conversions. The entire application is contained within `index.html` - a self-contained file with embedded CSS and JavaScript.

## Architecture

**Single-File Architecture**: The app uses no build tools or dependencies beyond Chart.js CDN. Everything is contained in `index.html`:

- **HTML Structure**: Multi-panel layout with tool selector and context-specific interfaces
- **CSS Styling**: Dark theme with CSS custom properties, responsive grid layout with breakpoints
- **JavaScript Logic**: Multi-tool system with data parsing, chart management, calculations, and UI interactions
- **Data**: Two main datasets - hop characteristics (14 aroma attributes, chemical data) and yeast profiles (14 flavor attributes, fermentation specs)
- **Internationalization**: Full multilingual support (PT/EN/ES) with translation system

**Key Components**:
- Tool switching system with 6 main tools (lines 319-324)
- Dual CSV parsers for hops (line 1591) and yeast (line 1619) data
- Multiple Chart.js configurations for different visualizations
- Comprehensive calculation engines for brewing parameters
- Real-time filtering system for searchable datasets
- Language switching with localStorage persistence

## Available Tools

1. **Hop Radar** (`data-tool="hop"`): Compare two hops with aroma radar charts, chemical composition, and aromatic compounds
2. **Yeast Radar** (`data-tool="yeast"`): Compare two yeast strains with fermentation profile radar charts and specifications
3. **Density Converter** (`data-tool="converter"`): Convert between Plato/Brix and Specific Gravity
4. **ABV Calculator** (`data-tool="abv"`): Calculate alcohol content with hydrometer/refractometer methods
5. **Beer Color Converter** (`data-tool="color"`): Convert between Lovibond/SRM/EBC with visual beer glass rendering
6. **Pitch Rate Calculator** (`data-tool="pitch"`): Calculate yeast cell requirements for fermentation

## Development Commands

Since this is a static HTML file with no build process:

**Development**: Open `index.html` directly in a browser - no server required
**Testing**: Manual testing in browser (no automated test suite)
**Deployment**: Copy `index.html` to any web server or use as static file

## Key Data Structures

**Hops** (stored at line ~1324):
- Basic info: `nome` (name), `pais` (country), `Estilos` (recommended beer styles array)
- 14 aroma attributes (0-10 scale): Chá, Cítrico, Verde, Caramelado, Amadeirado, Picante, Mentolado, Herbal, Vegetal, Floral, Fruta Verde, Fruta Vermelha, Fruta Amarela, Fruta Doce
- Chemical data: Alpha acids (AA), Beta acids (BA), Essential oils, aromatic compounds (Myrcene, Humulene, etc.)

**Yeast** (stored at line ~1459):
- Basic info: `nome` (name), `pais` (country), `Tipos` (beer types array), `Fonte` (sources)
- 14 flavor attributes (0-10 scale): Frutal, Floral, Picante, Fenol, Ester, Limpo, Cremoso, Mineral, Alcoólico, Acidez, Complexo, Selva, Terroso, Doce
- Fermentation specs: ABV tolerance, temperature range

## Code Conventions

- Portuguese language for primary UI text and data labels
- CSS custom properties for theming (`--bg`, `--brand-left`, `--brand-right`, `--card`, `--muted`, etc.)
- Chart.js v4.4.3 via CDN for all visualizations
- Embedded CSV data parsing with quote handling for array fields
- Responsive design with multiple breakpoints (1200px, 980px, 768px, 480px, 360px)
- Tool-based architecture with show/hide sections
- Google Analytics integration (gtag)
- Country flag support via external flag API

## Common Modifications

**Adding New Hops**: Edit the CSV string starting at line ~1324
**Adding New Yeasts**: Edit the yeastCSV string starting at line ~1459
**Styling Changes**: Modify CSS custom properties in `:root` (lines 19-27)
**Adding New Languages**: Extend TRANSLATIONS object (line ~924) and update language selector
**Chart Configuration**: Update respective Chart.js options objects for each tool
**Tool Logic**: Modify calculation functions for converters and calculators
**Filtering Logic**: Update filter functions (applyLeftFilter, applyRightFilter, etc.)