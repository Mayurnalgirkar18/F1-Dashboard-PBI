## 🏎️ F1 Race Dashboard — Power BI

An interactive, three-page Power BI dashboard that analyses a 2024-style Formula 1 season: race results, driver performance, pit-stop behaviour, speed and team points distribution.

Faster Together — dark, racing-themed UI with page navigation buttons, slicers and cross-filtering visuals.

##⚠️ Data disclaimer: The dataset is synthetic / illustrative, built for Power BI portfolio practice. It is not official FIA / Formula 1 historical data and should not be presented as real race results.

📸 Dashboard Preview
Race Overview	Drivers Performance	Race Analysis
Show Image	Show Image	Show Image

Save your screenshots in an images/ folder using the filenames above (or update the paths).

📑 Dashboard Pages
1. Race Overview

High-level season summary.

Slicers: Grand Prix, Circuit Name, Country
KPI cards: Total Races (24), Total Drivers (20), Total Points (~2K), Average Finish Points (10.50), Average Pit Stops (2.34)
Visuals:
Grid Position vs Finish Position (bubble/scatter by driver, sized by points)
Finish by Drivers (stacked column by finishing position)
Drivers Points (Top 10) — Max Verstappen leads with 383 pts, followed by Carlos Sainz (336), Lando Norris (308) and Charles Leclerc (307)
2. Drivers Performance

Driver-level drill-down.

Slicers: Driver Name, Team, Grand Prix
KPI cards: Points, Podiums, Team, Average Finish Position, Nationality
Visuals:
Points by Race (line chart)
Top Speed vs Time (scatter, km/h)
Position Results (column chart of finishing-position frequency)
Example (Carlos Sainz, Ferrari, Spain): 336 pts · 24 podiums · avg. finish 4.08
3. Race Analysis

Operational and team-level view.

Slicers: Grand Prix, Circuit Name, Country
KPI cards: First Fastest Lap Time (1:18.1), Top Speed (354.90 km/h)
Visuals:
Pit Stops by Drivers (average pit stops, bar chart)
Points Distribution by team (donut chart)
Points Distribution by driver (stacked bar)
Tooltip / Drill-through Pages

Additional hover pages for richer context:

Fastest lap by Grand Prix
Total points by team
Drivers' contribution to total points (pie chart)
🗂️ Data Model

Source file: F1_PowerBI_Dashboard_Data.xlsx

Sheet	Rows	Description
Race_Data	480	Fact table — 24 races × 20 drivers
Driver_Details	20	Driver dimension (slicers and profile cards)
Team_Details	10	Team dimension (base country, display name)
Race_Details	24	Race calendar (round, Grand Prix, circuit, country)
Driver_Summary	20	Pre-aggregated per-driver stats
README	—	Notes included in the workbook
Race_Data columns

Season, Driver_Name, Car_Number, Nationality, Team, Round, Grand_Prix, Circuit_Name, Country, Grid_Position, Finish_Position, Positions_Gained_Lost, Points, Pit_Stops, Fastest_Lap, Fastest_Lap_Time_Sec, Top_Speed_Kmh, Status

Relationship
Driver_Details[Driver_Name] (1) ───► Race_Data[Driver_Name] (many)

Driver images (optional): paste direct image URLs into Driver_Details[Image_URL], then set Data category → Image URL in Power BI.

💡 Key Insights

Team & strategy

Red Bull remains a major commercial asset
McLaren is the strongest growth story
Ferrari has high winning potential but uneven execution
Mercedes shows signs of recovery
Driver concentration creates both value and risk
Reliability is a direct financial and competitive issue
Midfield teams need stronger conversion strategies
Position gains reveal strategic and operational strength
Pit-stop activity should be treated as a cost-performance metric
Circuit-specific performance creates sponsorship opportunities

Driver snapshots

Driver	Takeaway
Max Verstappen	Consistent winner and recovery specialist
Lando Norris	Breakout star with multiple race wins
Oscar Piastri	High-potential rookie turning into regular scorer
Charles Leclerc	Fast but inconsistent race execution
Carlos Sainz	Strong race craft and position-gain specialist
Lewis Hamilton	Resurgent form with high commercial value
George Russell	Steady points contributor and team stabiliser
Sergio Pérez	Occasional winner but inconsistent season
Fernando Alonso	Midfield leader carrying Aston Martin's results

🛠️ Tools & Skills Demonstrated
Power BI Desktop — data modelling, DAX measures, report design
Star-schema relationships (dimension → fact)
Slicers, bookmarks / page navigation buttons, tooltips
KPI cards, scatter/bubble, line, stacked bar/column, donut and pie charts
Custom dark theme and background design
Business-style insight writing from visual analysis
🚀 How to Use
Clone or download this repository.
Open the .pbix file in Power BI Desktop.
If prompted, update the data source path: Home → Transform data → Data source settings and point it to F1_PowerBI_Dashboard_Data.xlsx.
Click Refresh, then explore using the slicers and navigation buttons.
├── F1_Race_Dashboard.pbix
├── F1_PowerBI_Dashboard_Data.xlsx
├── images/
│   ├── race_overview.png
│   ├── drivers_performance.png
│   └── race_analysis.png
├── f1.pdf
└── README.md

(Adjust file names to match your repository.)

📌 Notes
Dataset covers Season 2024: 24 rounds, 20 drivers, 10 teams.
Figures shown in the dashboard come from the generated dataset and will differ from real-world F1 results.
