# semsim
##Semantic Similarity For English language 
###Calculates a score for semantic similarity

## Features


- LSTM model for calculating semantic similarity with Keras library and Quora dataset.
- Sentiment Analysis included 
- Negation identification 
- Extract keywords including noun chunks with multiple words, in addition to stop-words removal
- Classify questions types, questions starting with question words such as what, when, how much, ..etc
- Named entities detection using NLTK's tree2conlltags and Spacy
- Extract numbers
- WordNet Similarity is used with the special case of having two sentences with only one word difference which has a special function for "mini similarity check" 
- Text normalization and part-of-speech tagging

## Input
Two English text strings
 
##   Output 
### Dictionary containing: 
- Flag indicating whether the two sentences are similar or not `sim`
- Total similarity score `sim_per`
- Keywords similarity score `keywords_sim`
- Semantic similarity score `keras`
- Keywords `keywords`
- Maximum number of keywords `max_keywords`
- Named entities `entities`
- Sentiment scores `sentiment`
- Numbers `numbers`
- Question types `class` and their flag `f_class`


## Example:
###Code 

```python

from semsim import Semsim

model = Semsim()

q1="what is the cost of the shirt"

q2="how much does the shirt cost"

model.similar(q1,q2) 
```

### Output
- similar

<pre>
{'numbers': [[], []], 'keywords': [['cost', 'shirt'], ['cost', 'shirt']], 'max_keywords': 4,
'f_class': True, 'entities': [[], []], 'sentiment': [0.0, 0.0, 0.0], 'sim': 1, 'class': [5, 5],
'keras': 98.558107145608687, 'sim_per': 86.779053572804344, 'keywords_sim': 75.0}

</pre>

-----

###Code

```python

q1="what is the cost of the shirt"

q2="how much does the shirt weigh"

model.similar(q1,q2) 
```

### Output
- similar

<pre>
{'numbers': [[], []], 'keywords': [['cost', 'shirt'], ['cost', 'shirt']], 'max_keywords': 4,
'f_class': True, 'entities': [[], []], 'sentiment': [0.0, 0.0, 0.0], 'sim': 1, 'class': [5, 5],
'keras': 98.558107145608687, 'sim_per': 86.779053572804344, 'keywords_sim': 75.0}

</pre>

