# CS6120 Natural Language Processing - Group 6 - Course Project
A project created as a part of CS6120 - Natural Language Processing offered at the Northeastern University in Spring 2025. Our group consists of 3 members as follows - 
- Akash Dhande
- Gargi Vipat
- Rohan Puntambekar

## Prerequisites - 
### 1. Locally running setup of Ollama -
We need a locally running instance of Ollama for downloading and running the models required for this project, which can then be used as an independent service. Ollama can be downloaded and installed from their official website - [Ollama Download](https://ollama.com/download)

### 2. Python Libraries/Dependencies -
A `requirements.txt` file has been provided with all the necessary libraries needed. It is recommended to create a separate Conda environment for installing the dependencies to avoid any conflicts. Use the following command to install all the python dependencies in your environment:
```
pip install -r requirements.txt
```
 
## Instructions to Run -
### 1. Chunking the raw data -
This repository contains the chunked data, and it is not compulsory to create the chunks again. However to create the chunks from scratch again please run the code provided in [`src/chunking.ipynb`](src/chunking.ipynb)


### 2. Running the RAG pipeline -
The code for the entire RAG pipeline is included in the [`src/rag_pipeline.ipynb`](src/rag_pipeline.ipynb). 
Specify the following config vairables in the notebook - 


The complete RAG pipeline performs the following steps - 
- Reads the chunks created in the above chunking step.
- Generated embeddings for all the chunks.
- Stores all the chunks in the vector database - ChromaDB
- Reads the question answer dataset, and performs retrieval from the vector database based on cosine similarity between the question and the chunks.
- Providing the question and the context as a part of the input prompt to the generation model.
- Perform all the above steps for each question and write the generated answers to a output CSV file.

After running the `src/rag_pipeline.ipynb` the results will be written to the folder `results/generated`.

### 3. Getting Evaluation Metrics -
The code for the evaluation and calculation of the BLEU Score and ROUGE Score is provided in the file [`src/raga_eval.ipynb`](src/raga_eval.ipynb). Specify the path of the generated output you need to evaluate as the value of the variable `generated_result_path` in the second cell. You can simply run all the cells to get the BLEU score and the ROUGE score towards the end of the notebook.