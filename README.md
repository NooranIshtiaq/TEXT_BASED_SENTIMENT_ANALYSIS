# TEXT_BASED_SENTIMENT_ANALYSIS
Sentiment and thematic analysis on Amazon product reviews using NLP techniques. The project involves preprocessing raw text data, performing thematic categorization, and classifying reviews into positive, negative, or neutral sentiments.

# 📊 Amazon Reviews Sentiment Analysis (Colab)

This project performs sentiment analysis on Amazon Cell Phones & Accessories reviews. It classifies reviews as **Positive**, **Negative**, or **Neutral** based on keyword sentiment scores and frequency-based keyword extraction.

## 🗂 Dataset

- **Source**: [Amazon Product Review Dataset](https://nijianmo.github.io/amazon/index.html)
- **File Used**: `Cell_Phones_and_Accessories_5.json`
- **Attributes Selected**: `reviewerID`, `asin`, `reviewText`, `overall`, `summary`, `reviewTime`

## 🧠 Workflow

1. **Mount Google Drive**  
   The dataset is accessed via Google Drive for seamless loading in Google Colab.

2. **Data Loading & Filtering**
   - Loads JSON data line by line.
   - Filters out relevant columns.
   - Converts all text to lowercase.

3. **Text Preprocessing**
   - Removes punctuation.
   - Removes stopwords (using a custom stopword file from NLTK list).
   - Cleans and tokenizes review text.

4. **Keyword Frequency Analysis**
   - Splits reviews into **positive** (`overall >= 4.0`) and **negative** (`overall <= 2.0`).
   - Calculates word frequencies using `collections.Counter`.
   - Extracts keywords with a minimum threshold count (default: 4).

5. **Sentiment Scoring**
   - Custom weights assigned to key sentiment words (e.g., `good`, `bad`, `excellent`, etc.).
   - Each review’s score is calculated based on word weights.
   - Scores are categorized as:
     - `Positive` if score > 0.5
     - `Negative` if score < -0.5
     - `Neutral` otherwise

6. **Output**
   - Results are saved in a text file `sentiments.txt` with:
     - Review ID
     - Sentiment Label
     - Cleaned Review Text

## 🔍 Example Output

