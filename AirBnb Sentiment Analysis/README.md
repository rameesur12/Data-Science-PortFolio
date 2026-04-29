# 🏙️ Airbnb London Reviews Sentiment Analysis using NLP

## 🔗 Full Code and Results

The full notebook for this project can be opened in Google Colab once it is uploaded to GitHub.

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](PASTE_YOUR_COLAB_NOTEBOOK_LINK_HERE)

> Replace the placeholder link above with your actual Colab/GitHub notebook link after uploading `Main.ipynb` to your project folder.

---

## 📌 Project Introduction

This project analyses **Airbnb guest reviews in London** using Natural Language Processing (NLP) techniques. The aim is to understand how guests perceive different London neighbourhoods by examining review text, sentiment scores, and neighbourhood-level similarity patterns.

The project uses two main datasets:

- `reviews.csv` — guest review text and review dates  
- `listings.csv` — listing information, including neighbourhood details

The analysis focuses on three key areas:

1. **Neighbourhood similarity** — identifying which areas are most strongly associated with positive or negative descriptors.
2. **Sentiment analysis** — ranking London neighbourhoods based on guest sentiment.
3. **Temporal stability** — checking whether sentiment trends remained stable or changed over time.

---

## 🎯 Purpose of the Project

The purpose of this project is to transform large volumes of Airbnb review text into useful insights about guest experience and neighbourhood perception.

This project answers questions such as:

- Which London neighbourhoods receive the most positive guest feedback?
- Which neighbourhoods are more strongly associated with negative descriptors such as noise, high prices, or safety concerns?
- Are guest sentiment trends stable over time?
- How can NLP techniques support Airbnb hosts, travellers, urban planners, and decision-makers?

This makes the project useful for demonstrating practical skills in **data cleaning, text preprocessing, NLP, sentiment analysis, feature extraction, visualisation, and insight generation**.

---

## 🧠 Techniques Used and Why

| Technique | Why it was used |
|---|---|
| **Pandas** | To load, clean, merge, and process the reviews and listings datasets. |
| **Data cleaning** | To handle missing values, duplicates, irrelevant entries, and inconsistent data. |
| **Sampling** | To reduce the dataset to 200,000 reviews for faster and more efficient processing. |
| **Language detection** | To keep only English-language reviews for consistent sentiment analysis. |
| **spaCy text preprocessing** | To clean review text through lowercasing, punctuation removal, stopword removal, and lemmatisation. |
| **TF-IDF Vectorisation** | To convert cleaned review text into numerical features suitable for text similarity analysis. |
| **Cosine Similarity** | To measure how closely neighbourhood reviews matched predefined positive and negative descriptors. |
| **VADER Sentiment Analysis** | To calculate sentiment scores for guest reviews using a lexicon-based NLP method suitable for short review texts. |
| **Temporal Analysis** | To examine whether sentiment trends remained stable across different years. |
| **Visualisation** | To present trends using scatter plots, heatmaps, and bar charts. |

---

## 🗂️ Dataset Overview

The project uses Airbnb data for London, mainly through two files:

### `reviews.csv`
Contains guest reviews, including review comments and dates. This file was used as the main source for sentiment and text analysis.

### `listings.csv`
Contains listing-level information, including neighbourhood data. This was merged with the reviews data to connect each review to a specific London neighbourhood.

The final analysis required merging these datasets so that each review could be analysed in relation to its neighbourhood.

> ⚠️ Note: The dataset files are large. If GitHub does not allow uploading them directly, they should be stored using Git LFS or referenced through an external source such as Google Drive, Kaggle, or the original dataset provider.

---

## 🧹 Data Cleaning and Preprocessing

The project included several important cleaning and preprocessing steps before applying NLP techniques.

### 1. Loading and inspecting the data
The reviews and listings datasets were loaded into Pandas. Initial checks were performed to understand:

- dataset shape
- column names
- missing values
- duplicate records
- data types

This step helped identify data quality issues before analysis.

### 2. Handling missing values
Rows with missing review comments were removed because incomplete review text would distort the sentiment analysis.

For the listings dataset, missing values in numerical columns such as `reviews_per_month` were filled with `0`. This allowed the dataset to remain usable without introducing unnecessary missing-value errors during processing.

### 3. Merging reviews and listings
The reviews dataset was merged with the listings dataset to link each review with its corresponding neighbourhood. During the merge, duplicate ID columns such as `id_x` and `id_y` were handled to avoid redundancy.

This step was essential because the sentiment analysis needed to be grouped by neighbourhood.

### 4. Removing duplicates and filtering dates
Duplicate reviews were removed to avoid repeated records influencing the analysis.

The `date` column was converted to datetime format, and the dataset was filtered to keep reviews from **2015 onwards**. This helped keep the analysis more relevant and focused on recent guest experiences.

