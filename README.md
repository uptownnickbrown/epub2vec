Goals of this script:

* Accept a directory of .epub books as input
* Generate a word2vec model using the corpus of words available in those books as a domain-specific training set.
* Analyze the books (using paragraphs?) to figure out the average (or something?) vector for each passage/paragraph/sentence.
* Using k-means clustering or similar, find the "most similar paragraphs" by word2vec-based "paragraph vectors".
* Output lists of highly relevant passages that could be linked to each other, presented side by side, etc...something interesting.

To run:

* Include .epub files in the root directory alongside this script...run it.

Background info:

* This script owes a lot to this set of Kaggle NLP tutorials: https://www.kaggle.com/c/word2vec-nlp-tutorial
* Specifically for more info on tweaking the word2vec hyperparameters see this page: https://www.kaggle.com/c/word2vec-nlp-tutorial/details/part-2-word-vectors