# Module 1.2 Similarity Between Words and Sentences

If we represent each word as a vector, we can measure the similarity between two words in 2 ways. 

The first method is the **dot product**, where you take the dot product of the two vectors. The larger the result, the more similar the two words are. 

![Image](../Assets/DotProduct.png "TextEmbeddings.png")

The second method is **Cosine Distance**. Where you take the cosine of the angle between the two rays from the origin to the two points. The larger the result, the more similar the words are. An advantage of cosine distance is that the result will always be between -1 and 1.

![Image](../Assets/CosineDistance.png "CosineDistance.png")
