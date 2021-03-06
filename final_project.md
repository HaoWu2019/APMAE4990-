# Final Project Grading Outline

Below is the outline for the grading of the final project. Your main goal is to have a public web server I can go to such as `http://yourname.somedomain.com`. 

**Broad requirements:**
- Each team member has pushed their contributions to Github. 
- A notebook is pushed along with the code base that summarizes your work on the steps below. 

**Specific Requirements:**

- A 5-10 minute presentation of your work which will include: motivation, using the app, notebook presentation. **Note:** For CVN students, please provide a youtube link to a video (or upload it to your Github). 
- An iPython notebook which shows your analysis/work. 
- The full code base in the same Github repo. 
- Provide a link in the projects worksheet to your completed project. 


# Data Engineering and Machine Learning

Below is a breakdown of the grading scheme. 

## Data Gathering and Preparation (30%):

**Data gathering/preprocessing** (may not be as relevant depending on project):

- Did you find ways of processing your data to make the problem at hand more tractible/easier

**Examples:** image formatting, string matching.

**Data integrity checks (10%):** 

- Did you account for missing values and outliers? 
- Is there information leakage? ie. a variable which is actually inferred by the outcome (eg. predicting a user likes a movie using the fact that they've liked that movie before).
- Are some variables non-sensical or redundant? (ie. if you see "Male" sometimes and "M" other times, or numerical values in the gender column).

**Feature Engineering (15%):** 
- Did you convert categorical features into one hot encoded dummy variables? 
- Was there an opportunity to make a new variable from the old ones that has more predictive power? (ie. if you are predicting the Titanic survivor problem and Cabin seems to be predictive but it's sparse, maybe replacing it with a binary variable "had a cabin or not" is better). 

**Standarization (5%):** 
- Did you standardize your variables properly?

**Use of databases (BONUS) (+15%):** If you use any kind of SQL database for your data storage/retrieval (MySQL, Postgres, etc).


## Model Selection, Comparison and Cross Validation (60%):

### Supervised Problem (predicting an outcome such as a recommendation, stock price, disease, etc):

**Exploratory Analysis (10%):** 
- Did you analyze the features and how they are related to the outcome variable? (regression: scatter plots, classification: conditional histograms). 
- Did you look at correlations or chi-squared if the variables are categorical? 
(https://en.wikipedia.org/wiki/Chi-squared_test. But feel free to find a package that does this automatically). 

**Model Selection (50%)**: 
- Did you randomly split your data into training and testing data (20%, 80%) using k-fold cross validation?
- Did you perform regularization (very important if the number of features is large!)? Why did you use L^1 or L^2? I expect to see use of GridSearchCV for this with at least 2 fold cross validation.
- Did you try out various models and see which one performed best? (You don't need to check all of them, but for classification/regression you should at least try a couple. **DID YOU TRY OUT THE SIMPLEST MODEL FIRST?**

**Examples:**

*Classification:* Logistic Regression and Random Forest Classification. (Use ROC for evaluation)

*Regression:* Linear Regression and Random Forest. (Use R^2 for evaluation)

*Recommendation Engines:* Item/Item, User/User, Matrix Factorization. (Use precision/recall for evaluation).

*Image classification/segmentation:* Try neural nets and simple logistic regression. 

*Time Series:* Auto-regressive models with different distributions (Poisson, Normal, etc). 

**I would like to see a performance comparison of at least two different models.**

### Unsupervised Problem (extracting meaning from text, finding similar images/documents, etc):

**Model Selection /Exploration (60%)**:
- Did you analyze features and see relationships? 
- Did you do dimensionality reduction and try making scatter plots of your data?
- Did you then investigate properties of those clusters?
- Did you check if the groups have comparable numbers of points, similar covariances? For instance, if you did K-means, did you check for the kinds of behavior we covered in class?
- Based on the above, did you try various clustering algorithms appropriate for this problem? 
- Are the clusters stable? (ie. when you take random subsets of your data, do you get similar clusters? When you choose different initial conditions, do you get the same result?
- Do you have interpretations for the clusters you found? Can you justfiy the number of clusters you selected?

**Examples:**

- *Word embeddings/Topic models:* LDA, word2vec with K-means, GMM, DBSCAN. 
- *Recommendations:* If you don't have any validation data, cosine similarity is a good start. Try item/item, user/user,  etc. Did you account for high dimensionality? 

**Ideally you can find a way of validating your model in a supervised way. If this isn't possible, try to show that your clusters are stable, and make sense by investigating what they say. 

## Design and Strategy (10%)

## Problem Statement and Usefuleness: (5%)

Is the problem clearly stated and motivated? Is this something useful or is it contrived?

## User Experience (5%):

Is the website relatively easy to use? Does it accept some kind of user input and then apply a model, and return
the user information?

## Extra interesting ideas (BONUS 10-20%):

This isn't necessary, but I'm leaving this here to allow for interesting and novel modeling/strategy approaches that I may not have thought of. 

- Did you use a novel modelling approach for your problem that required coding something by hand?
- Did you use clever processing or hierechcal models for your problem to customize for your context?







 
