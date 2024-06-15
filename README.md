# Chatbot-llama-gemini
Trying to create my first Storytelling bot with Q/A, summarizing capabilities using Gemini Flash LLM by integrating it with a vector database using LLamaIndex. 
This project is an improvement of my course project in IS 707- Intelligent Technologies at UMBC. 

# Why use this Google API?
  - Free up to certain limit
  - To leverage free Gemini flash LLM capabilities without running it locally.
# Why should we try RAG with LLMs?
  - LLMs are trained on large data chunks on the internet but not specifically on your own data.
  - So they can hallucinate when performing Q/A tasks on your data.
# How do we fix it?
  - By indexing your data from databases(structured)/documents(unstructured)/API(programmatic) and storing it in vector database.
    ![image](https://github.com/Ilurusheshasai/Chatbot-llamaIndex-gemini-RAG/assets/82218555/69246a3d-6da4-4621-a403-af0096fb7a32)

# What is the role of LlamaIndex in this?
  - Offers data connectors to ingest your existing data sources and data formats (APIs, PDFs, docs, SQL, etc.).
  - Provides ways to structure your data (indices, graphs) so that this data can be easily used with LLMs.
  - Provides an advanced retrieval/query interface over your data: Feed in any LLM input prompt, get back retrieved-context and knowledge-augmented output.
  - Allows easy integrations with your outer application framework (e.g. with LangChain, Flask, Docker, ChatGPT, or anything else).
# Key Concepts in RAG:
These are the sequence of steps that one can follow to improve LLM performance using RAG.
  1) Loading - Getting data from text files, PDFs, websites, Databases, and API. These are collected using readers/connectors and are converted into documents and nodes.
  2) Indexing - Once data loading is done we will be creating vector embeddings that allow querying the data. we are converting data into a structure. LLamaIndex converts the query into embeddings then the vector store will find the data that is numerically similar to the embeddings of the query.
  3) Storing - Once data is indexed we can store it instead of re-indexing ( very helpful for this project as data don't change much for this project).
  4) Querying - For any indexing strategies, there are supposedly many ways to use LLMs and LLamaIndex data structures to query. LLamaindex help is optimizing the query asked retrieving data and passing it to LLM to get an optimal output from LLM.
  5) Evaluating - A critical step in any pipeline is to check how effective when compared with other strategies.
