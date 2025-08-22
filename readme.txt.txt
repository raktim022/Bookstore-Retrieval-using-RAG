--Bookstore retrieval--


One of the most effective approaches for the ML focus problem is to create two different databases, and use the individual book rows to create documents, with name of the book as the content, and other information about the book such as author, publisher, rating, price etc as metadata for the books, so that when a user asks for a book based on indirect information about the book, the retriever can retrieve the correct books even if the user does not mention the book they are looking for.

We create a RAG based architecture as follows:

Input: two bookstore datasets with different schema.
-Used Ollama with LLama3.2 model embeddings and ChromaDB to store the bookstore datasets separately in two different paths
-Created two different retrievers for the databases separately.
-Queried both the retrievers and merged the retrieved documents(I used k=5 for both retrievers. In case of large number of datasets, that can be reduced).
-Used LLama3.2 model for generating answer to query from retrieved documents(used same model as embedding for compatibility).