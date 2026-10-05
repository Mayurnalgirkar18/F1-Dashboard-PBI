# 🏎️ F1 Race Dashboard — Power BI

An interactive **three-page Formula 1 Race Dashboard** built in **Power BI** to analyze race results, driver performance, pit-stop behavior, speed, and team/driver points distribution.

The dashboard uses a **dark racing-themed UI** with interactive slicers, cross-filtering, page navigation, KPI cards, and tooltip pages.

> ⚠️ **Data Disclaimer:**
> This project uses a **synthetic / illustrative dataset** created for Power BI portfolio and learning purposes. It is **not official FIA or Formula 1 historical data** and should not be presented as real-world race results.

---

## 📸 Dashboard Preview

### 🏁 Race Overview

![Race Overview](images/race_overview.png)

### 👨‍🏎️ Drivers Performance

![Drivers Performance](images/drivers_performance.png)

### 📊 Race Analysis

![Race Analysis](images/race_analysis.png)

---

# 📑 Dashboard Pages

## 1. 🏁 Race Overview

Provides a high-level overview of the season and overall race performance.

### Slicers

* Grand Prix
* Circuit Name
* Country

### KPI Cards

* Total Races — 24
* Total Drivers — 20
* Total Points — ~2K
* Average Finish Points — 10.50
* Average Pit Stops — 2.34

### Visuals

* Grid Position vs Finish Position — scatter/bubble chart by driver
* Finish Position by Drivers — stacked column chart
* Top 10 Drivers by Points

### Example Top Drivers

| Driver          | Points |
| --------------- | -----: |
| Max Verstappen  |    383 |
| Carlos Sainz    |    336 |
| Lando Norris    |    308 |
| Charles Leclerc |    307 |

---

# 2. 👨‍🏎️ Drivers Performance

A driver-focused page designed to analyze individual performance across races.

### Slicers

* Driver Name
* Team
* Grand Prix

### KPI Cards

* Points
* Podiums
* Team
* Average Finish Position
* Nationality

### Visuals

* Points by Race — line chart
* Top Speed vs Fastest Lap Time — scatter chart
* Position Results — finishing-position frequency chart

### Example Driver Profile

**Carlos Sainz — Ferrari — Spain**

* **Points:** 336
* **Podiums:** 24
* **Average Finish Position:** 4.08

---

# 3. 📊 Race Analysis

Focuses on operational performance, pit-stop strategy, and team/driver points distribution.

### Slicers

* Grand Prix
* Circuit Name
* Country

### KPI Cards

* Fastest Lap Time — 1:18.1
* Top Speed — 354.90 km/h

### Visuals

* Pit Stops by Drivers — average pit stops
* Points Distribution by Team — donut chart
* Points Distribution by Driver — stacked bar chart

---

# 🔎 Tooltip & Drill-Through Pages

Additional pages were created to provide more detailed context when interacting with dashboard visuals.

### Tooltip Analysis

* Fastest Lap by Grand Prix
* Total Points by Team
* Drivers' Contribution to Total Points

These tooltip pages allow users to hover over visuals and quickly explore additional information without leaving the main dashboard.

---

# 🗂️ Data Model

The project follows a **star-schema style data model**, with `Race_Data` acting as the main fact table and supporting dimension tables providing driver, team, and race information.

### Source File

`F1_PowerBI_Dashboard_Data.xlsx`

| Sheet            | Rows | Description                        |
| ---------------- | ---: | ---------------------------------- |
| `Race_Data`      |  480 | Fact table — 24 races × 20 drivers |
| `Driver_Details` |   20 | Driver dimension                   |
| `Team_Details`   |   10 | Team dimension                     |
| `Race_Details`   |   24 | Race calendar                      |
| `Driver_Summary` |   20 | Pre-aggregated driver statistics   |
| `README`         |    — | Dataset notes                      |

---

## 🔗 Relationship

```text
Driver_Details[Driver_Name]
          │
          │ 1 : Many
          ▼
Race_Data[Driver_Name]
```

### Driver Images

Driver images can optionally be added using the `Image_URL` column in `Driver_Details`.

In Power BI:

**Column tools → Data category → Image URL**

---

# 📊 Race_Data Columns

The main `Race_Data` table contains the following fields:

```text
Season
Driver_Name
Car_Number
Nationality
Team
Round
Grand_Prix
Circuit_Name
Country
Grid_Position
Finish_Position
Positions_Gained_Lost
Points
Pit_Stops
Fastest_Lap
Fastest_Lap_Time_Sec
Top_Speed_Kmh
Status
```

