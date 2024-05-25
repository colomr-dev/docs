---
description: https://mlpills.substack.com/p/issue-59-retrieval-methods-i
---

# Retrieval methods

Retrieval refers to the process of finding and extracting relevant information or documents from a large collection or database in response to a query or information need. It is a fundamental task in information retrieval systems, search engines, and question-answering applications. Effective retrieval methods aim to identify and return the most pertinent and useful information to the user's query, filtering out irrelevant or redundant content.

Similarity search and maximum marginal relevance are two basic, but important retrieval methods used in vector databases.

Similarity search retrieves documents most semantically similar to a given query based on their vector embeddings, enabling efficient and relevant information retrieval. Maximum marginal relevance builds upon similarity search by balancing relevance and diversity, retrieving documents that are both similar to the query and different from each other, providing a comprehensive set of results covering various aspects of the query topic.

Let’s learn more about them!

#### Similarity Search

Similarity search involves retrieving documents that are most similar to a given query based on vector embeddings. These embeddings represent the semantic meaning of the text. By converting text into high-dimensional vectors, similarity search algorithms can measure the closeness of these vectors to identify relevant documents.

It is used to find documents that closely match the content of the query. This is particularly useful in scenarios where exact keyword matching is insufficient and the context or meaning of the query needs to be considered.

**Advantages**:

* High relevance to the query due to semantic understanding.
* Efficient for large datasets when using vector databases like Chroma.
* Reduces noise by focusing on semantic similarity rather than keyword occurrence.

**Applications**:

* Document search in large databases.
* Information retrieval in customer support systems.
* Content recommendation engines.
* Medical record retrieval where symptoms and diagnoses need to be matched semantically.

**Example**: Given a query about "types of edible berries found in North America", the system retrieves documents discussing various edible berries such as blueberries, raspberries, and strawberries, including their habitats and nutritional benefits.

```
question = "types of edible berries found in North America"
docs_ss = vectordb.similarity_search(question, k=3)
```

* `similarity_search()` is a method call on the `vectordb` object, which is an instance of a vector database.
* `k=3` specifies the number of top similar documents to retrieve. In this case, it will return the three most similar documents based on the vector embeddings of the query and the documents in the vector database.

The `similarity_search` method works as follows:

1. The question is converted into a vector embedding, as specified when initializing the `vectordb` object.
2. The vector database (e.g., Chroma, Qdrant, Pinecone…) compares the query vector embedding with the vector embeddings of all the documents in the database.
3. The database calculates the similarity (e.g., cosine similarity or dot product) between the query vector and each document vector.
4. The database returns the top k documents (in this case, 3) with the highest similarity scores, representing the most relevant documents to the query.

The `docs_ss` variable will contain a list (or a similar data structure) of the top 3 most similar documents, which can be further processed or displayed to the user.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

[Similarity search](https://substack.com/redirect/f061ea16-e0c0-468c-a293-f9f9d064a195?j=eyJ1IjoiM213enIwIn0.jOOrL\_ZVtwmFeVl9SRII-GNj-lSweOtiZkAMjS2JOCU) using vector embeddings allows for semantic understanding of the query and documents, enabling more relevant and contextual document retrieval compared to traditional keyword-based search methods.

#### Maximum Marginal Relevance

Maximum Marginal Relevance (MMR) aims to balance relevance and diversity in search results. It reduces redundancy by selecting documents that are both relevant to the query and different from each other. MMR uses a combination of similarity scores and novelty scores to rank documents, ensuring a diverse set of results.

It is used to provide a more comprehensive set of results that cover different aspects of the query. This is particularly useful in exploratory searches where the user benefits from a variety of perspectives.

**Advantages**:

* Reduces redundancy in search results.
* Enhances the user experience by providing diverse information.
* Ensures broader coverage of the query topic.

**Applications**:

* Academic research tools where diverse perspectives on a topic are needed.
* News aggregation services.
* Market research where varied opinions and data points are valuable.

**Example**: When querying about "sustainable energy solutions", MMR ensures that the retrieved documents cover various aspects such as solar energy, wind power, and bioenergy, providing a broad understanding of sustainable energy technologies.

```
question = "sustainable energy solutions"
docs_mmr = vectordb.max_marginal_relevance_search(question, k=3, fetch_k=20)
```

* `maximum_marginal_relevance_search()` is a method call on the `vectordb` object, which is an instance of a vector database.
* `k=3` specifies the number of top relevant and diverse documents to retrieve. In this case, it will return the three most relevant and diverse documents based on the vector embeddings of the query and the documents in the vector database, as well as the novelty scores calculated by the MMR algorithm.
* `fetch_k=20` is an additional parameter that specifies the number of candidate documents to consider for the MMR algorithm. In this case, it will fetch the top 20 most similar documents to the query based on vector embeddings, and then the MMR algorithm will select the 3 most relevant and diverse documents from this pool of 20 candidates.
