# **Email Spam Filtering: Implementation with Python and Scikit-learn**

Spam filtering is a document classification task which involves classifying an email as spam or non-spam (a.k.a. ham) mail. Spam box in your Gmail account is the best example of this.

The Dataset used in training the model can be found [here](https://www2.aueb.gr/users/ion/data/enron-spam/). The Enron-Spam in pre-processed form was used. It contains five folders of which each folder contains a spam and a ham folder. Each spam and ham folder contains email files. I extracted all these email files (33,722) into a single directory on googlecolab. 

## Steps taken to building the Spam_filtering model

1. Preparing the text data
2. Creating Total-Word List
3. Feature Extraction Process
4. Training the Classifier
5. Checking Performance

### **1. Preparing the text data**
A random sample of 8000 email files was selected from the total number of email files to prevent the RAM from running out of memory during computation. Each email file contains messages. As data (messages) are in preprocessed form, Text cleaning was performed on the messages by creating a function called "format_email_to_messages". Text cleaning involved dropping punctuation marks from words and messages in general, removing words which are not very meaningful in deciding whether a message is a spam or not (words with length less than or equal to 2), removing numbers from messages, lemmatization to avoid having words and their inflected forms registered as different words. The processed/important words from the messages in each email were returned as a list of strings from the function.

A Target label List was also created with value 1 if message is spam and value 0 if it is not spam by checking for "spam" and "ham" in each emails file's name.

### **2. Creating a set of Total-Words**
A Set was created containing all the possible words in the email files without duplicates. This List was used for feature extraction.

### **3. Feature Extraction Process**
The next stage was feature extraction. A word Count Vector function was created by comparing each word in the Total-word Set with the words in each message (list of strings). If the word exist in the message, the frequecy of such word in the message is returned, else it returns zero. 

### **4. Training the Classifier**
Here I used Scikit-learn ML library to train Naive Bayes Classifier. The Dataset (The word count vector features and target Label) was split into training data and test data in the ratio 70:30 and the training data was used to train Naive Bayes classifier. Naive Bayes classifier is a conventional and very popular method for document classification problem. It is a supervised probabilistic classifier based on Bayes theorem assuming independence between every pair of features. 

### **5. Checking Performace**
After the classifier was trained, I checked for the performace of the model against the test data. Confusion matrix was one of the metrics used.

