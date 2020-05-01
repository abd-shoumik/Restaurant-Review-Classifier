# Restaurant-Review-Classifier

**This is a simple NLP project based on the
[NLP section of A-Z Machine Learning Course on Udemy](https://www.udemy.com/course/machinelearning/learn)**

## Steps I folllowed:
* Importing the libraries and dataset
* Text cleaning or pre-processing
* Tokenization
* Creating bag of words model
* Splitting Dataset into training set and test set
* Fitting to a predictive model
* Predicting final result
* Accuracy Measurement
* **Deploying it in heroku**

## Steps Description

- **Importing the libraries and dataset**
1. Import `numpy`,`pandas` and `matplotlib`
2. Import the dataset Restaurant_Reviews.tsv in your editor.We  are using `.tsv` file here as we want to seprate the words by spaces. We always use `.csv(comma seperated value)` file as our dataset. But comma can appear in reviews ,as a result we can get error in separating columns if we use comma as delimiter.So,we use tab for sepation that's why we will import `.tsv`
 
- **Text cleaning or pre-processing**
 1. Remove Punctuations, Numbers: Punctuations, Numbers doesn’t help much in processong the given text, if included, they   will    just increase the size of bag of words that we will create as last step and decrase the efficency of algorithm.
 2. Stemming: Take roots of the word
 3. Convert each word into its lower case: For example, it useless to have same words in different cases (eg ‘good’ and ‘GOOD’).

- **Tokenization**
 Tokenization, involves splitting sentences and words from the body of the text.
 
- **Creating bag of words model** 
 1. Take all the different words of reviews in the dataset without repeating of words.
 2. One column for each word, therefore there are going to be many columns.
 3. Rows are reviews
 4. If word is there in row of dataset of reviews, then the count of word will be there in row of bag of words under the     column of the word.

 For this purpose we need `CountVectorizer` class from `sklearn.feature_extraction.text`.

- **Splitting Dataset into training set and test set**
 Splitting Corpus into Training and Test set. For this, we need class `train_test_split` from `sklearn.model_selection`. Split can be made 70/30 or 80/20 or 85/15 or 75/25, here I choose 75/25 via “test_size”.
 
- **Fitting to a predictive model**
  1. Here I used `NaiveBayesClassifier` as I got best accuracy out of it.
  Fit the model via `.fit()` method with attributes X_train and y_train.

- **Predicting final result**
 - `y_pred = model.predict(X_test)` 

- **Accuracy Measurement**
I used the naivebayes classifier which gave me an accuracy of **_73 percent_**.There are 1000 reviews in the dataset.If you can train it  with bigger dataset and do parameter tuning ,this accuracy will improve.

- **Deploying it in heroku**
  In **_review_app.py_** I have taken pickled data from `text_transform.pkl` and `nlp_review_classifier.pkl` 
and created the path of rendering `home.html` & `result.html` template.

**Then, I have deployed it in heroku platform using this github repository which you can visit at
[restaurantreviewclassifier](https://restaurantrreviewclassifier.herokuapp.com/)**

*** If you want to deploy this in your heroku account,make sure you have all the files uploded in this git repo in your
github repository ***




 
 
 