### 5. Sampling the dataset
The original dataset contained a very large number of reviews, making full processing computationally expensive.

To improve efficiency, a random sample of **200,000 reviews** was selected. This allowed the project to remain manageable while still using a large enough sample for meaningful analysis.

### 6. Language filtering
Language detection was applied using `langdetect`, with `swifter` used to speed up processing.

Only English-language reviews were retained. This was important because VADER sentiment analysis and the chosen text preprocessing approach were designed for English text.

### 7. Text preprocessing
The review text was cleaned using NLP preprocessing techniques, including:

- converting text to lowercase
- removing punctuation and special characters
- removing stopwords
- lemmatising words to their base form

This created a cleaner version of the review text for TF-IDF, similarity analysis, and sentiment scoring.

---

## 🔍 Methodology

### 1. Neighbourhood Similarity Analysis

TF-IDF vectorisation was used to convert cleaned review text into numerical vectors. The project then compared neighbourhood review text with predefined positive and negative descriptor lists.

Examples of positive descriptors included words such as:

```text
vibrant, charming, peaceful, gastronomic, affordable, historic
```

Examples of negative descriptors included words such as:

```text
isolated, overpriced, noisy, unsafe, crime, gentrified
```

Cosine similarity was then applied to measure how closely reviews aligned with these positive and negative descriptors.

The similarity scores were aggregated at neighbourhood level to identify which areas were described more positively or negatively by Airbnb guests.

---

### 2. Sentiment Analysis using VADER

VADER Sentiment Analysis was applied to each cleaned review. VADER produces a compound sentiment score ranging from:

```text
-1 = very negative
 0 = neutral
+1 = very positive
```

The sentiment scores were then grouped by neighbourhood to calculate average neighbourhood sentiment.

This made it possible to rank neighbourhoods from the most positively reviewed to the most negatively reviewed.

---

### 3. Temporal Stability Analysis

To assess whether guest sentiment changed over time, the year was extracted from the review date.

Average sentiment scores were calculated for each year, and variance was used to measure stability.

A low variance indicates stable sentiment trends, while a higher variance would suggest stronger changes over time.

---

### 4. Visualisation

Several visualisations were used to support interpretation:

- **Scatter plot** — to compare positive and negative similarity scores.
- **Heatmap** — to show correlation between similarity scores.
- **Bar charts** — to rank the most positively and negatively perceived neighbourhoods.

These visualisations made the results easier to interpret and present.

---

## 📊 Key Findings

### 1. Neighbourhood Similarity Findings

The cosine similarity analysis identified the neighbourhoods most strongly associated with positive and negative descriptors.

#### ✅ Most positively similar neighbourhoods

These neighbourhoods were most strongly associated with positive descriptors such as vibrant, charming, peaceful, and affordable:

1. Sutton  
2. Barking and Dagenham  
3. Harrow  
4. Barnet  
5. Bexley  

#### ⚠️ Most negatively similar neighbourhoods

These neighbourhoods were more strongly associated with negative descriptors such as overpriced, noisy, unsafe, or crime-related terms:

1. Tower Hamlets  
2. Camden  
3. Westminster  
4. City of London  
5. Hackney  

### Interpretation

Sutton and Barking and Dagenham showed strong positive descriptor similarity, suggesting that guests often associated these areas with favourable experiences. Camden and Westminster showed stronger negative similarity, which may be linked to issues such as pricing, noise, congestion, or perceived safety concerns.

---

### 2. Sentiment Analysis Findings

Using VADER sentiment scores, neighbourhoods were ranked based on average guest sentiment.

#### 😊 Happiest neighbourhoods

The neighbourhoods with the highest average sentiment scores were:

1. Richmond upon Thames  
2. Hackney  
3. Lambeth  
4. Wandsworth  
5. Kingston upon Thames  

#### 😕 Most negatively reviewed neighbourhoods

The neighbourhoods with the lowest average sentiment scores were:

1. Sutton  
2. Camden  
3. Croydon  
4. City of London  
5. Havering  

### Interpretation

Richmond upon Thames and Hackney had high sentiment scores, suggesting positive guest experiences overall. Camden appeared in both negative descriptor similarity and lower sentiment rankings, indicating that it may receive mixed or more critical guest feedback despite being a popular London area.

---

### 3. Correlation Between Positive and Negative Similarity

A negative correlation of approximately **-0.42** was observed between positive and negative similarity scores.

This suggests that neighbourhoods with stronger positive associations generally had weaker negative associations. However, some overlap existed, meaning certain neighbourhoods could receive both positive and negative feedback depending on guest expectations and experiences.

Hackney is a good example of a mixed-perception area because it appeared in both positive sentiment and negative similarity results.

---

### 4. Temporal Stability of Sentiment Trends

The yearly sentiment variance was approximately:

```text
0.0010
```

