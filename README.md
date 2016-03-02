### EPUB2Vec

#### Goals of this script

* Accept a directory of .epub books as input
* Generate a word2vec model using the corpus of words available in those books as a domain-specific training set.
* Analyze each paragraph from those books to figure out an "average word" / "paragraph" vector for each passage/paragraph.
* Using k-means clustering, find the "most similar paragraphs" by clustering on "paragraph vectors".
* Output lists of highly relevant passages that could be linked to each other, presented side by side, etc...something interesting.

#### Example Output

Some clusters as output from early trial runs (each bullet is a paragraph included in the cluster):

##### See this other thing...
* See common shares.
* See mortgage rate.
* See direct format.
* See alternative trading systems.
* See indirect format.
* See alternative trading systems.
* See mortgage rate.
* See special purpose entity.

##### Bayesian equations about orders"
* P(Order 1 executes | Order 2 executes) = 1
* P(Order 1 executes and Order 2 executes) = P(Order 1 executes | Order 2 executes)P(Order 2 * executes) = 1(0.25) = 0.25
* P(Order 1 executes or Order 2 executes) = P(Order 1 executes) + P(Order 2 executes) − P(Order 1 * executes and Order 2 executes) = 0.35 + 0.25 − 0.25 = 0.35
* P(Order 1 executes and Order 2 executes) = 0.25 = P(Order 2 executes | Order 1 executes)P(Order 1 executes)
* 0.25 = P(Order 2 executes | Order 1 executes)(0.35)

##### Descriptions of types of bonds or other assets"
* Monies issued by national monetary authorities.
* Bonds secured by specific types of equipment or physical assets.
* Holding by the central bank of non-domestic currency deposits and non-domestic bonds.
* Bonds issued by the UK government.
* A type of non-sovereign bond issued by a state or local government in the United States. It very often (but not always) offers income tax exemptions.
* A type of non-sovereign bond issued by a state or local government in the United States. It very often (but not always) offers income tax exemptions.
* In the United States, securities issued by private entities that are not guaranteed by a federal agency or a GSE.
* A bond issued by a government below the national level, such as a province, region, state, or city.
* A bond issued by a government below the national level, such as a province, region, state, or city.
* The most recently issued and most actively traded sovereign securities.
* The purchase or sale of bonds by the national central bank to implement monetary policy. The bonds traded are usually sovereign bonds issued by the national government.
* A bond issued by an entity that is either owned or sponsored by a national government. Also called agency bond.
* A type of central bank policy rate.
* A bond issued by a national government.
* A bond issued by a national government.
* A bond issued by a supranational agency such as the World Bank.
* Taxes that a government levies on imported goods.
* Shares that were issued and subsequently repurchased by the company.
* Shares that were issued and subsequently repurchased by the company.
* The governing legal credit agreement, typically incorporated by reference in the prospectus. Also called bond indenture.

They weren't all that good of course...

#### To run

* I highly recommend installing the anaconda Python distribution and using conda for further module installations as needed: https://www.continuum.io/downloads
* Include .epub files in the root directory alongside this script...run it.

#### Background info

* This script owes a lot to this set of Kaggle NLP tutorials: https://www.kaggle.com/c/word2vec-nlp-tutorial
* Specifically for more info on tweaking the word2vec hyperparameters see this page: https://www.kaggle.com/c/word2vec-nlp-tutorial/details/part-2-word-vectors
* Some benchmarks...processing 20 large economics textbooks on a Macbook Pro w/ 16 GB RAM, times for each step were roughly:

|Step|Time|
|----|----|
|Explode .epubs into folders|<< 1 min|
|Extract text from .xhtml files|2 min|
|Tokenize sentences from full text|1 min|
|Create word2vec model|5 min|
|Extract paragraphs and calculate paragraph vectors|1 min|
|Run k means clustering|?? min|
