# **Email Spam Filtering: Implementation with Python and Scikit-learn**

Spam filtering is a document classification task which involves classifying an email as spam or non-spam (a.k.a. ham) mail. Spam box in your Gmail account is the best example of this.

The Dataset used in training the model can be found [here](https://www2.aueb.gr/users/ion/data/enron-spam/). The Enron-Spam in pre-processed form was used. It contains five folders of which each folder contains a spam and a ham folder. Each spam and ham folder contains email files. I extracted all these email files (33,722) into a single directory on googlecolab. 

## Steps taken to building the Spam_filtering model

1. Preparing the text data
2. Creating Word List
3. Feature Extraction
4. Training the Classifier

### **1. Preparing the text data**
A random sample of 8000 email files is selected from the total number of email files to prevent the RAM from running out of memory during computation. Each email file contains messages. Text cleaning was performed on the messages using a function called "format_email_to_messages". Text cleaning involved dropping punctuation marks from words, remove words which are not very meaningful in deciding whether a message is a spam or not (words with length less than or equal to 2), lemmatization to avoid having words and its inflected forms as different words. The important words from the messages in each email were returned as a list of strings when passed to the function.

