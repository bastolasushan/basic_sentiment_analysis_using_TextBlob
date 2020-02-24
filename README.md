# Basic sentiment analysis using TextBlob

We are using a library called TextBlob for sentiment analysis. 

### What is TextBlob?
TextBlob is a Python (2 and 3) library for processing textual data. It provides a simple API for diving into common
natural language processing (NLP) tasks such as part-of-speech tagging, noun phrase extraction, sentiment analysis, 
classification, translation and more.

```python

from textblob import TextBlob

text = """ The titular threat of the Blob has always struck me as the ultimate movie monster: an instatiably hungry, amoeba-like mass
able to penetrate virtually any safeguard, capable of--as a doomed doctor chillingly describes it -- " assimilating flesh on contact.
Snide comparisons to geltain be damned, it's a concept with the most devastating of potential consequences, not unlike the grey goo
scenario proposed by technological theorists fearful of artificial intelligence run rampt. """

blob = TextBlob(text)
blob.tags 
blob.noun_phrases

for sentence in blob.sentences:
  print(sentence.sentiment.polarity)
 
# 0.060
# - 0.341


```
  
  
I recommend you to install NLTK
```
pip install nltk
```

### Import the libraries
```
# Import the libraries

from textblob import TextBlob
import nltk
from newspaper import Artice

```


### Get a sentiment of text from a website
```Python
url = 'http://everythingcomputerscience.com'
article = Article(url)
```

### Do some NLP

```Python
article.download()
article.parse()
nltk.download('punkt')
article.nlp()

```


### Get summary of the article
```Python
text = article.summary

# Print the text
print(text)

```



### Create a TextBlob object

```Python

obj = TextBlob(text)

# This returns a value between -1 and 1
sentiment = obj.sentiment.polarity
print(sentiment)


if sentiment == 0:
  print('This text is neutral')
elif sentiment > 0:
  print('The text is positive')
else:
  print('The text is negative')
 
```

