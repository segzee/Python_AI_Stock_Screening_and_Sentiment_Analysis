# AI Stock Screening and Sentiment Analysis
Overview
This Python script utilizes artificial intelligence (A.I.) and Python to streamline the process of stock screening and sentiment analysis. The goal is to identify potentially undervalued stocks by applying specific financial criteria and analyzing sentiment from news articles. The script integrates various libraries, including finvizfinance, transformers, yfinance, and goose3, to fetch financial data, perform sentiment analysis, and extract relevant information from news articles.

# Installation
Before running the script, ensure that the required libraries are installed. You can install them using the following command:

bash
Copy code
pip install finvizfinance pandas datetime requests bs4 lxml beautifulsoup4 zope.interface pytz numpy charset-normalizer idna urllib3 yfinance goose3 transformers
Usage

# 1. Undervalued Stock Screening
To identify undervalued stocks, use the get_undervalued_stocks function. It applies filters such as positive operating margin, low debt-to-equity ratio, low P/B and P/E ratios, positive insider transactions, and a specified market capitalization range.

python
Copy code
undervalued_stocks = get_undervalued_stocks()
print(undervalued_stocks)

# 2. Sentiment Analysis on News Articles
For each undervalued stock, sentiment analysis is performed on related news articles. The get_ticker_news_sentiment function retrieves news articles using Yahoo Finance, applies sentiment analysis using the FinBERT model, and constructs a DataFrame with the results.

python
Copy code
ticker_sentiment_df = get_ticker_news_sentiment(undervalued_stocks)
print(ticker_sentiment_df)
3. Generate CSV Files
To save sentiment analysis results for each undervalued stock as a CSV file, use the generate_csv function.

python
Copy code
for ticker in undervalued_stocks:
    generate_csv(ticker)
    
# 3. generate_csv Function
This function generates CSV files for sentiment analysis results related to each stock ticker.

# Components
1. get_undervalued_stocks Function
This function fetches undervalued stocks based on specific financial criteria, including positive operating margin, low debt-to-equity ratio, and more. It utilizes the finvizfinance library for data retrieval.

2. get_ticker_news_sentiment Function
This function performs sentiment analysis on news articles related to a list of stock tickers. It uses Yahoo Finance for news retrieval, the FinBERT model for sentiment analysis, and the goose3 library for web scraping.


Notes
Adjust parameters in the script to suit specific needs, such as industry-specific filtering.
Ensure proper authentication for the Hugging Face Hub if using private models.
The script creates an 'out' directory to store CSV files.
Disclaimer
This script is for educational purposes only and does not constitute financial advice. Use it responsibly and consult with financial professionals before making investment decisions.
