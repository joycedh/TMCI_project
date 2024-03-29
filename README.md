# TMCI_project: Fake News Detection

## Abstract
Online news sources are becoming increasingly popular and with that powerful. Fake news has always existed, but with more and more people choosing online news as their primarily news portal, fake news is becoming easier to generate and to spread. Fake news can be dangerous, which makes it important to be able to determine the accuracy of online news articles. Therefore, this project will analyze and research fake news articles in comparison to real news articles. This not only to examine the features of fake news but also to create a fake news detector. In this research we will make use of the liar dataset consisting of bot a training and test set of fake and real news articles concerning politics. 

## Research questions

#### What features are associated with fake news?
- What are the sentiments and most common words used in fake news?
- How accurate can we predict fake news by creating a detector using these, and other features? 
- What approach leads to the highest accuracy in prediction? 

## Dataset: The Liar Dataset
[The Liar Dataset](https://github.com/thiagorainmaker77/liar_dataset)
- The Liar Dataset is a dataset of short statements from [politifact.com](politifact.com). The statements are manually labeled into ‘pants on fire’, ’false’, ‘barely true’, ‘half true’, ‘mostly true’ and 'true'. The dataset also contains information on the subject of the statement, who produced it, their job, party and the context. 
- The dataset is divided into a training (+- 1200 statements) and a test-set (way larger)
- Feature engineering:
  - First, we would like to create a word-frequency vector from the dataset
  - Also, we would like to add a sentiment score to each statement

## A tentative list of milestones for the project

#### *By November 22: Preparation*
- Setting up:
  - create a representation of statements in a word vector to be applied for feature inspection, using word frequencies (ALL)
  - perform Logistic Regression to detect which features are the most important (ALL)
  
#### *By November 29: Learning*
- Start with feature engineering:
  - Sentimental value per statement
    - Find which Lexicon based model is most effective when applied to Fake News (Joyce, Eva)
    - Use this model to compute the sentimental value of each statement (Joyce, Eva)
  - Other features: think of which features already apparent in the dataset can also be used in our model (political party, job, subject, etc.) (Barbara)

#### *By December 6: Testing*
- Testing our model, implementing the weighted features, to see what the accuracy is on fake news detection (Barbara, Joyce)
- Find a new, small dataset which we can annotate and also use to test whether the model also performs well outside its mother dataset (Eva)

#### *By December 13: Visualisation*
- Data visualisation:
  - visualising all our findings in nice figures (Eva, Barbara)
- Wrapping up the project (Joyce)

## Final Contribution
- Coming up with the project idea and making a project plan (Eva, Joyce, Barbara)
- Creating matrices of the dataset to which later LR could be applied (Barbara) 
- Binomial regression and feature importance (Joyce)
- Multinomial regression and feature importance (Barbara) 
- Including the sentiment analysis (Joyce) 
- Applying SVD and TfIdf (Joyce) 
- Testing the binomial model on new dataset (Joyce) 
- Filtering words and lemmatization (Barbara) 
- Commenting and layout notebooks (Joyce & Barbara)
- Updating the documentation in the README (Joyce & Barbara) 
- Writing the weekly updates (Barbara) 
- Writing the report (Eva)
- Creating Slides for the presentation (Eva) 

## Documentation
##### Datafiles
- `more-fake-news.csv` : this file contains some more fake news data that we will probably test our best regression model on, to see whether it performs the same on different data, this will show if the model is scalable.
- `test.tsv`: this file contains the test set of the Liar Dataset. 
- `train.tsv`: this file contains the training set of the Liar Dataset.
- `sentiment_test.csv`: this file contains the test set of the Liar Dataset, with the added sentiment values calculated in `sentiment-analysis.ipynb`. 
- `sentiment_train.csv`: this file contains the training set of the Liar Dataset, with the added sentiment values calculated in `sentiment-analysis.ipynb`. 

##### Notebooks
Our main code can be found in the notebooks `binomial-LR.ipynb`,`Multinomial-LR.ipynb` and `sentiment-analysis.ipynb`. The results mentioned in the report can be all found in `binomial-LR.ipynb`and `Multinomial-LR.ipynb`. However, we kept some of the other files in our repository, to be able to see a bit more of the process of our project. Thus looking into these extra files is not necessary to read our report.  
- `binomial-LR.ipynb`: Here we show a binomial implementation of the logistic regression on fake news classification. It contains implementation of countvectorizer, feature importance analysis, experimentation with dimensionality reduction, and an implementation of tfidf vectorizer. Furthermore it contains a logistic regression model trained on data including the sentiment and the political score. Finally the model is tested on a new fake news dataset and the results of all the different binomial models are presented. 
- `Multinomial-LR.ipynb`: Here we implemented multinomial Logistic Regression in a few different ways. We used Count Vectorizer and tf-idf Vectorizer. Furthermore we applied SVD and did some filtering and lemmatization of the statements. We also included the addition of the new features (incl. political score) to our data. At the end of the notebook we present all the accuracies of the different multinomial models.   
- `sentiment-analysis.ipynb`: Here we calculated the positive and negative sentiment scores of the statements in our train and test dataset, and created new datasets with this score added. We used SentiWordNet for this sentiment analysis.
- `update-1.ipynb`: Here we have created a count vector of the training set, tried some regression, but we just split the training data up in a training and test part, since we did not know how to fit the test data on the model yet. Therefore, the accuracy is pretty low.
- `Multinomial_LR_Matrices.ipynb`: Here we implemented multinomial logistic regression by first creating matrices containing the frequencies of the occuring words. However, we did not include this code in `Multinomial-LR.ipynb` as using Count Vectorizer appeared to be a way more efficient way to implement multinomial logistic regression in a similar way. 
- `Filtered_Multinomial_LR.ipynb`: Here we applied filtering to the multinomial logistic regression model created in `Multinomial_LR_Matrices.ipynb`. We filtered out stopwords numbers and words that only occured once in the train dataset. As we ended up using Count Vectorizer rather than our own created matrices for multinomial logistic regression, this code is also not included in `Multinomial-LR.ipynb`. However, we saw here, that filtering out words that only occured once in the train dataset made the accuracy much lower. We therefore only filterd out stopwords and numbers in `Multinomial-LR.ipynb`.
