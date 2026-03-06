# 🎓 Student Performance Analysis

> End-to-end Exploratory Data Analysis (EDA) on student academic performance using Python, Pandas, Seaborn, Matplotlib & Plotly.

---

## 📁 Project Structure

```
student-performance-analysis/
│
├── Student_Performance_Analysis.ipynb   ← Main Jupyter notebook
├── Student_performance_data.xlsx  ← Dataset (place here)
├── requirements.txt                     ← Python dependencies
└── README.md
```

---

## 📊 Dataset Overview

| Feature | Description |
|---|---|
| `Age` | Student age (15–18) |
| `Gender` | 0 = Male, 1 = Female |
| `Ethnicity` | 0=Caucasian, 1=African Am., 2=Asian, 3=Other |
| `ParentalEducation` | 0=None → 4=Higher |
| `StudyTimeWeekly` | Weekly study hours (continuous) |
| `Absences` | Annual absences count |
| `Tutoring` | 0=No, 1=Yes |
| `ParentalSupport` | 0=None → 4=Very High |
| `Extracurricular / Sports / Music / Volunteering` | Binary participation flags |
| `GPA` | Grade Point Average (0.0 – 4.0) |
| `GradeClass` | 0=A, 1=B, 2=C, 3=D, 4=F |

**999 records × 15 columns**

---

## 🧪 Analysis Pipeline

```
1. Import Libraries
2. Load Dataset (.xlsx)
3. Data Inspection  →  df.info(), df.describe(), column catalogue
4. Data Cleaning    →  missing values, duplicates, drop StudentID, encode labels
5. EDA (15 charts)
6. Key Findings & Insights
7. Conclusion
```

---

## 📈 Charts Included

---

### Chart 1 — GPA Distribution (Histogram + KDE + Box Plot)
![GPA Distribution]<img width="1656" height="612" alt="image" src="https://github.com/user-attachments/assets/4c25be4c-694a-44c4-8018-10d2b717d30e" />

> Shows the overall spread of student GPAs. The histogram with KDE curve reveals a roughly uniform distribution with mean ≈ 1.90 and median ≈ 1.92. The box plot highlights the interquartile range (IQR: ~1.2 – 2.6) and confirms no extreme outliers, though GPAs span the full 0–4 range.

---

### Chart 2 — Grade Class Distribution (Bar + Pie)
![Grade Class Distribution](charts/chart_02_grade_class.png)
> Reveals a heavily skewed grade landscape — **52.2% of students score an F**, while only 3.1% achieve an A. The bar and pie charts together make it immediately clear that the majority of students are underperforming, signaling a systemic issue worth addressing.

---

### Chart 3 — Gender Analysis (Count + Violin)
![Gender Analysis](charts/chart_03_gender.png)
> Compares the 482 male and 517 female students. The violin plots show nearly identical GPA distributions for both genders, confirming that **gender has minimal impact on academic performance** in this dataset. The shape of both violins is wide in the mid-range, reflecting the high concentration of Grades C–F.

---

### Chart 4 — Study Time vs GPA (Scatter + Regression)
![Study Time vs GPA](charts/chart_04_study_time.png)
> The left scatter plot color-codes students by grade, showing clear vertical bands (Grade A at the top, F at the bottom) regardless of study hours. The regression line (r = 0.192) shows a **modest positive relationship** — more study time helps, but is not the dominant factor compared to absences.

---

### Chart 5 — Absences vs GPA (Scatter + Hexbin Density)
![Absences Impact](charts/chart_05_absences.png)
> The most striking chart in the project. With **r = −0.922**, absences are overwhelmingly the strongest predictor of GPA. As absences increase from 0 to 30, GPA drops almost linearly from ~3.5 to ~0.5. The hexbin density plot confirms the high concentration of students along this negative diagonal trend.

---

### Chart 6 — Parental Influence (Box + Bar)
![Parental Influence](charts/chart_06_parental.png)
> Box plots show a clear upward shift in GPA as parental support increases from None → Very High. The bar chart on parental education shows that students with parents having **no formal education** actually score slightly higher mean GPAs than those with bachelor's or higher degrees — suggesting parental presence matters more than parental education level.

---

### Chart 7 — Extracurricular Activities (Multi-Bar + Strip)
![Extracurricular Activities](charts/chart_07_activities.png)
> Compares mean GPA across 5 activities for participants vs non-participants. **Tutoring has the highest positive impact** (2.09 vs 1.82), while Sports and Volunteering show negligible differences. The strip plot on the right confirms that extracurricular participants (1) are spread across all GPA ranges, similar to non-participants.

