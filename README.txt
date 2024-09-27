RAG Pipeline & Potential Failure Points
Below figure shows a typical RAG pipeline and potential failure points. The whole RAG pipeline can be divided into 3 main parts:
1. Index: Potential failures includes
a. Missing content: Missing data due to incomplete dataset, missing meta data, and bad chunking that separates content.
b. Divergent sources: Two resources that pointing to similar query but contains divergent information. E.g., HR policy documents that published in different years.
c. Bad chunking: For different chunking strategies, check out this page: https://wilki.one.int.sap/wiki/display/GenAiApps/Document+Chunking+ Strategies
2. Retrieval: for both initial retrieval and re-ranking
a. Low retrieval precision
b. Low retrieval recall
3. Generation
a. Not grounded: The answer does not use the information from the retrieved context
b. Not relevant to query
RAG Pipeline & Failure Points
-------------------------
RAG evaluation framework
Currently, there are two main open-source framework for RAG evaluation: Ragas and Trulens.
A summary of supported metrics are shown in the Figure below. Both Ragas and Trulens have similar metrics that focus on the retrieval and generation parts:
•Ragas:
• Generation: Faithfulness and answer relevance.
a Retrleval: LLM rated context precision and context recall
• Trulens (The RAG triad)
• Context Relevance: Measures the relevance of retrieved text chunks to the user's query, aiding in debugging and refining the retrieval process.
•Groundedness: Assesses how well the LLM's response is supported by the retrieved context.
• Answer Relevance: Evaluates the relevance of the LLM's response to the original query.
------------------------
