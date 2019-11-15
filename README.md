# TMCI_project: Fake News Detection

## Abstract
A max 150-word description of the project question or idea, goals, dataset used. What story you would like to tell and why? What's the motivation behind your project?
Motivation: to decide whether a statement is fake news or not. 

## Research questions

#### What features are associated with fake news?
- What are the sentiments and most common words used in fake news?
- How accurate can we predict fake news by creating a detector using these, and other features? 
- What approach leads to the highest accuracy in prediction? 

## Dataset: The Liar Dataset
- [The Liar Dataset](https://github.com/thiagorainmaker77/liar_dataset)
- The Liar Dataset is a dataset of short statements from politifact.com. The statements are manually labeled into ‘pants on fire’, ’false’, ‘barely true’, ‘half true’, ‘mostly true’. The dataset also contains information on the subject of the statement, who produced it, their job, party and the context. 
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

## Documentation
This can be added as the project unfolds. You should describe, in particular, what your repo contains and how to reproduce your results.
