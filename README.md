# Exploring RAG pattern for LLMs

**Retrieval Augmented Generation (RAG)** is the pattern or architectural design enabling data management of custom business data in a db, real-time data retrieval to efficiently extract information from the db which are relevant to the user query, and LLM prompt augmentation with the search result.

The way it works is:
- The user inputs an initial prompt, which is used to search a data source and **retrieve** relevant grounding data.
- The grounding data is used to **augment** the prompt by adding additional contextualization and scoping text.
- The augmented prompt is submitted to the LLM, which can then **generate** an appropriate response in natural language.

![RAG pattern visualization](RAG_pattern_visualization.png)

## In this repo
This repository contains a collection of notebooks and scripts that break down the RAG pattern for LLMs. It is organized as follows:
1. [0-create-search-index.ipynb](./0-create-search-index.ipynb): this notebook demonstrates how to *create a search index* with **Azure AI Search** using an hybrid search approach + semantic ranking. It populates the index with a sample dataset containing a product catalog ([products.csv](./data/products.csv)) of a fictional retail company called Contoso.
2. [1-retrieve-documentation.ipynb](./1-retrieve-documentation.ipynb): this notebook demonstrates how to *retrieve relevant documentation* from the Azure AI search index using a user query. To do so, it first converts the query into an embedding, using Azure OpenAI text-embedding-ada-002 model.
3. [2-augment-prompt.prompty](./2-augment-prompt.prompty): this script demonstrates how to *build a dynamic prompt specification* with **Prompty** and inform it with the retrieved documentation. The Prompty file can also be executed to *generate the final answer* to the augmented prompt.

## Pre-requisites

## Run in GitHub Codespaces