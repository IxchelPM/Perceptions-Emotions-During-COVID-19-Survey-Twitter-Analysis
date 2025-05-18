# Exploring Perceptions and Emotions During COVID-19  
### A Mixed-Data Analysis of Survey Responses and Twitter Content

## Introduction

The COVID-19 pandemic significantly altered daily life across the world, shaping public sentiment, emotional well-being, and opinions on government measures. This project presents a dual-perspective analysis by examining:

- Structured survey data collected from individuals in **Milan** and **New York**  
- Unstructured social media data from **Twitter**

Using Python-based tools and libraries such as **Pandas**, **NumPy**, **Matplotlib**, **Seaborn**, **TextBlob**, and **NLTK**, this analysis explores how people *felt*, *reacted*, and *reflected* during various phases of the pandemic.

The project is organized into three key sections:

1. **Data Preprocessing**  
   Loading, cleaning, and transforming survey and Twitter datasets. Column renaming and feature engineering were essential for clarity and effective analysis.

2. **Survey Data Analysis**  
   An in-depth exploration of how demographics, living situations, and work/study conditions influenced emotional and psychological responses. Topics include:
   - Emotional well-being and living arrangements
   - Public opinion on mask mandates, lockdowns, and vaccination passes
   - Feelings and experiences after testing positive for COVID-19
   - Impact on students and professionals
   - Perceptions of returning to "normality"
   - General emotions associated with the pandemic

3. **Twitter Data Analysis**  
   Natural language processing (NLP) techniques were applied to examine sentiment and categorize emotions in real-time COVID-19 related tweets. This includes:
   - Text cleaning and preprocessing
   - Sentiment analysis using polarity and subjectivity scores
   - Emotion classification using keyword matching, WordNet expansion, and manual variation detection
   - Comparison of online sentiment with reported emotions from survey participants

## Analysis Overview

The analysis is conducted in a Jupyter Notebook (`covid_analysis.ipynb`) and is broadly divided into data preprocessing, survey data analysis, and Twitter data analysis.

### 1. Data Preprocessing
-   **Loading Data:** Importing the survey (`dataset.csv`) and Twitter (`covid19_tweets.csv`) datasets.
-   **Extensive Column Renaming:** A significant number of columns in the survey data were renamed for clarity and ease of use (e.g., `'At the beginning of the pandemic did you work or study?'` to `'Work_Study_Status'`).
-   **Handling Missing Values:**
    -   Missing values (NaNs) in specific survey columns (often categorical responses like feelings or choices) were identified.
    -   These NaNs were strategically replaced with 'No', while existing values were converted to 'Yes', effectively transforming these columns into binary indicators.
-   **Feature Selection (Column Removal):** Columns deemed irrelevant for the specific analysis goals were dropped from the survey dataset.

### 2. Survey Data Analysis: Perceptions and Experiences During COVID-19
This section explores various facets of the pandemic's impact using the cleaned survey data.

-   **Living Situations and Emotional Well-being:**
    -   Analyzes how living arrangements (e.g., with family, friends, pets, alone) correlated with reported feelings (boredom, stress, loneliness, etc.).
    -   Compares feelings of those living alone versus with others, including feelings experienced when talking to friends/family.
    -   Examines these feelings across different ethnic groups.
-   **Public Opinion on COVID-19 Measures:**
    -   Assesses levels of agreement (on a 1-5 Likert scale) with measures like mask mandates, lockdowns, vaccination passes, social distancing, and quarantine for 2020 and 2021.
    -   Investigates how these opinions varied across demographic groups (Age, Gender, Ethnicity).
-   **Perceptions Regarding Non-Vaccinated Individuals:**
    -   Explores emotions (e.g., proud, optimistic, vulnerable, hostile) survey respondents associated with people who were not vaccinated.
    -   Analyzes these perceptions by age group and gender.
    -   Compares opinions on vaccination passes (for 2020 and 2021) between respondents from Milan and New York.
-   **Experiences and Feelings Upon Testing Positive for COVID-19:**
    -   Tracks the timeline of positive tests (2020, 2021, 2022) and analyzes distributions by age, work/study status, and gender.
    -   Determines the frequency of testing positive (once, twice, thrice).
    -   Identifies common feelings (stressed, optimistic, lonely, etc.) experienced by individuals upon testing positive.
-   **Impact on Students: Feelings About Studying During the Pandemic:**
    -   Focuses on respondents who were students (or both working and studying).
    -   Analyzes the prevalent emotions (bored, stressed, free, proud, etc.) related to their study experience.
    -   Categorizes these feelings into broader 'Positive', 'Negative', or 'Neutral' sentiments.
-   **Impact on Professionals: Workplace Emotions and Career Changes:**
    -   Examines emotional responses (free, aggressive, frustrated, etc.) of professionals in their work environment.
    -   Investigates reported changes in professional situations (e.g., reduced hours, smart working, job loss).
-   **Comfort Levels in Social Activities (Winter 2021 vs. Summer 2022):**
    -   Compares self-reported comfort levels (on a 1-5 scale) for various social activities (e.g., meeting friends, going to public places, using public transport, attending crowded outdoor events) between Winter 2021 and Summer 2022.
    -   Analyzes the correlation between comfort levels for different activities.
-   **Perception of Returning to "Normality":**
    -   Assesses individuals' perception (on a 1-10 scale) of how much they felt they had returned to their pre-pandemic "normality."
    -   Compares these perceptions by city (Milan vs. New York) and age group.
-   **General Emotions Associated with COVID-19:**
    -   Identifies the predominant emotions (anxious, frustrated, optimistic, etc.) that participants generally associated with the COVID-19 pandemic.
    -   Classifies these emotions into 'Positive' and 'Negative' types.
    -   Examines how these associated emotions varied by job sector and age group.

### 3. Twitter Data Analysis: Public Sentiment and Emotions
This section analyzes public discourse on Twitter regarding COVID-19.

-   **Data Collection and Cleaning:**
    -   Loads COVID-19 related tweets.
    -   Cleans tweet text by removing URLs, mentions, hashtags, RT symbols, punctuation, and converting to lowercase.
-   **Sentiment Analysis:**
    -   Applies TextBlob to perform sentiment analysis on cleaned tweets, calculating polarity and subjectivity scores.
    -   Classifies tweets into 'positive', 'negative', or 'neutral' sentiments based on polarity.
-   **Emotion Categorization:**
    -   Explores multiple approaches to categorize tweets into more specific emotions (e.g., Free, Optimistic, Anxious, Stressed):
        1.  **TextBlob NaiveBayesAnalyzer:** Basic keyword matching.
        2.  **NLTK WordNet:** Using synonyms and related words for a predefined list of emotions.
        3.  **Manual Variations:** Matching manually defined common variations of emotion words.
-   **Comparative Analysis:**
    -   Compares the distribution of emotions identified through different NLP techniques on Twitter data with the emotions reported in the survey data (specifically from New York respondents).

## Key Visualizations
The notebook generates a wide array of visualizations to present the findings, including:
-   **Heatmaps:** For showing correlations (e.g., living situations vs. feelings, comfort level correlations) and distributions (e.g., COVID-19 measure agreement).
-   **Bar Charts (Simple, Stacked, Grouped, Diverging):** For comparing counts, percentages, and mean values across categories (e.g., feelings by demographic, positive tests by year, comfort levels).
-   **Box Plots:** For showing distributions of numerical responses across categories (e.g., 'Feel_normal' by city/age).
-   **Histograms & KDE Plots:** For visualizing the distribution of responses (e.g., 'Feel_normal' scores).

