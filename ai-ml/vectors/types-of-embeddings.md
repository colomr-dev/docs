---
description: https://open.substack.com/pub/mlpills/p/issue-58-embeddings-in-nlp
---

# Types of embeddings

Embeddings have emerged as a powerful technique for representing linguistic units, such as words, sentences, or entire documents, as dense numerical vectors in a high-dimensional vector space. These embeddings capture the semantic meaning and relationships between different linguistic entities, allowing them to be processed and analyzed using machine learning techniques.

#### **Types of Embeddings**

There are four main types of embeddings in NLP:

1. **Token Embeddings**: These are vector representations of tokens, which can be characters, subwords, or other text units. Token embeddings are particularly useful in languages with complex morphology or when handling out-of-vocabulary words. Models like BERT use token embeddings to represent subword units.
2. **Word Embeddings**: These are dense vector representations of individual words, where words with similar meanings or contexts are represented by similar vectors. Popular word embedding techniques include Word2Vec, GloVe, and fastText.
3. **Sentence Embeddings**: These represent entire sentences or phrases as single vectors, capturing the overall meaning and context of the sentence. Sentence embeddings can be derived from word embeddings using methods like averaging or more advanced techniques like transformers or recurrent neural networks.
4. **Document Embeddings**: Similar to sentence embeddings, these represent entire documents or longer pieces of text as single vectors.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

#### **Learning Embeddings**

Embeddings are typically learned from large text corpora using unsupervised or self-supervised learning methods, allowing the model to capture the statistical patterns and co-occurrences of words in the training data.

**Unsupervised Learning Methods**

Unsupervised learning methods for learning embeddings do not require any labeled data or explicit supervision. Instead, they rely on the statistical properties and patterns present in the raw text data itself. The most common unsupervised methods for learning word embeddings are:

* **Word2Vec**: Includes two models, Skip-gram and Continuous Bag of Words (CBOW), which learn word embeddings by predicting nearby words given a target word (Skip-gram) or predicting the target word given its context (CBOW).
* **GloVe (Global Vectors)**: Learns word embeddings by factorizing a global word-word co-occurrence matrix, capturing the statistical information about word co-occurrences in the entire corpus.

These methods leverage the distributional hypothesis, which states that words appearing in similar contexts tend to have similar meanings, to learn meaningful word representations.

**Self-Supervised Learning Methods**

Self-supervised learning methods are a variation of unsupervised learning, where the input data itself is used to generate supervised signals for training the model. Some examples include:

* **Masked Language Modeling (MLM)**: Used in models like BERT, this technique masks some words in the input text and trains the model to predict the masked words based on the context.
* **Next Sentence Prediction (NSP)**: Also used in BERT, this task trains the model to predict whether two given sentences are consecutive, helping it capture relationships between sentences.
* **Contrastive Learning**: Methods like SimCLR and CERT learn embeddings by maximizing the similarity between different views (augmented versions) of the same input while pushing apart views from different inputs.

Self-supervised methods can leverage large amounts of unlabeled data and learn rich representations that can be fine-tuned for various downstream NLP tasks.

#### **Advantages of Embeddings**

The key advantage of using embeddings is that **they capture semantic and contextual information about words, phrases, or documents in a dense, low-dimensional representation**. This significantly improves the performance of NLP models and simplifies the feature engineering process. By encoding linguistic units as numerical vectors, embeddings allow NLP models to leverage powerful tools of linear algebra and machine learning for tasks such as text classification, sentiment analysis, machine translation, and information retrieval.

#### **Embeddings in Large Language Models (LLMs)**

LLMs, such as BERT and GPT, leverage embeddings to process and understand text. Here’s how embeddings function within LLMs:

**Initial Text Representation**

* **Tokenization**: Text is split into smaller units like words or subwords. Each token is then converted into an embedding vector.
* **Contextual Embeddings**: LLMs generate embeddings that take into account the context, allowing the model to grasp nuanced meanings of words.

**Model Input and Output**

* **Model Input**: Embeddings serve as inputs to the neural network of the LLM, which processes these vectors through multiple transformer layers to understand and generate text.
* **Output Embeddings**: The final layer of the LLM produces output embeddings, representing the model’s understanding of the input text, which can be converted back to human-readable text.

#### **Embeddings in Retrieval from Vector Databases**

Vector databases are **optimized for storing and searching large collections of embeddings**, facilitating efficient text retrieval. Here’s how embeddings are used in this context:

**Indexing**

* **Embedding Generation**: Text documents or snippets are converted into embeddings using an LLM or other embedding models.
* **Vector Storage**: These embeddings are stored in the vector database, forming an index that can be efficiently searched.

**Query Processing**

* **Query Embedding**: A user’s search query is converted into an embedding vector using the same model that generated the document embeddings.
* **Similarity Search**: The query embedding is compared with stored document embeddings using metrics like cosine similarity or Euclidean distance. The most similar vectors (documents) are retrieved.

**Applications**

* **Semantic Search**: Instead of keyword matching, search retrieves documents based on semantic similarity, improving relevance.
* **Recommendation Systems**: Embeddings help recommend items by finding similar items in the embedding space.
* **Question Answering**: Embeddings assist in retrieving relevant paragraphs or documents likely to contain the answer.

#### **Workflow Example**

1. **Data Ingestion**
   * Text data (articles, product descriptions) is processed to generate embeddings using an LLM.
   * These embeddings are stored in a vector database.
2. **User Query**
   * A user inputs a query.
   * The query is converted to an embedding using the same LLM.
3. **Retrieval**
   * The vector database performs a similarity search to find the closest embeddings to the query embedding.
   * The corresponding documents or text snippets are retrieved and presented to the user.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### **Conclusion**

Embeddings are a powerful tool in NLP, allowing for the efficient and effective processing of text. They enable LLMs to understand and generate human language and facilitate semantic search and retrieval in vector databases. By transforming text into high-dimensional vector representations, embeddings enhance a wide range of applications, from search engines to recommendation systems and question-answering platforms. Understanding and leveraging embeddings is key to advancing the capabilities of modern NLP systems.
