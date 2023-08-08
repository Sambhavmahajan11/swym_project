# Swym project - Analyzing Product Reviews
Analyzing Product Reviews
This repository contains code to analyze product reviews from a dataset. The goal is to identify potential promoters among users and find the product with the most promoters. The analysis involves sentiment analysis, feature engineering, and data processing techniques.

Table of Contents
1.Introduction
2.Datasets
3.Code Overview
4.Usage
5.Results

Introduction
In this project, we analyze product reviews to identify potential promoters and determine the product with the most promoters. The analysis involves calculating sentiment scores, creating a scoring system based on review sentiment and ratings, and aggregating the results to identify the desired outcomes.
we consider 4 factors for importance of a post :
a. Overall rating 
classify 1,5⭐ ratings as 0.6 
classify 2,4⭐ ratings as 0.3 
classify 3⭐ ratings as 0.1
b.Sentiment score
using the NLTK library
c.Verified
0.75 if the user is verified
0.25 if the user is not verified
at last we calculate the score of each post as follows

df['score']=df['overall']*df['senti_score'] 
df['score'] = df['score'] * (0.75 * df['verified'] + 0.25 * ~df['verified'])
     

Datasets
We have used two datasets for this analysis:

Review Dataset: Contains user-product review information, including reviewer information, review text, ratings, and helpful votes.
Product Metadata Dataset: Provides product information such as title, description, price, brand, and related products.
Code Overview
The code is structured into different sections:

Data Loading and Preprocessing: We load the review and product metadata datasets, perform data cleaning, and combine relevant information.

Sentiment Analysis: We utilize the VADER sentiment analysis tool to calculate sentiment scores for each review text.

Calculating Review Scores: Based on sentiment scores and overall ratings, we calculate a review score for each review that represents its positivity.

Identifying Potential Promoters: We aggregate review scores for each user to identify potential promoters. Additionally, we identify the user with the most positive reviews across different products as the global potential promoter.

Finding Products with Most Promoters: We track the number of promoters for each product and identify the product with the most promoters.

Saving Results: The calculated results and processed data are saved using pickle for further analysis and visualization.

Usage
Clone this repository to your local machine.
Ensure you have the necessary dependencies installed. You can use the following command to install them: pip install -r requirements.txt.
Execute the code by running the main script.
Results
The code aims to identify the global potential promoter (user with the most positive reviews across different products) and the product with the most promoters. The final outcomes are based on the calculated review scores and counts.
