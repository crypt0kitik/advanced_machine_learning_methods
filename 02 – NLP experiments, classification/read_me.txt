Classic ML – Naïve-Bayes –classification
Neural network approach – BERT or some other base model used


Ideas for optimizations for this exercise project (optional):
 Stopword removal and other text data processing/optimization 
methods (e.g. n-gram)
 Stemming or lemmatization
 Data augmentation (synonym replacement etc.)
 Different vectorization algorithms, like TfidVectorizer 
 Different tokenization strategies and methods
 Hyperparameter and algorithm (also neural network) tuning
 Different base models / embeddings
o DistilBERT, roBERTa, ALBERT, FastText, Word2Vec, GloVe etc.


Preprocess the Text Data  
•	Remove stopwords and perform text cleaning.  
•	Apply lemmatization or stemming (I opted for lemmatization because it is a smarter reduction)
•	Experiment with different tokenization strategies.  
•	Consider using TF-IDF or Word2Vec/GloVe embeddings.  


1. Word Tokenization (SpaCy)
2. Subword Tokenization (BPE)
3. Sentence Tokenization (SpaCy)
4. BERT Tokenization (WordPiece)
5. Tiktoken (OpenAI, GPT)
6. Whitespace Tokenization (Simple but Fast)

Remove stopwords
https://www.geeksforgeeks.org/removing-stop-words-nltk-python/

Lemmatization Approaches
https://www.geeksforgeeks.org/python-lemmatization-approaches-with-examples/