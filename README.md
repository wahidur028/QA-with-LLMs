###**The Pipeline for converting raw unstructured data into a QA chain using LangChain**

- **Step 1. Loading:** First, data needs to be loaded. Structured data and Unstructured data can be loaded from many sources. As of today (August 18, 2023), 154 data loaders are available on the LangChain platform. **[link](https://integrations.langchain.com/)**.

- **Step 2. Splitting:** Text splitters break documents into splits of specified size. Chunk size and chunk overlaping can be defined here. 

- **Step 3. Storage:** To look up the document splits, it needs to be stored where we can later look them up. The most common way to do this is to embed the contents of each document and then store the embedding and document in a vector store, with the embedding being used to index the document.  As of today (August 18, 2023), 40 vectorstores and 30 text embedding are available on the LangChain platform. **[link](https://integrations.langchain.com/)**.

- **Step 4. Retrieval:** Retrieve relevant splits for any question using similarity search. Vectorstores are commonly used for retrieval, but they are not the only option. For example, SVMs can also be used. LangChain has many retrievers including, but not limited to, vectorstores. Some common ways to improve on vector similarity search include:
  - *MultiQueryRetriever* generates variants of the input question to improve retrieval. **[link](https://python.langchain.com/docs/modules/data_connection/retrievers/MultiQueryRetriever)**.
  - *Max marginal relevance* selects for relevance and diversity among the retrieved documents. **[link](https://www.cs.cmu.edu/~jgc/publication/The_Use_MMR_Diversity_Based_LTMIR_1998.pdf)**.

- **Step 5. Generation:** An LLM produces an answer using a prompt that includes the question and the retrieved data. You can pass in an LLM or a ChatModel to the RetrievalQA chain. **[link](https://integrations.langchain.com/)**.
