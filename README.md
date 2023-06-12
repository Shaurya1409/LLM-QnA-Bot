# LLM-QnA-Bot
A PoC for an LLM based QnA Bot that answers questions from a few chapters from the NCERT Books.

## Issues 
Langchain has a hardcoded value of 1536 as the Vector Size for PG Vector. In this PoC I have utilized Hugging Face Embeddings which has a dimensionality of 768. 

This resulted in errors being thrown while pushing the embeddings to the VectorStore (Postgres)

To fix this update the following line in 
*/{ENV}/Lib/site-packages/langchain/vectorstores/pgvector.py*

From 
```ADA_TOKEN_COUNT = 1536```

To
```ADA_TOKEN_COUNT = 768```