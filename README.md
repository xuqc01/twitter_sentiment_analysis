# twitter_sentiment_analysis

**Authors**: Maddie Smithers, Steven Hui

## Overview

This project aims to analyze the sentiment of Tweets about Apple products in the South by Southwest conference held in 2012. We hope to use this data to predict the sentiment (positive or negative) of newer tweets not found in our data so that we can find and address negative reviews of the Apple products more effectively in the future.

## Business Situation

We've learned that customer feedback is a crucial element in developing a successful product that would lead to higher return on investments and greater customer satisfaction. To consider customer feeedback, our team created a model to predict whether Tweets about the Apple product exhibits negative or positive sentiment. That way, we can specifically focus on Tweets with negative sentiment and improve our products based on their feedback. 

## Data Information

We obtained our data from CrowdFlower (https://data.world/crowdflower/brands-and-product-emotions), a human-in-the-loop machine learning company that uses human intelligence to label and transcribe text and images. We gathered about 2,560 Tweets where the target variable was originally quaternary, having positive, negative, no emotion, and unsure as possible variables; these Tweets were from a conference in South by Southwes in 2012. The quaternary variable was then limited to just positive and negative emotions to simplify the machine learning process and to focus more on our business problem.

After converting our target variable into a binary classification, we noticed that the classes were highly imbalanced. In other words, there were much more positive Tweets than there were negative. In order to balance the this distribution, we generated an additional 600 negative Tweets with ChatGPT. We then had a 60-40 ratio between positive and negative tweets.
## Modelling

Our metric of interest was recall. We wanted to minimize the number of false negatives (predicting that the Tweet had positive sentiment, when in reality it did not) because our goal is to find as many negative tweets to address. We used a RandomForestClassifier as our model with the hyperpararmeters: n_estimators as 10, criterion as 'gini', max_depth as 5, and a random state of 42 to achieve consistent results. With only the default stop words found in the Natural Language Toolkit (NLTK), the model produced a baseline recall score of 62.37%. After adding new stop words that appeared in a majority of the Tweets, such as apple, sxsw, ipad, and iphone, the model produced an improved recall score of 70.88%. 

## Results

Listed below are word clouds that show the most frequent words in the Tweets:

- Positive Apple Tweets about all their products: 'new', 'store', 'pop'. It seems that customers were excited to purchase new Apple products in pop-up stores.
![image](https://github.com/xuqc01/twitter_sentiment_analysis/assets/38637431/c86b16fb-bc8a-485d-b29c-374cd5bd76ce)

- Negative Apple Tweets about all their products: 'store', 'line', 'time', 'design headache'. It seems that customers were dissatisfied with the store lines and the product itself.
![image](https://github.com/xuqc01/twitter_sentiment_analysis/assets/38637431/2dcdb7d5-01ff-44f0-9e5c-ff1ff8d1a765)

- Positive Apple Tweets about their iPhone: 'case', 'new', 'thank'. For iPhones, customers were again happy with the novelty of the product. 
![image](https://github.com/xuqc01/twitter_sentiment_analysis/assets/38637431/002ee727-e4e6-4761-b745-339db32e5332)

- Negative Apple Tweets about their iPhone: 'battery', 'time', 'blackberry'. For iPhones, customers were primarily making complaints about the iPhone's battery life and made multiple comparisons to Apple's competitors such as Blackberry and Android.
![image](https://github.com/xuqc01/twitter_sentiment_analysis/assets/38637431/02fffa23-ee92-4634-807d-6bd468f0b6ab)

## Conclusions

Through cleaning, anlayzing, and pre-processing our dataset, our team was able to successfully uncover the most significant topics discussed on Twitter regarding Apple and SXSW 2012. By performing sentiment analysis and training an XGBoost Classifier, we created a model that can predict whether a tweet is positive or negative with 73% recall. Paying attention to customer sentiment on Twitter is extremely important to most companies, particularly tech companies like Apple with technology-inclined users.

## Future Insights

-**Consider Tweets from other events**: Tweets from other events may incorporate different opinions than the ones that were just found in South by Southwest.

-**Focus on Tweets that mention competitors**: It's important to focus on Tweets that specifically mention competitors because it reveals their advantages and disadvantages over the Apple product which will enable Apple to adjust and improve accordingly. 

-**Create a model that incorporates neutral tweets**: Our current model only has positive and negative Tweets. The inclusion of netural tweets may improve the overall performance of our model since it has exposure to a larger range of Tweets. 

## For More Information

Read the full analysis in our [Jupyter Notebook](https://github.com/xuqc01/twitter_sentiment_analysis/blob/main/P4ProjectNotebook.ipynb).

## Repository Structure

├── Data

├── Flu_Analysis.pdf

├── Flu_Analysis_notebook.ipynb

├── Flu_Analysis_notebook.pdf
