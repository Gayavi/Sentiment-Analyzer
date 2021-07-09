# Sentiment-Analyzer

Bigram model is a language model with a sequence of 2 words and calculate the probability of a word given the preceding word. Bigram model can be used to assign sentiment as positive or negative to given text sentences as follows when set of positive and negative polarity documents are given.

•	First preprocess the both positive polarity document and negative polarity document by removing punctuations, numbers etc..
•	Then tokenize the comments in both positive polarity document and negative polarity document to form unigram lists.
•	Then store the count of each unigram in both the positive polarity document and negative polarity document separately.
•	Then prepare bigram lists using the unigram in each comment of both the positive polarity document and negative polarity document. 
•	Then store the count of each bigram in both positive polarity document and negative polarity document.
•	Then take a comment that is needed to be assign the sentiment after preprocessing it and calculate the number of unique unigrams in it. 
•	Then prepare the bigrams for the comment.
•	Then calculate the probability of appearing each bigram in the comment in the positive bigram list

•	When the comment doesn’t appear in the training dataset, the probability becomes 0. As we cannot divide by 0, it is not possible to calculate the perplexity. Therefore we can apply Laplace smoothing technique for smoothing. In that technique we pretend that we saw each bigram one time more than we did and add 1 to all the counts.
•	Then calculate the probability of the test comment becoming a positive comment by multiplying the probability of each bigram in the test comment.
•	In the same way calculate the probability of the test comment becoming a negative comment.
•	Then compare the both probabilities and assign the sentiment for the test comment. If the probability of becoming positive is higher than the probability of becoming negative then the test comment is positive and vice versa.
•	Then perplexity can be calculated for evaluation.

Perplexity = (Probability of the test comment) -1/No of bigrams
