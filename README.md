# Sleep & Lifestyle Data Preprocessing

Data preprocessing and exploratory analysis of a sleep and lifestyle health
dataset, plus text preprocessing on mental health statements.
Course project for DS2301 (Data Collection & Preprocessing),
Umm Al-Qura University, 2026.

## 🎯 Objective
Explore how daily habits, mainly exercise and caffeine intake, relate to
sleep efficiency, and prepare the data for modeling through a full
preprocessing pipeline.

## 📂 Datasets
- **Sleep & Lifestyle Health Dataset:** 1,000 records, 15 columns
  ([Kaggle](https://www.kaggle.com/datasets/shraddha4ever20/sleep-and-lifestyle-health-dataset))
- **Mental health statements (Combined Data):** 53,043 records,
  with a random sample of 20,000 used for text preprocessing

## 🔧 Pipeline

| Stage | What was done |
|---|---|
| Inspection | `head`, `shape`, `info`, `describe`, column renaming |
| Quality checks | Missing values, duplicates, label consistency, invalid ranges, data types |
| Cleaning | 256 missing caffeine values filled with the median (25 mg), Bedtime/WakeupTime converted to datetime, whitespace stripped |
| EDA | Groupby, pivot table, histogram, bar plot, correlation heatmap |
| Outliers | IQR method and boxplots: 0 outliers found |
| Scaling | Min-Max scaling and Standardization (Z-score) |
| Encoding | One-Hot, Label and Binary encoding |
| Feature engineering | `Sleep_Grade` (pd.cut), `Caffeine_Category`, pivot and melt |
| Feature selection | RFE with Linear Regression (top 5 features) |
| Dimensionality reduction | PCA on standardized features |
| Text preprocessing | Lowercasing, punctuation and stopword removal, tokenization, stemming, lemmatization, word frequency, word cloud |

## 📊 Key findings
- Sleep efficiency is nearly identical for females and males (about 0.72).
- The strongest correlation is between deep sleep and light sleep (r = -0.94),
  and REM and light sleep are negatively correlated (r = -0.31).
- Correlations of caffeine, alcohol and exercise with sleep efficiency are
  close to zero in this dataset.
- RFE selected: Gender, Sleep_Duration_Hours, Awakenings, SmokingStatus,
  ExerciseFrequency.
- PCA: PC1 explains 15.57% of the variance, PC2 8.90% and PC3 8.75%.
  The variance is spread across many components, so sleep quality
  is not driven by a single factor.
- Text analysis: the most frequent words are *like, feel, want, know, get,
  life*, which reflect first-person emotional language.

## ⚠️ Limitations
- Self-reported habits (caffeine, exercise) may contain recall bias.
- No timestamp for measurements, so no time-series analysis.
- Median imputation slightly compresses variance in caffeine values.

## 🛠️ Tools
Python, Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn,
category_encoders, NLTK, WordCloud, Google Colab

## 📁 Files
- `Code File (3).pdf`: full code with outputs
- `Lab_7.ipynb`: text preprocessing notebook

## 📌 Note
The datasets are not included in this repository. See the Kaggle link above.
