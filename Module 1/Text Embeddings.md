# Module 1.1 Text Embeddings

A word embedding is a way for computers to understand their relationship between different words. 

If we visualize each word in a 2D plane, similar words would be located close together (have closer coordinates) and different words would be place further apart.

A simplification is to consider each axis/dimension of an embedding as a property. I.e. x axis captures the age and the y axis captures the size.

![Image](../Assets/TextEmbeddings.png "TextEmbeddings.png")

Scaling this up, LLMs generally have many many more "dimensions"; Cohere has 4096.
