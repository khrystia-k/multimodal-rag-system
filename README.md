# Multimodal RAG system

This system that retrieves relevant news articles from The Batch, incorporating both textual and visual data. It allows users to input queries, answer questions, retrieve relevant articles, and display any associated media (such as images). 

## Data scraping
The data was collected from [The Batch](https://www.deeplearning.ai/the-batch/), which includes tests of all articles and corresponding images.
The scraped data can be viewed in the file **`raw_data.ipynb`**

## Data preprocessing
The texts of the articles were divided into chunks to fit into the LLM window. To save the images and search them, image summaries were generated using gpt-4o-mini. Saved image descriptions can be viewed in the file **`image_summaries.json`**

## Creating multimodal database
The Chroma vector database with the embedding function OpenAIEmbeddings() was chosen to store embedding. It stores chunks and image summaries.
To save the original data, docstore InMemory Stor is used. It stores text chunks, article titles and links, images.

## Multimodal RAG

The multimodal system uses gpt-4o-mini. The system itself consists of two subtasks:

1) Obtaining a response from the LLM according to the received context (text only)
2) Searching for relevant articles and images in the database

The user receives a combined result with the model's  response and the retrieved data.
For demonstration purposes, a simple interface was created using Gradio. 

# Usage
You can get the module from git repository:
```
git clone https://github.com/khrystia-k/multimodal-rag-system
```
Upload necessary packages:
```
pip install requarements.txt
```
Run **`rag.ipynb`** file.

# Demo (video)

[![Video Title](https://img.youtube.com/vi/myFQL0PQ-L8/0.jpg)](https://www.youtube.com/watch?v=myFQL0PQ-L8)

