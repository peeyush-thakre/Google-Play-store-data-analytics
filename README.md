# 📱 Google Play Store Data Analysis

An end-to-end **Data Analytics project** using Python to analyze Google
Play Store applications, user reviews, app performance, monetization,
and sentiment.

The project covers **data cleaning, transformation, exploratory data
analysis (EDA), NLP-based sentiment analysis, interactive Plotly
visualizations, and an HTML dashboard**.

## 📌 Project Overview

The analysis uses two datasets:

-   `googleplaystore.csv` --- application-level information such as
    category, rating, reviews, installs, price, content rating, genres,
    and update date.
-   `User_Reviews_Google_Play.csv` --- user review text with
    sentiment-related fields.

The notebook loads both datasets, cleans and transforms the data, merges
app and review information, performs sentiment analysis using **VADER**,
creates interactive visualizations with **Plotly**, and generates an
HTML dashboard.

## 🎯 Objectives

-   Clean and prepare Google Play Store data for analysis
-   Analyze app categories and genres
-   Compare free and paid applications
-   Study app ratings, reviews, and installations
-   Analyze revenue by category
-   Examine app update trends over time
-   Perform sentiment analysis on user reviews
-   Build interactive visualizations
-   Generate a browser-based HTML dashboard

## 🛠️ Technologies & Libraries

  Technology                Purpose
  ------------------------- -----------------------------------------------------
  Python                    Data analysis and processing
  Pandas                    Data manipulation
  NumPy                     Numerical operations
  Plotly Express            Interactive visualizations
  NLTK / VADER              Sentiment analysis
  Scikit-learn              Machine-learning utilities imported in the notebook
  Jupyter Notebook          Development and analysis environment
  HTML / CSS / JavaScript   Interactive dashboard

## 🔄 Project Workflow

``` text
Raw CSV Data
     ↓
Load Datasets
     ↓
Data Cleaning
     ↓
Data Transformation
     ↓
Merge App + Review Data
     ↓
Feature Engineering
     ↓
Sentiment Analysis
     ↓
EDA & Interactive Visualizations
     ↓
HTML Dashboard
```

## 🧹 Data Cleaning & Transformation

The project includes:

-   Removing rows with missing ratings
-   Filling missing values using the column mode
-   Removing duplicate records
-   Validating ratings so they do not exceed 5
-   Removing reviews with missing review text
-   Converting `Installs` from text to numeric values
-   Converting `Price` from text to numeric values
-   Converting app `Size` into numeric MB values
-   Converting `Reviews` to numeric values
-   Converting `Last Updated` into datetime format
-   Extracting the update year
-   Creating log-transformed install and review features

## 🧠 Feature Engineering

Additional analytical features are created, including:

-   `Log_Installs`
-   `Log_Reviews`
-   `Rating_Group`
-   `Revenue`
-   `Year`
-   `Sentiment_Score`

The estimated revenue feature is calculated as:

``` python
Revenue = Price × Installs
```

## 💬 Sentiment Analysis

User reviews are analyzed using **NLTK VADER
SentimentIntensityAnalyzer**.

The project generates a sentiment score from review text using the VADER
compound score, allowing reviews to be analyzed based on their
sentiment.

Example:

``` python
sia = SentimentIntensityAnalyzer()

reviews_df["Sentiment_Score"] = reviews_df[
    "Translated_Review"
].apply(
    lambda x: sia.polarity_scores(str(x))["compound"]
)
```

## 📊 Visualizations

The notebook creates interactive Plotly visualizations including:

1.  **Top Categories on Play Store**
2.  **App Type Distribution**
3.  **Rating Distribution**
4.  **Sentiment Distribution**
5.  **Installs by Category**
6.  **Number of Updates over the Years**
7.  **Revenue by Category**
8.  **Top Genres**
9.  **Impact of Last Update on Rating**
10. **Rating for Paid vs Free Apps**

The notebook also saves individual visualizations as HTML files.

## 📈 Key Insights

Based on the analysis implemented in the notebook:

-   The Play Store contains a wide variety of application categories,
    with several categories having substantially more apps than others.
-   Free applications make up the large majority of apps compared with
    paid applications.
-   App ratings are generally concentrated toward the higher end of the
    rating scale.
-   Installation volume varies considerably across categories.
-   Revenue analysis highlights categories with stronger monetization
    potential.
-   App update activity can be analyzed year by year.
-   User reviews provide additional qualitative information through
    sentiment analysis.
-   The comparison of paid and free apps provides insight into
    differences in rating distributions.

> **Note:** These insights describe patterns explored in this project
> and should be interpreted within the limitations of the underlying
> dataset.

## 🌐 Interactive HTML Dashboard

The project includes code for generating a web dashboard containing the
interactive Plotly charts.

The dashboard is generated as:

``` text
html_files/
└── web page.html
```

The notebook also creates a `plots/` directory for individual
interactive chart HTML files.

## 📁 Recommended Repository Structure

``` text
Google-Playstore-Data-Analysis/
│
├── Google-Playstore-data-analysis.ipynb
├── googleplaystore.csv
├── User_Reviews_Google_Play.csv
│
├── plots/
│   ├── Category_Graph_1.html
│   ├── Type_Graph_2.html
│   ├── Rating_Graph_3.html
│   ├── Sentiment Distribution 4.html
│   ├── Installs by Category 5.html
│   ├── Updates Graph 6.html
│   ├── Revenue Graph 7.html
│   ├── Genre Graph 8.html
│   ├── Update Graph 9.html
│   └── Paid Free Graph 10.html
│
├── html_files/
│   └── web page.html
│
└── README.md
```

## ⚙️ Installation

Clone the repository:

``` bash
git clone https://github.com/peeyush-thakre/Google-Playstore-Data-Analysis.git
cd Google-Playstore-Data-Analysis
```

Install the required libraries:

``` bash
pip install numpy pandas plotly scikit-learn nltk jupyter
```

## ▶️ Run the Project

Start Jupyter Notebook:

``` bash
jupyter notebook
```

Open:

``` text
Google-Playstore-data-analysis.ipynb
```

Make sure the two CSV datasets are available in the expected project
location before running the notebook.

For VADER sentiment analysis, download the NLTK resource if required:

``` python
import nltk
nltk.download("vader_lexicon")
```

## 💡 Skills Demonstrated

-   Data Cleaning
-   Data Preprocessing
-   Exploratory Data Analysis
-   Feature Engineering
-   Data Visualization
-   Interactive Visualization
-   Natural Language Processing
-   Sentiment Analysis
-   Business Insight Generation
-   HTML Dashboard Development
-   Python for Data Analytics

## 🚀 Future Improvements

-   Add a dedicated machine-learning prediction model
-   Add more advanced NLP techniques
-   Build a Power BI version of the dashboard
-   Add automated data pipelines
-   Deploy the dashboard online
-   Add additional KPIs and filters
-   Improve dashboard responsiveness and UX

## 👨‍💻 Project Purpose

This project was created as a practical **Data Analytics portfolio
project** to demonstrate the complete workflow from raw data to
actionable insights and an interactive dashboard.

------------------------------------------------------------------------

⭐ If you find this project useful, consider giving the repository a
star!
