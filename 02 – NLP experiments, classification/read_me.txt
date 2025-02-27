Classic ML – Naïve-Bayes –classification

01 PART - Tokenization

1. Word Tokenization (SpaCy)
2. Subword Tokenization (BPE)
3. Sentence Tokenization (SpaCy)
4. BERT Tokenization (WordPiece)
5. Tiktoken (OpenAI, GPT)
6. Whitespace Tokenization (Simple but Fast)



02 PART - PREPROCESS THE TEXT DATA 

•	Remove stopwords and perform text cleaning.  
•	Apply lemmatization or stemming (I opted for lemmatization because it is a smarter reduction)



03 PART - TOKENIZATION

1. Word Tokenization (SpaCy)
2. Subword Tokenization (BPE)
3. Sentence Tokenization (SpaCy)
4. BERT Tokenization (WordPiece)
5. Tiktoken (OpenAI, GPT)
6. Whitespace Tokenization (Simple but Fast)



04 PART - VECTORIZATION

Forms of vectorization 
-----------------------------------------------------------------------------------------------------------------------
Feature             |   TF-IDF                       |   Word2Vec                   |   GloVe                         |
-----------------------------------------------------------------------------------------------------------------------
Method              |   Frequency-based              |   Neural Network             |   Co-occurrence Matrix          |
-----------------------------------------------------------------------------------------------------------------------
Handles Synonyms?   |   ❌ No                       |   ✅ Yes                     |   ✅ Yes                        |
-----------------------------------------------------------------------------------------------------------------------
Dimensionality      |   High (Sparse)                |   Low (Dense)                |   Low (Dense)                   |
-----------------------------------------------------------------------------------------------------------------------
Training            |   Per corpus                   |   Pre-trained or trainable   |   Pre-trained                   |
-----------------------------------------------------------------------------------------------------------------------
Best For            |   Keyword Extraction, Search   |   NLP Models, Chatbots       |   NLP Models, Word Similarity   |
-----------------------------------------------------------------------------------------------------------------------

Some explanations of the table:
* Neural Network: track words with similar meanings have closer vector representations.
** Co-occurrence Matrix to learn relationships between words
*** High (Sparse) in Dimensionality: Creates a huge sparse matrix (each word has its own dimension); 
If a dataset has 10,000 words, the matrix will have 10,000 dimensions; 
Makes it memory-heavy and slow for large datasets.

In my case the best approach is a combination of TF-IDF and GloVe. 
This allows TF-IDF to handle structured, keyword-based answers and GloVe to capture semantic meaning in longer responses.



05 PART - Naïve Bayes Classifier MODEL 

Talking about the model, I started with Naïve Bayes Classifier because it does not require GPU. 

In order to proceed with Naïve Bayes Classifier, I need to have an answer key.
Therefore, I want to automatically assess correctness of survey answers without a predefined answer keym
For this I can use AI-based NLP model to evaluate responses - OpenAI’s GPT-4 / GPT-3.5.







References:
Remove stopwords
https://www.geeksforgeeks.org/removing-stop-words-nltk-python/

Lemmatization Approaches
https://www.geeksforgeeks.org/python-lemmatization-approaches-with-examples/