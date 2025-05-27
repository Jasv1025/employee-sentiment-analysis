# Employee Sentiment Analysis

This project analyzes internal communication messages to assess employee sentiment and engagement trends using natural language processing and statistical modeling.

## Project Objectives

- Label employee messages as **Positive**, **Negative**, or **Neutral**
- Perform **Exploratory Data Analysis (EDA)** to understand sentiment distribution and messaging patterns
- Calculate **monthly sentiment scores** for each employee
- Identify **top-performing and at-risk employees**
- Build a **linear regression model** to analyze sentiment trends

---

## Folder Structure

```
employee-sentiment-analysis/
│
├── data/
│   ├── test.csv
│   ├── labeled_test.csv
│   ├── monthly_scores.csv
│   ├── monthly_rankings.csv
│   └── flight_risks.csv
│
├── visualizations/
│   ├── sentiment_distribution.png
│   └── messages_by_month.png
│
├── sentiment_analysis.ipynb
├── requirements.txt
└── README.md
```

---

## Setup Instructions

1. Clone the repository and navigate into the project folder
2. Create a virtual environment (optional but recommended)
3. Install required dependencies:

```bash
pip install -r requirements.txt
```

4. Run the notebook:

```bash
jupyter notebook sentiment_analysis.ipynb
```

---

## Methodology Summary

### Sentiment Labeling
Used **TextBlob** to classify email body text into:
- Positive (`polarity ≥ 0.1`)
- Negative (`polarity ≤ -0.1`)
- Neutral (otherwise)

### EDA

I performed detailed EDA to understand messaging behavior and sentiment dynamics. This included:

- **Sentiment Distribution:** Count of positive, negative, and neutral messages
- **Message Volume Trends:** Messages per month over time
- **Message Length Analysis:** Histogram and boxplot of message lengths across sentiment classes
- **Employee Activity:** Top 10 most active employees by message volume
- **Monthly Sentiment Breakdown:** Stacked bar chart showing sentiment shifts over time
- **Negative Message Heatmap:** Employee vs. month matrix for frequency of negative messages
- **Missing Data Summary:** Visualization of null counts per field (if applicable)

### Monthly Scoring
Each message scored as:
- `+1` for Positive
- `0` for Neutral
- `–1` for Negative  
Scores aggregated monthly by employee.

### Employee Ranking
For each month:
- Top 3 most positive employees
- Top 3 most negative employees  
Saved to `monthly_rankings.csv`.

### Flight Risk Identification
Flagged employees with **≥4 negative messages in any rolling 30-day window**.  
Result saved to `flight_risks.csv`.

### Predictive Modeling
Built a **linear regression model** using `month_num` to predict sentiment trends over time.  
Evaluated with R² and MSE metrics.

---

## Deliverables

- `sentiment_analysis.ipynb`: Full code and commentary
- `README.md`: This file
- `requirements.txt`: Python dependencies
- `data/`: Raw and processed datasets
- `visualizations/`: Key plots

---

## Contact

Prepared by: **[James Alvin Simmons V]**  
Email: **[Jasv1025@gmail.com]**