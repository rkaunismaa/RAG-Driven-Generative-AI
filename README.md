# RAG-Driven-Generative-AI

This repository will be my walk through of the book "RAG Driven Generative AI" by Denis Rothman.

<img src="images/RAG_GENAI.png" alt="RAG Driven Generative AI" width="300">

## Sunday, November 10, 2024

Creating a local mamba environment for this repository:

 1) mamba create -n rag_genai python=3.11
 2) mamba activate rag_genai
 3) mamba install conda-forge::jupyterlab
 4) mamba install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
 5) mamba install conda-forge::openai
 6) mamba install conda-forge::scikit-learn
 7) mamba install conda-forge::nltk
 8) mamba install conda-forge::spacy
 9) mamba install conda-forge::pandas

The notebooks from the book all default to using OpenAI, but I also want to run them against a local model served up through LMStudio. The folder 'LMStudio' will be where these notebooks reside. 

## Monday, November 11, 2024

Running 'LMStudio/Chapter01/RAG_Overview.ipynb' against the 4090 is sooo much faster than running it against the 2070 super!

Working through Chapter 2 of the book requires a bunch of more installs, so I am going to back up the current 'rag_genai' environment to, say, 'rag_genai_20241111' and continue with installing to rag_genai.

mamba create --name rag_genai_20241111 --clone rag_genai


