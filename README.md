<div align="center">

<img src="https://images.plot.ly/logo/new-branding/plotly-logo-01-stripe.png" width="300" alt="Plotly Logo"/>

# 📈 60-Day Plotly Challenge

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-5.x-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Dash](https://img.shields.io/badge/Dash-2.x-00B4D8?style=for-the-badge&logo=plotly&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Status](https://img.shields.io/badge/Challenge-Day%2001%20✓-22C55E?style=for-the-badge)

> *"Most people skim tutorials and wonder why nothing sticks. I'm doing this differently — 60 days of going deep into Plotly from the inside out. Building real intuition, not just syntax familiarity."*

</div>

---

## 🎯 The Challenge

This repository documents my **60-day deep-dive into Plotly** — built entirely from official documentation, no watered-down tutorials. Each day is a Jupyter notebook that explores a concept hands-on, from first principles.

| # | Principle | Description |
|---|-----------|-------------|
| 1 | **Learn from the source** | Official docs only — no shortcuts |
| 2 | **Build notes from scratch** | Personal Jupyter notebooks for every concept |
| 3 | **Implement everything hands-on** | If I learn it, I build it |
| 4 | **Share progress publicly** | Accountability through visibility |

---

## 📘 Day 01 — The Figure Data Structure

### Core Concept

A Plotly figure is simply a **structured object** — a nested dictionary converted to JSON and rendered by `Plotly.js` behind the scenes. No direct JavaScript required.

```python
Figure = {
    'data':   [...],   # What to draw (traces)
    'layout': {...},   # How it looks (styling, axes, annotations)
    'frames': [...]    # Animation states
}
```

---

## 📚 What This Notebook Covers

| # | Topic | Key Takeaway |
|---|-------|-------------|
| 1 | **Overview & Setup** | Import `plotly.express`, `graph_objects`, `dash`; configure defaults |
| 2 | **Figures in Dash** | Pass Plotly figures into `dcc.Graph()` to build interactive web apps in Python |
| 3 | **Figures as Attribute Trees** | Every figure is a nested dict — access via paths like `layout.title.text` |
| 4 | **The `data` Attribute** | A list of traces; each trace is one visual layer (scatter, bar, pie, etc.) |
| 5 | **The `layout` Attribute** | Controls everything non-data: axes, fonts, margins, annotations, buttons |
| 6 | **The `frames` Attribute** | Enables animations — each frame is a new data state |
| 7 | **The `config` Object** | Runtime UI/UX settings: modebar, scroll zoom, export format |
| 8 | **Coordinate Systems** | Paper / Container / Axis Domain — three ways to position elements |
| 9 | **2D Cartesian Subplots** | Scatter, Bar, Histogram, Box — the foundation of most charts |
| 10 | **3D, Polar, Ternary & Smith** | `scene`, `polar`, `ternary` coordinate systems + Surface, Mesh3d, Cone, Volume |
| 11 | **Map Trace Types** | Geo subplots (outline maps) vs Tile maps (Mapbox, interactive) |
| 12 | **Self-Contained Subplots** | Pie, Indicator, Sunburst — traces that don't use x/y axes |
| 13 | **Carpet Trace Types** | Custom skewed/curved coordinate systems with `Carpet` + `Scattercarpet` |
| 14 | **Legends & Color Bars** | Discrete legends for categories; continuous color bars for numeric scales |
| 15 | **What About Dash?** | Turn any Plotly figure into a full interactive web application |

---

## 🧠 Key Mental Models Built

### The 3-Layer Figure Model
```
data    →  WHAT to draw   (traces: scatter, bar, surface, geo...)
layout  →  HOW it looks   (axes, title, colors, annotations, buttons)
frames  →  WHEN it changes (animation states)
config  →  HOW users interact (toolbar, zoom, export)
```

### Coordinate Systems at a Glance
| System | Range | Best Used For |
|--------|-------|---------------|
| **Paper** | `0.0 → 1.0` (plot area) | Fixed labels, watermarks, legends |
| **Container** | `0.0 → 1.0` (full figure incl. margins) | Title positioning |
| **Axis Domain** | `0.0 → 1.0` (per axis) | Subplot-aware annotations |

### Trace → Subplot Mapping
| Trace Type | Subplot Attribute | Example |
|------------|-------------------|---------|
| Scatter, Bar, Histogram | `xaxis` / `yaxis` | Standard 2D charts |
| Scatter3d, Surface | `scene` | 3D visualizations |
| Scatterpolar | `polar` | Radar charts |
| Scattergeo, Choropleth | `geo` | Outline maps |
| Scattermap | `map` | Mapbox tile maps |
| Pie, Indicator | `domain` | Self-contained subplots |

---

## 🗂️ Repository Structure

```
60-day-plotly-challenge/
│
├── 01_figure_structure.ipynb    ← Day 01 (this notebook)
├── README.md
└── ...                          ← Days 02–60 coming soon
```

---

## ⚙️ Setup & Usage

### Prerequisites
```bash
pip install plotly dash numpy
```

### Run the Notebook
```bash
jupyter notebook 01_figure_structure.ipynb
```

### Quick Start — Your First Figure
```python
import plotly.express as px

fig = px.line(x=['Jan', 'Feb', 'Mar', 'Apr'], y=[4, 5, 7, 8], title="Sample Figure")
fig.show()
```

---

## 🗺️ Full 60-Day Roadmap

```
Phase 1 — Fundamentals     Days 01–10   Figure internals, Plotly Express, Graph Objects
Phase 2 — Chart Mastery    Days 11–25   Statistical charts, Scientific viz, 3D visualizations
Phase 3 — Advanced         Days 26–40   Animations, Subplots, Maps, Custom themes
Phase 4 — Real Projects    Days 41–55   Dashboards, real-world datasets
Phase 5 — Deep Mastery     Days 56–60   Performance, publishing, custom components
```

Topics covered across the challenge:

`Figure internals` · `Plotly Express` · `Graph Objects` · `Statistical charts` · `Scientific viz` · `3D visualizations` · `Animations` · `Subplots` · `Real-world projects`

---

## 📌 Day 01 — Key Takeaways

- A Plotly figure is just a **nested dictionary** rendered as JSON by Plotly.js
- `data` holds traces (what to draw), `layout` controls appearance, `frames` enable animation
- `config` controls runtime interactivity — zoom, toolbar, export settings
- Every trace type connects to a specific subplot system via a single attribute
- Dash converts any Plotly figure into a **full interactive web application** in pure Python

---

## 🏷️ Tags

`#Plotly` · `#DataVisualization` · `#Python` · `#DataScience` · `#LearningInPublic` · `#60DayChallenge` · `#Jupyter`

---

<div align="center">



Made with 🔥 by [Yash Brahmankar](https://github.com/loisekk)

</div>
