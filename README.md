# Song Popularity Prediction Using Machine Learning Models

## Project Overview
This project was developed as part of the DSO 528 course at USC to help **Universal Music Group (UMG)** optimize song promotion strategies and identify trends in popular music. Using a historical Spotify dataset, we applied **exploratory data analysis (EDA)**, **data cleaning**, and **feature engineering** to uncover key patterns and trends. We built and evaluated multiple machine learning models to predict song popularity, focusing on maximizing net profit as the key performance indicator.

The **XGBoost model** emerged as the best-performing model, achieving a record profit of $91.86 million by leveraging a probability threshold of 0.08. We provided actionable recommendations for UMG, including insights into song production, playlist curation, and targeted marketing.

---

## Dataset
The dataset spans **2010–2020** and consists of **26,266 rows** representing individual tracks. Each track contains attributes like:
- **Track ID, Name, Artist**
- **Danceability, Energy, Tempo, Key, Genre**
- Target variable: `Popular` (binary indicator)

### Data Cleaning
The dataset contained anomalies and missing values:
1. **Duplicate Track IDs:** Represented as separate rows with different genres.
2. **Erroneous Release Years:** Values like `1905` and `0` were placeholder errors.
3. **January Bias:** Placeholder months for missing release dates.

### Steps Taken:
- Used **Spotify API** to fetch accurate metadata for tracks.
- Applied **one-hot encoding** for multiple genres per track.
- Engineered new columns for **date** (combining year and month) and **key_mode** (combining musical key and mode).
- Reduced the dataset to **22,944 rows** and **49 columns** after cleaning.

---

## Exploratory Data Analysis (EDA)
Key findings include:
- **Genres:** Pop is the most popular genre, followed by Latin, R&B, and Rap.
- **Features:** Popular tracks tend to have higher **danceability** and **speechiness** compared to unpopular tracks.
- **Artist Trends:** Artists like David Guetta have the most popular songs.
- **Time Trends:** Increasing danceability and speechiness in popular songs over time.

Visualizations such as correlation heatmaps and time series graphs helped uncover these trends.

---

## Machine Learning Models
We evaluated various models to predict song popularity, using a custom profit formula:
- **Profit per true positive (TP):** $120K
- **Loss per false positive (FP):** $10K

### Models Evaluated:
1. **Logistic Regression:** Baseline model, achieving $87.99M profit at a 0.07 threshold.
2. **Decision Tree:** Achieved $83.13M profit at a 0.0 threshold.
3. **Random Forest, Bagging, and Boosting:** Ensemble methods showed better performance.
4. **XGBoost (Best Model):**
   - **Profit:** $91.86M at 0.08 threshold.
   - **Recall:** 92.9%
   - **Precision:** 22.0%
5. **Neural Network:** Achieved $88.04M profit at 0.06 threshold.

The **XGBoost model** excelled in balancing recall (high sensitivity to hit songs) and precision (avoiding over-promotion of unpopular tracks).

---

## Recommendations for UMG
1. **Feature-Based Predictions:**
   - Use additional data like **streaming metrics** and **sentiment analysis**.
2. **Targeted Promotion:**
   - Prioritize tracks with high predicted popularity (e.g., regional campaigns for emerging artists).
3. **Playlist Curation:**
   - Curate playlists to highlight tracks with high danceability and energy.
4. **Collaboration Strategy:**
   - Recommend artist pairings based on audience overlap (e.g., emerging talents with top performers).

---

## Limitations & Next Steps
### Challenges:
1. **Dynamic Trends:** Reliance on historical data limits adaptability to future market trends.
2. **Artistic Creativity:** Model predictions supplement but cannot replace artistic intuition.

### Recommendations:
- **Retrain the model regularly** with updated data.
- Develop **region-specific models** for tailored strategies.
- Implement a **feedback loop** to refine predictions and strategies.

---

## Team Members
- Ethan Liu
- Jewel Ling
- Camilla Zhao
- Katherine Wang
- Tsubasa Lin
- Hanwei Chang

---

## Files Included
1. **EDA and Cleaning.ipynb:** Data preprocessing, cleaning, and feature engineering steps.
2. **Modeling.ipynb:** Model development, evaluation, and comparison.
3. **Presentation.pdf:** Summary of project findings and recommendations.
4. **Summary.pdf:** Detailed project report and executive summary.

---
