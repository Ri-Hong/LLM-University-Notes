# Module 1.5 Semantic Search

Semantic search is the process of searching based on the meaning of the sentence instead of the word frequencies (Lexical search). This is done using sentence embeddings. The query is turned into an embedding and the "nearest neighbour" technique to perform the search. 

## Nearest Neighbour
Give the query in the form of an embedding, the answer is selected based on its proximity of its embedding to the query's embedding. The closest sentence embedding to the query embedding is selected. In reality though, similarity (See Module 1.2) is used instead of absolute distance. Recall that a similarity score is high when two words/sentences are similar and low when dissimilar.

## Problems with Nearest Neighbour
### 1. Speed
In order to do find the most similar sentence in a pool of sentences, each sentence must be checked. In a dataset of 4 questions and 4 answers, There would need to be 4^2 searches done to find the answer to every question.

### Solutions to 1. 
 - Inverted File Index (IVD), which works by clustering the data then searching
 - Hierarchical Navigable Small Worlds (HNSW): Start with less points, search there. Then add more and iterate

### 2. Multiple answers
If we have one question like, "Where was the last world cup?" and we have three possible responses:
- The previous world cup was in Russia
- The last world cup was in Qatar
- The world cup is in the moon
 
 All three responses have similar embeddings to the question but only the second one is correct. How do we ensure that the second one is selected? 

### Solutions to 2. 
### Reranking
We have a model that is trained to see how good a question-answer pair is. This model is trained on a dataset of correct and incorrect question-answer pairs. It is trained to give a high score to correct answers and a low score to incorrect answers.

### Positive and Negative Pairs
We have a set of good answers and a set of bad answers. Good answers will form a positive pair with the question and bad answers will form a negative pair. We will adjust the embeddings as follows:
- negative pairs will be moved further apart
- positive pairs will be moved closer together

That way, there is a higher chance for the correct answer to be chosen.