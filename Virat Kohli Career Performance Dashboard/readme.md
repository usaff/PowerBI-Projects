# 🏏 Virat Kohli Career Performance Dashboard

## 📌 Overview

This project is a **data-driven tribute** to **Virat Kohli**, one of the greatest cricketers of our time. The **Power BI dashboard** provides an in-depth analysis of his career, covering:

- Performance across formats (**T20, ODI, Test**)
- **Total runs, centuries, match-winning performances**
- **Records against different teams**
- **Yearly batting trends and consistency**

## 🔍 Questions This Dashboard Answers

1. **How has Virat Kohli performed over the years?** 📊
2. **Which teams has he performed best against?** 🏆
3. **What is his batting average across different formats?** ⚡
4. **How consistent has he been in scoring centuries and fifties?** 🔥
5. **What are his best performances year by year?** 📅
6. **How does he compare to other cricket legends?** 🏏
7. **Is he still maintaining his legendary form?** 🔄

---

## 🎯 Why This Project?

The inspiration for this project came from the **Asia Cup 2025**, where **India defeated Pakistan** in a high-intensity match. After the game, some critics questioned Kohli’s form. As a dedicated **Virat Kohli fan**, this dashboard was built to **showcase his legendary career using data-driven insights.**

![Virat Kohli](images/Virat_Kohli_Career_Performance_Dashboard.PNG)

---

## 🏆 Key Projects

### 🚀 Virat Kohli Career Dashboard

- **Role:** Data Analyst
- **Impact:** Designed an interactive Power BI dashboard that showcases Kohli’s performance trends.
- **Technologies:** Power BI, SQL, DAX
- **Achievements:**
  - Analyzed **50,000+ records** to extract key insights.
  - Developed **DAX measures** for calculating averages, strike rates, and centuries.
  - Created **interactive visualizations** for year-wise performance trends.

---

## 🛠️ Steps & DAX Calculations

### 📌 Step 1: Importing Data

- Imported match-by-match performance data from **ESPN Cricinfo** into Power BI.
- Cleaned and transformed the dataset using **Power Query**.

### 📅 Step 2: Creating a Calendar Table

```DAX
Calender = CALENDAR(
    DATE(YEAR(MIN(Virat_Kohli[date])), 1, 1),
    DATE(YEAR(MAX(Virat_Kohli[date])), 12, 31)
)
```

### 📆 Step 3: Creating Date Dimension Columns

```DAX
day = FORMAT(Calender[Date], "ddd") // Extracts Day Name (e.g., Mon, Tue)
day_no = DAY(Calender[Date]) // Extracts Day Number (1-31)
month = FORMAT(Calender[Date], "mmm") // Extracts Month Name (e.g., Jan, Feb)
month_no = MONTH(Calender[Date]) // Extracts Month Number (1-12)

```

### 📊 Step 4: Creating Key Performance Metrics

```100s = SUM(Virat_Kohli[100s])  // Total centuries scored
30+ = SUM(Virat_Kohli[30+])  // Matches where he scored 30+ runs
50s = SUM(Virat_Kohli[50s])  // Total half-centuries
HighestScore = MAX(Virat_Kohli[runs])  // Highest individual score
Runs = SUM(Virat_Kohli[runs])  // Total runs scored
Total_Matches = COUNT(Virat_Kohli[opponent])  // Total matches played
```

---

### 📊 Step 5: Insights & Visuals in Power BI

- Opponent vs Total Matches → Number of matches Kohli played against each team.
- Runs vs Opponent → Total runs scored against different teams.
- Yearly Runs Trend → Analyzes performance over time.
- KPI Cards → Displaying total runs, centuries, highest score, and matches played.
- Filters & Drill-Downs → Allows exploration by year, opponent, and format.

---

### 🚀 Future Enhancements

- Add Strike Rate & Batting Average trends 📈
- Introduce match-winning contributions analysis 🏆
- Implement player comparison with other legends 🔄
- Build predictive analytics for future performance 🔮

### IPL Performance Analysis

- **Impact:** Built a dashboard to analyze IPL players' performance.
- **Technologies:** Power BI, SQL
- **Achievements:**
  - Scraped data from ESPN Cricinfo.
  - Used **DAX calculations** for batting consistency metrics.
  - Provided **team-wise player insights**.

---

### 📢 Conclusion

This Power BI dashboard is a data-driven response to Virat Kohli’s critics, proving that his legacy is built on undeniable numbers. By visualizing his performances across formats, this project provides cricket fans and analysts a clear perspective on his impact in the game. 🔥🏏
