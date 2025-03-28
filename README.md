# Swahili news classification model on NLP


## Project Overview

News media plays a crucial role in shaping public opinion, informing societies, and influencing political and social discourse. In East Africa, Swahili is one of the most widely spoken languages, serving as a unifying medium for news dissemination across multiple countries, including Tanzania, Kenya, Uganda, Rwanda, Burundi, and the Democratic Republic of Congo.

With the rise of digital journalism, there has been a rapid increase in Swahili news content, necessitating the need for automated classification of Swahili news articles. This project aims to leverage Natural Language Processing (NLP) and Deep Learning to develop a model that can accurately categorize Swahili news content into predefined categories

## Business Understanding
The growing volume of Swahili-language news presents a challenge for media organizations in managing, organizing, and delivering relevant content efficiently. Manual classification is labor-intensive, time-consuming, and prone to inconsistencies, leading to inefficiencies in news dissemination. To address this, automated categorization using Natural Language Processing (NLP) and Deep Learning offers a scalable and reliable solution. By leveraging these technologies, news platforms, media houses, and content aggregators can streamline content management, enhance searchability, and improve audience engagement.


## Objectives
Automating News Classification.
How can we efficiently categorize Swahili news articles using machine learning and deep learning?

Understanding Media Trends.
What are the most common news topics in East African media?

Are there any biases in media coverage based on classification trends?

Enhancing Content Accessibility.
How can automated classification improve information retrieval for journalists, policymakers, and the general public?

## Data Understanding

### Overview
This dataset consists of Swahili news articles categorized into different topics. The goal is to classify news articles into predefined categories using Natural Language Processing (NLP) and Deep Learning techniques.

### Data Structure
The dataset contains the following columns:

id: A unique identifier for each news article.

content: The text of the news article written in Swahili.

category: The label representing the category of the news article (e.g., uchumi, kitaifa, michezo).


### Categories in the Data
The dataset has multiple categories representing different types of news. Some of the common categories include:

Uchumi (Economy): Articles related to business, finance, and economic activities.

Kitaifa (National News): General news related to Tanzania.

Michezo (Sports): News about sports teams, events, and athletes.

(Other categories may exist and need to be explored further.)


### Data Size and Distribution
To understand the dataset better, key aspects to analyze include:

The total number of articles.

The distribution of articles across different categories (class imbalance analysis).

The average length of articles in terms of word count.

### Data Quality Issues
Potential issues to check before preprocessing:

Missing values: Are there any missing or empty fields?

Duplicates: Are there repeated news articles?

Class imbalance: Are some categories significantly overrepresented compared to others?

Noise in text: Presence of irrelevant characters, symbols, or stopwords that may need cleaning.


## Problem Statement
The goal of this project is to build a Swahili news classification model that accurately categorizes news articles into six predefined categories:

uchumi (economy)

kitaifa (national news)

michezo (sports)

kimataifa (international news)

burudani (entertainment)

afya (health)

To achieve this, we will preprocess the text data to remove noise, tokenize, and normalize the text, followed by building a classification model. To ensure a clear, reproducible, and scalable approach, we will implement the preprocessing steps within an Scikit-learn Pipeline.

## Modeling  

- We have trained several machine learning models: **Naive Bayes, Logistic Regression, Linear SVC, and Random Forest**.  
- Due to the complexity of our data, our machine learning models were all **overfitting**.  
- We have applied **SVD**, but it yielded **no significant results**.  
- We hyperparameter-tuned **Naive Bayes, Logistic Regression, and Linear SVC** and attempted **ensembling**, but that too did not salvage the models.  


### Deep Learning Approach

Due to overfitting in traditional models and the complexity of our dataset, we transitioned to deep learning models to better capture the intricacies of Swahili news content.

#### LSTM Model

We implemented a Long Short-Term Memory (LSTM) model, designed to handle sequential data.

Despite the model's ability to process sequential dependencies, it underfitted, with validation accuracy stagnating at 45.64%.

The model struggled due to possible data imbalance, suboptimal learning rate, or insufficient complexity.

#### BiLSTM Model

We then implemented a Bidirectional LSTM (BiLSTM), which processes input sequences in both forward and backward directions.

However, validation accuracy still remained at 45.64%, and training loss decreased but did not lead to better generalization.

#### BERT Model

Finally, we fine-tuned a BERT-base-uncased model for sequence classification.

Performance Results:

Accuracy: 89.41%

F1 Score: 89.34%

The small gap between accuracy and F1 score indicates that the model effectively balances precision and recall.

The BERT model demonstrated strong generalization, making it the best-performing classifier.

#### Conclusion

Text Length Analysis: The "afya" and "kitaifa" categories have the longest articles, which may introduce complexity in training.

Best Classifier: The fine-tuned BERT model significantly outperformed all other models, achieving 89.41% accuracy.

#### Recommendations

Optimize Content Length for Categories:

Shorter content for "burudani," longer content for "afya" and "kitaifa."

Enhance User Engagement:

Tailor content length to user preferences to improve retention and interaction.

Automate Content Classification:

Implement automated tagging using the Fine-Tuned BERT model for better content organization and searchability.

Refer to the main notebook for more details.  