# Isaac Brassard
- Vectorizer: Count Vectorizer 
- Classifier: Svm
- Preprocessing: Wordnet Lemmatization, no numbers 

- F-score : 0.69
- Accuracy score: 0.95

This is my first model; a pretty standard binary SVM classifier with a Count Vectorizer.
The output should be interpreted as 1 = "indicates start of ceasefire".
I suspect that it is a bit too conservative, and might miss quite a few sentences.
:warning: Note that the model is only trained on sentences containing a  match to `([Cc]ease-?fire|[Tt]ruce|[Aa]rmistice)`.
Therefore i would prefilter sentences before applying the model, to avoid having to sift through too much noise.
