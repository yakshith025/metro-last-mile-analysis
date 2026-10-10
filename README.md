# Metro Last-Mile Connectivity: Bengaluru, Delhi, Nagpur

How do metro passengers complete the first and last mile of their trip? This project analyses about **7,500 cleaned station-survey records across three Indian cities**. Python handles cleaning and station-level aggregation, QGIS the spatial maps, and Power BI an interactive dashboard.

## Key findings

| City | Walk share (last mile) | Auto share | Notes |
|---|---|---|---|
| Bengaluru | ~84% | ~12% | Longest last-mile times; peripheral stations have walk share below 25% |
| Delhi | 66–75% | 16–24% | Walkable core; the outer network depends on autos |
| Nagpur | ~77% | ~10% | Walkable even at 1 km |

- **500 m is the practical walking limit** in all three cities.
- **Recommendations:** pedestrian infrastructure within 500 m of stations, formal feeder services in Delhi and Bengaluru, and walkability-first design in emerging metro cities.

## Workflow

1. **Python:** clean the raw survey workbook, then analyse each city and aggregate to station level.
2. **QGIS:** join station summaries to metro station coordinates and map access modes and distances.
3. **Power BI:** interactive dashboard across the three cities.

## Repository structure

```
code/
├── 01_preprocess_survey.ipynb          initial cleaning
├── 02_bengaluru_analysis.ipynb         per-city cleaning + station aggregation
├── 03_delhi_analysis.ipynb
├── 04_nagpur_analysis.ipynb
└── 05_station_summary_for_qgis.ipynb   station-level summary for mapping
data/
├── raw/                                survey workbook + metro station coordinates
└── processed/                          cleaned surveys + station summaries per city
gis/                                    QGIS projects (bengaluru, delhi, nagpur .qgz)
dashboard/last_mile_dashboard.pbix      Power BI dashboard
report/
├── final_report.pdf (+ .docx source)
└── qgis_maps.pdf                       rendered maps
```

## Getting started

```bash
pip install -r requirements.txt
cd code
jupyter notebook
```

**Note:** the notebooks still use the absolute Windows paths from the original machine (`E:\aug-2025\...`). Change the paths at the top of each notebook to `../data/raw/` and `../data/processed/` before running. The QGIS projects use embedded memory layers; the rendered maps are in `report/qgis_maps.pdf`. The dashboard opens in Power BI Desktop.

## Team

SL 221 Introduction to Multimodal Mobility Systems, Indian Institute of Science (IISc), Sep 2025.
Revathy Ramesh, Yakshith Maddineni.
