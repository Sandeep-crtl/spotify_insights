# 🎧 Spotify Top-50 Global Analytics Dashboard  
### 📊 Power BI | DAX | Consumer Streaming Insights

---

## 🚀 Project Overview
This project analyzes **Spotify’s Top-50 Global chart data** using **Power BI** to uncover **popularity dynamics, artist dominance, content characteristics, and time-based trends**.  

The goal is not visualization for aesthetics, but **building a robust analytical model** that supports insight generation through **DAX-driven metrics**.

---

## 📁 Dataset Summary
| Attribute | Value |
|--------|-------|
| 📀 Dataset | Spotify Top-50 Global |
| 🧩 Granularity | One row per song per chart entry |
| 🎵 Distinct Songs | **789** |
| 🎤 Distinct Artists | **342** |
| ⭐ Avg Popularity | **~90** |
| ⏱ Avg Duration | **~3.28 min** |
| 🔞 Explicit Content | **~40%** |

---

## 🧠 Business Objectives
✔ Identify **concentration of popularity** across artists  
✔ Analyze **explicit vs non-explicit performance**  
✔ Track **monthly and yearly popularity trends**  
✔ Measure **artist consistency and chart dominance**  
✔ Build **scalable DAX measures** reusable across contexts  

---

## 📊 Dashboard Capabilities
### 🔹 Executive KPIs
- 🎵 Total Songs  
- 🎶 Distinct Songs  
- 🎤 Distinct Artists  
- ⭐ Avg / Min / Max Popularity  
- ⏱ Avg Track Duration  

### 🔹 Artist-Level Analysis
- Songs per artist  
- Average popularity by artist  
- #1 chart positions per artist  
- Dominance and repetition detection  

### 🔹 Content Insights
- 🔞 Explicit vs Clean song distribution  
- Popularity comparison by content type  

### 🔹 Time-Series Analysis
- 📆 Monthly and yearly popularity trends  
- 📈 Seasonality in song releases  
- Comparative year-over-year metrics  

### 🔹 Song-Level Rankings
- 🔝 Top songs by cumulative popularity  
- Duration and position correlation  

---

## 🧮 Core DAX Measures
```DAX
Total Songs =
COUNTROWS('Top-50-world')

Distinct Songs =
DISTINCTCOUNT('Top-50-world'[song])

Distinct Artists =
DISTINCTCOUNT('Top-50-world'[artist])

Avg Popularity =
AVERAGE('Top-50-world'[popularity])

Avg Duration (Minutes) =
AVERAGE('Top-50-world'[duration_ms]) / 60000

Explicit Songs =
CALCULATE(
    COUNTROWS('Top-50-world'),
    'Top-50-world'[is_explicit] = TRUE()
)

Pct Explicit Songs =
DIVIDE([Explicit Songs], [Total Songs], 0)
