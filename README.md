# Chatbot-llama-gemini
Trying to create my first Storytelling bot with Q/A, summarizing capabilities using Gemini Flash LLM by integrating it with a vector database using LLamaIndex.<br>
This project is an improvement of my course project in IS 707- Intelligent Technologies at UMBC. <br>
The initial development of a project can be found here: https://github.com/Ilurusheshasai/multiple-LLM-chatbot<br>
I have used multiple LLMs to empower chatbots with human-like capabilities in summarizing (extractive (to retrieve important points from stories) and abstraction(to rewrite a sentence without changing the meaning)), Question answering, speaking out the story (using Python gtts module).
<br>
So, I have used 3 models and ran them locally. 
<br>
Although summarizing the stories is working fairly, I wouldn't say I liked the performance of the QA model, for the following reasons.
1) It gives correct answers only for a few questions.
2) On top of that The correct answers are also not convincing because it looks like they give answers giving the exact sentence from the story.
3) My argument is if there is an LLM that learned a lot from pre-training before, I do not want to train it again by passing questions, context, and answers to work on my local story base. If I had to train it on question answer and context again, I would choose a simple conditional code with TF-IDF to find similarity and answer it.
5) So, I explored other options and wanted to try RAG using a vector database and knowledge graphs.
6) This repo is an implementation of an RAG-based vector store to leverage the best output from LLM (Google Gemini pro model) in this case...

The objective was to learn and explore, I might have trained and fine-tuned these models to improve the performance at the same time I looked for easier and better options which led to implementing RAG using LLamaIndex. which I think is a good exposure. So I am happy....

# Why use this Google API?
  - Free up to certain limit
  - To leverage free Gemini flash LLM capabilities without running it locally.
# Why should we try RAG with LLMs?
  - LLMs are trained on large data chunks on the internet but not specifically on your own data.
  - So they can hallucinate when performing Q/A tasks on your data.
# How do we fix it?
  - By indexing your data from databases(structured)/documents(unstructured)/API(programmatic) and storing it in vector database.
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
