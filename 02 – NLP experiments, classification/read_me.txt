Classic ML – Naïve-Bayes –classification

00 PART
When it came to classification (05 part) by utilizing Naïve Bayes Classifier,
I undrstood that I do not have labels in my data, that is why I made comparison
of several APIs and opted for Google Bard API (PaLM 2) for Survey Answer Classification .
It will have 3 options:
- HIGH: If the answer is fully correct and detailed.
- MEDIUM: If the answer is somewhat correct but lacks detail.
- LOW: If the answer is incorrect or unrelated.

By adding both labels, you get a detailed view of:

How correct each answer is (High/Medium/Low)
How participants' knowledge changed after the post-survey (Improved/Same/Declined)


1️⃣ Use Google Bard API (PaLM 2) to evaluate correctness of each response:

HIGH → Fully correct and detailed.
MEDIUM → Somewhat correct, lacks details.
LOW → Incorrect or unrelated.

2️⃣ Compare pre-survey and post-survey answers to measure change in performance:

IMPROVED → Post-survey score is higher than pre-survey.
SAME → No change in correctness.
DECLINED → Post-survey score is lower than pre-survey.



This classification will help us to understand how well participant learnt during the user study.
After that I had to run all code snippets again because the original dataset was changed.
Why I have so many snippets? I want to test different types of tokenization

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