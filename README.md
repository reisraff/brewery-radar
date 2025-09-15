# HopRadar

HopRadar is a lightweight single-page web app for exploring and comparing hop characteristics.  
It visualizes aroma and flavor attributes of hops (tea-like, citrus, herbal, fruity, etc.) on a **radar (spider) chart**, making it easy to compare two hops side by side.

## ✨ Features

- Interactive **radar chart** using [Chart.js](https://www.chartjs.org/).
- Select one hop for the **left side (blue)** and optionally another for the **right side (magenta)**.
- Built-in **dataset of international hops** (US, Germany, UK, Czech Republic, NZ, Australia, France, Spain, Argentina/Chile).
- Quick **search/filter** by name, country, or beer style.
- Clear **style and country metadata** shown for each selected hop.
- Entirely self-contained: **HTML, CSS, and JS in one file**.

## 📊 Dataset

The app ships with a curated CSV dataset of hops, including:
- **Origin country**
- **14 aroma attributes** (scored 0–10):
  - Tea, Citrus, Green, Caramel, Woody, Spicy, Menthol, Herbal, Vegetal, Floral, Green Fruit, Red Fruit, Yellow Fruit, Sweet Fruit
- **Recommended beer styles**

## 🚀 Getting Started

1. Clone or download this repository.
2. Open `lupulos.html` in your browser.
3. Use the left and right selectors (or the search bar) to choose hops and compare their profiles.

No build steps or dependencies are required — everything runs locally.

## 📷 Screenshot

*(Add a screenshot of the radar chart here once available)*

## 🛠 Tech

- **HTML5**  
- **CSS3** (responsive grid + dark theme)  
- **JavaScript**  
- **Chart.js** for radar visualization  

## 🔮 Roadmap Ideas

- Export comparison results as PNG or PDF.  
- Add user’s own hops via CSV upload.  
- Show aggregated flavor categories (e.g., “fruity” as sum of fruit attributes).  
- Style recommendations based on selected hops.  

## 📄 License

MIT License — free to use, modify, and share.
