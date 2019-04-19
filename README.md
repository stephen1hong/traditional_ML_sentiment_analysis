# traditional_ML_sentiment_analysis


Step 1: Exploring the data!
The dataset we are going to use is very popular among researchers in Natural Language Processing, usually referred to as the IMDb dataset.
It consists of movie reviews from the website imdb.com, each labeled as either 'positive', if the reviewer enjoyed the film, or 'negative' 
otherwise.

Step 2. Preprocessing
As you might have noticed in the sample reviews, our raw data includes HTML. Therefore there are HTML tags that need to be removed. We also
need to remove non-letter characters, normalize uppercase letters by converting them to lowercase, tokenize, remove stop words, and stem 
the remaining words in each document.

Step 3: Extracting Bag-of-Words features¶
Now that each document has been preprocessed, we can transform each into a Bag-of-Words feature representation. Note that we need to create 
this transformation based on the training data alone, as we are not allowed to peek at the testing data at all!

The dictionary or vocabulary $V$ (set of words shared by documents in the training set) used here will be the one on which we train our 
supervised learning algorithm. Any future test data must be transformed in the same way for us to be able to apply the learned model for
prediction. Hence, it is important to store the transformation / vocabulary as well.

Step 4: Classification using BoW features
Now that the data has all been properly transformed, we can feed it into a classifier. To get a baseline model, we train a Naive Bayes
classifier from scikit-learn (specifically, GaussianNB), and evaluate its accuracy on the test set.

Step 5: Switching gears - RNNs
We just saw how the task of sentiment analysis can be solved via a traditional machine learning approach: BoW + a nonlinear classifier.
We now switch gears and use Recurrent Neural Networks, and in particular LSTMs, to perform sentiment analysis in Keras. Conveniently, Keras
has a built-in IMDb movie reviews dataset that we can use, with the same vocabulary size.