---

### Chart 8 — Demographic Analysis (Age + Ethnicity)
![Demographics](charts/chart_08_demographics.png)
> Age 18 has the most students (280), while all age groups (15–18) are relatively balanced. For ethnicity, **African American students show the highest mean GPA (2.06)**, while all four ethnic groups sit within a very narrow range (1.84–2.06), suggesting ethnicity has minimal practical impact on GPA in this dataset.

---

### Chart 9 — Feature Correlation Heatmap
![Correlation Heatmap](charts/chart_09_correlation.png)
> A lower-triangle heatmap of all 13 numeric features. The two standout correlations are **Absences ↔ GPA (−0.92)** and **Absences ↔ GradeClass (+0.83)** — confirming attendance as the dominant academic driver. StudyTimeWeekly shows a weak positive correlation with GPA (0.19). Most other features show near-zero correlations with each other.

---

### Chart 10 — Pair Plot (Study Time, Absences & GPA by Grade)
![Pair Plot](charts/chart_10_pairplot.png)
> A corner pair plot with KDE diagonals and scatter off-diagonals, colored by grade. The **Absences vs GPA** panel shows perfect grade-band separation — each grade occupies a distinct diagonal strip. The **StudyTimeWeekly vs Absences** panel shows no relationship, confirming these are independent variables.

---

### Chart 11 — Pivot Heatmap (Grade × Gender)
![Pivot Heatmap](charts/chart_11_pivot_heatmap.png)
> A green-to-red heatmap showing mean GPA for each Grade × Gender combination. Female and Male students show virtually identical GPAs within every grade class (e.g., A: Female 3.67 vs Male 3.68; F: Female 1.19 vs Male 1.15), further confirming that **gender does not meaningfully differentiate academic performance**.

---

### Chart 12 — Stacked Bar: Parental Support × Grade Class (%)
![Stacked Bar](charts/chart_12_stacked_bar.png)
> Shows grade composition as a percentage within each parental support level. Students with **"Very High" parental support** have the largest share of A and B grades and the smallest proportion of F grades. Conversely, students with **"None"** support have the highest F proportion (~70%), making parental support one of the clearest levers for grade improvement.

---

### Chart 13 — Interactive Scatter: Study Time vs GPA (Plotly)
![Interactive Scatter](charts/chart_13_plotly_scatter.png)
> An interactive Plotly chart where each dot is colored by grade class and hoverable for student details (Age, Gender, Absences, Parental Support). The horizontal banding by grade is clearly visible — students within each grade maintain a consistent GPA range regardless of study hours, further reinforcing that **absences override study time** as the dominant factor.

---

### Chart 14 — Sunburst: Parental Education → Grade → Gender (Plotly)
![Sunburst](charts/chart_14_sunburst.png)
> A three-level interactive sunburst chart. The inner ring shows parental education levels, the middle ring shows grade distribution within each education group, and the outer ring breaks down by gender. **"Some College" and "High School"** are the largest parent education groups, and within every education level, Grade F dominates — reinforcing that parental education alone doesn't prevent poor grades.

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/student-performance-analysis.git
cd student-performance-analysis
```

### 2. Create a virtual environment (recommended)
```bash
python -m venv venv
source venv/bin/activate        # macOS / Linux
venv\Scripts\activate           # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter
```bash
jupyter lab
# or
jupyter notebook
```

### 5. Open the notebook
Open `Student_Performance_Analysis.ipynb` and run all cells (`Kernel → Restart & Run All`).

---

## 💡 Key Findings

- 📉 **Absences** have the strongest negative correlation with GPA (r ≈ −0.92)
- 📚 **Study time** is the strongest positive driver (r ≈ +0.18)
- 👨‍👩‍👧 **Parental support** consistently linked to higher grade classes
- 🎓 **Tutoring** raises performance even for students who start lower
- 👦👧 **Gender** difference in GPA is minimal overall

---

## 🛠 Tech Stack

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-2.0-green)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12-orange)
![Plotly](https://img.shields.io/badge/Plotly-5.x-purple)
![Jupyter](https://img.shields.io/badge/Jupyter-Lab-orange)

---

## 📄 License

MIT License — free to use, modify, and share.