---

# 💡 Key Business & Performance Insights

The dashboard is designed to demonstrate how race data can be converted into meaningful business and performance insights.

### Team & Strategy

* **Red Bull** remains a major commercial and competitive asset.
* **McLaren** shows strong growth and increasing competitive potential.
* **Ferrari** demonstrates high winning potential but inconsistent execution.
* **Mercedes** shows signs of competitive recovery.
* Driver concentration creates both **commercial value and performance risk**.
* Reliability can directly affect both **competitive results and financial performance**.
* Midfield teams need stronger strategies for converting opportunities into points.
* Position gains can reveal **strategic and operational strengths**.
* Pit-stop activity can be evaluated as a **cost-versus-performance metric**.
* Circuit-specific performance can help identify potential **sponsorship and commercial opportunities**.

---

# 👨‍🏎️ Driver Performance Snapshots

| Driver              | Key Takeaway                                                           |
| ------------------- | ---------------------------------------------------------------------- |
| **Max Verstappen**  | Consistent winner and strong recovery specialist                       |
| **Lando Norris**    | Breakout performer with multiple race wins                             |
| **Oscar Piastri**   | High-potential driver developing into a regular scorer                 |
| **Charles Leclerc** | Strong pace with inconsistent race execution                           |
| **Carlos Sainz**    | Strong race craft and position-gain specialist                         |
| **Lewis Hamilton**  | Resurgent form with strong commercial value                            |
| **George Russell**  | Consistent points contributor and team stabiliser                      |
| **Sergio Pérez**    | Occasional winner with inconsistent performance                        |
| **Fernando Alonso** | Midfield leader carrying a significant share of Aston Martin's results |

> **Note:** These insights are based on the synthetic dataset created for this portfolio project.

---

# 🛠️ Tools & Skills Demonstrated

### Power BI

* Data modelling
* DAX measures
* Power Query
* Star-schema modelling
* Data relationships
* Interactive dashboards
* Report design

### Data Visualization

* KPI Cards
* Scatter/Bubble Charts
* Line Charts
* Stacked Bar Charts
* Stacked Column Charts
* Donut Charts
* Pie Charts
* Tooltips
* Drill-through pages
* Slicers
* Cross-filtering

### Dashboard Design

* Dark racing-themed UI
* Custom background
* Page navigation buttons
* Interactive report navigation
* Business-style insight generation

---

# 🚀 How to Use

### 1. Clone the Repository

Clone or download this repository to your local machine.

### 2. Open the Power BI File

Open:

```text
F1_Race_Dashboard.pbix
```

using **Power BI Desktop**.

### 3. Update the Data Source

If Power BI asks for the dataset location:

**Home → Transform data → Data source settings**

Select the correct location of:

```text
F1_PowerBI_Dashboard_Data.xlsx
```

### 4. Refresh the Dataset

Click:

**Home → Refresh**

### 5. Explore the Dashboard

Use the slicers, navigation buttons, tooltips, and interactive visuals to explore the dataset.

---

# 📁 Project Structure

```text
F1-Race-Dashboard/
│
├── F1_Race_Dashboard.pbix
├── F1_PowerBI_Dashboard_Data.xlsx
├── f1.pdf
├── README.md
│
└── images/
    ├── race_overview.png
    ├── drivers_performance.png
    └── race_analysis.png
```

> Update the filenames above if your actual repository uses different names.

---

# 📌 Dataset Notes

* **Season:** 2024-style synthetic season
* **Rounds:** 24
* **Drivers:** 20
* **Teams:** 10
* **Race Records:** 480
* **Data Type:** Synthetic / illustrative
* **Purpose:** Power BI learning and portfolio demonstration

The numbers and driver/team performance shown in this dashboard are generated for this project and **do not represent official Formula 1 or FIA statistics**.

---

# 🎯 Project Objective

The primary objective of this project is to demonstrate the ability to transform structured race data into an **interactive business intelligence dashboard** using Power BI.

The dashboard combines:

**Data → Modelling → DAX → Visualization → Interactive Analysis → Business Insights**

---

## ⭐ Skills Demonstrated

**Power BI · Power Query · DAX · Data Modelling · Data Visualization · Dashboard Design · Data Analysis · Business Intelligence**

---

### 👨‍💻 Author

**Mayur Nalgirkar**

---

⭐ **If you find this project useful, consider giving the repository a star!**
