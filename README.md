# nlp-authorship_attribution
NLP based authorship identification of the greatest novels of the 20th century.

Here I analyzed the writing styles of 12 authors of the 20th century based on their most prominent novels. It was interesting to me whether the works of these authors can be correctly identified. It's difficult to distinguish between writing styles because the writing style of the same author may change over time. Also, some authors write their novels in different genres, which makes distinguishability even harder.


I split each book into chunks of 2000 words to get a larger amount of the training examples for consistency. After data preprocessing steps, I built a word frequency matrix (tf-idf) that highlights moderately rare words in a document. After that, I applied various statistical and machine learning methods to treat this problem as a classification problem. The text classification process usually includes the following steps: (1) data collection, (2) data analysis and labeling, (3) feature construction, weighting, and selection, (4) ML model selection and training, and (5) evaluation of the results. 

The matrix obtained from the corpus was sparse and had about 5000 columns, each corresponding to a particular word. I considered unigrams and bigrams that are contained in at least 50 documents and less than 70% of documents. Then I applied PCA to this vectorizer transformer to speed up training and combine words that are similar into the same vector space. After that, I used different machine learning methods, such as Logistic Regression, Random Forest, SVM, Multinomial Naive Bayes to the training set. I also considered other accuracy metrics (precision, recall, f1 score) that are more appropriate to use when working with imbalanced data. I've implemented two approaches, one uses PCA, and the other does not.


An interesting question to ask is how many dominant topics can capture the themes of all of these novels? I applied the Latent Dirichlet Allocation model that treats each document as a mixture of topics, and each topic as a mixture of words. There are only 4-5 main topics across 72 novels. Not only the texts of the same authors can be similar to each other, but the novels of two different authors can be very close thematically to each other. 



