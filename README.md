# 🎓 Student Performance Analysis

> End-to-end Exploratory Data Analysis (EDA) on student academic performance using Python, Pandas, Seaborn, Matplotlib & Plotly.

---

## 📁 Project Structure

```
student-performance-analysis/
│
├── Student_Performance_Analysis.ipynb   ← Main Jupyter notebook
├── Student_performance_data___csv.xlsx  ← Dataset (place here)
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

| # | Chart Type | Topic |
|---|---|---|
| 1 | Histogram + KDE + Box Plot | GPA Distribution |
| 2 | Bar + Pie | Grade Class Proportions |
| 3 | Count + Violin | Gender vs GPA |
| 4 | Scatter + Regression | Study Time → GPA |
| 5 | Scatter + Hexbin Density | Absences → GPA |
| 6 | Box + Bar | Parental Support & Education |
| 7 | Multi-Bar + Strip | Extracurricular Activities |
| 8 | Bar + Horizontal Bar | Age & Ethnicity |
| 9 | Correlation Heatmap | All Features |
| 10 | Pair Plot | Study Time, Absences, GPA |
| 11 | Pivot Heatmap | Grade × Gender |
| 12 | Stacked Bar (%) | Parental Support × Grade |
| 13 | Interactive Scatter (Plotly) | Study Time vs GPA |
| 14 | Sunburst (Plotly) | Parental Education → Grade → Gender |
| 15 | Violin | Study Time by Grade |

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