This indicates that Airbnb guest sentiment in London remained relatively stable over time.

### Interpretation

There were no major shifts in yearly guest sentiment. This suggests that overall guest perceptions of London neighbourhoods remained consistent despite possible changes in tourism, housing policy, or market conditions.

---

## ✅ Main Conclusion

This project used NLP techniques to analyse Airbnb reviews and understand guest perceptions of London neighbourhoods.

The combination of **TF-IDF**, **cosine similarity**, and **VADER sentiment analysis** made it possible to identify both descriptive patterns and overall sentiment trends. The findings showed that neighbourhoods such as Richmond upon Thames and Hackney received positive guest sentiment, while Camden and Westminster had stronger negative associations in some parts of the analysis.

The temporal analysis also showed that sentiment trends remained stable over time, suggesting consistent guest perceptions across the reviewed period.

Overall, this project demonstrates how NLP can be used to convert large-scale customer review data into meaningful insights for tourism, accommodation platforms, urban planning, and service improvement.

---

## ⚠️ Limitations

This project had several limitations:

1. **Large dataset and sampling bias**  
   The original dataset contained a very large number of reviews. A sample of 200,000 reviews was used for efficiency, but this may have introduced sampling bias.

2. **English-only filtering**  
   Only English-language reviews were retained. Some useful multilingual feedback may have been excluded.

3. **Limitations of VADER**  
   VADER is effective for short text, but it can struggle with sarcasm, context, and complex expressions.

4. **Preprocessing limitations**  
   Removing stopwords and lemmatising text may sometimes remove context or alter subtle meaning.

5. **Neighbourhood-level aggregation**  
   Averaging sentiment at neighbourhood level may hide variation between individual listings or property types.

---

## 🚀 Future Improvements

Future work could improve the project by:

- using the full dataset with better computing resources
- comparing VADER with transformer-based models such as BERT
- analysing sentiment by property type, price range, or host characteristics
- adding topic modelling to identify common complaint themes
- building an interactive dashboard using Tableau, Power BI, Streamlit, or Plotly Dash
- improving multilingual analysis instead of filtering only English reviews

---

## 📁 Project Folder Guide

The project folder can be organised as follows:

```text
Airbnb_London_Sentiment_Analysis/
│
├── README.md
├── airbnb_sentiment_analysis.py
│
└── project_files/
    ├── notebooks/
    │   └── Main.ipynb
    │
    ├── data/
    │   └── raw/
    │       ├── listings.csv
    │       └── reviews.csv
    │
    ├── reports/
    │   ├── CST4070 Challenge w14.pdf
    │   └── CST4070_Challenge_14_Unit3.pdf
    │
    └── outputs/
        ├── charts/
        └── sentiment_results/
```

### Current folder contents

Based on the project folder, the files include:

| File | Purpose |
|---|---|
| `Main.ipynb` | Main notebook containing the NLP analysis workflow. |
| `reviews.csv` | Main review dataset used for sentiment and text analysis. |
| `listings.csv` | Listing dataset used to connect reviews with neighbourhood information. |
| `CST4070 Challenge w14.pdf` | Challenge or assignment brief. |
| `CST4070_Challenge_14_Unit3.pdf` | Project documentation/report explaining methodology, findings, limitations, and conclusion. |

---

## ▶️ How to Run the Project

### Option 1: Run in Google Colab

1. Open the notebook using the Colab badge at the top of this README.
2. Upload or connect the required data files:

```text
reviews.csv
listings.csv
```

3. Run the cells in order.
4. Review the outputs, charts, and sentiment rankings.

### Option 2: Run locally

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/Data-Science-PortFolio.git
```

Navigate to the project folder:

```bash
cd Data-Science-PortFolio/Airbnb_London_Sentiment_Analysis
```

Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn spacy vaderSentiment langdetect swifter
python -m spacy download en_core_web_sm
```

Open the notebook:

```bash
jupyter notebook project_files/notebooks/Main.ipynb
```

---

## 🛠️ Tools and Libraries

- Python
- Pandas
- NumPy
- spaCy
- scikit-learn
- VADER Sentiment Analysis
- langdetect
- swifter
- Matplotlib
- Seaborn
- Google Colab / Jupyter Notebook

---

## 💼 Skills Demonstrated

This project demonstrates practical skills in:

- Natural Language Processing
- Sentiment Analysis
- Text Cleaning and Preprocessing
- TF-IDF Vectorisation
- Cosine Similarity
- Data Cleaning
- Dataset Merging
- Feature Engineering
- Exploratory Data Analysis
- Visualisation
- Temporal Trend Analysis
- Insight Communication
- GitHub Project Documentation

---

## 🧾 Portfolio Summary

This project is part of my data science portfolio. It demonstrates how NLP can be applied to real-world review data to extract insights about customer satisfaction, neighbourhood reputation, and sentiment stability over time.
