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

Hmm no conda package for deeplake.

10) pip install deeplake

This installed deeplake 4.0.2 which was released '26 minutes ago' ... ! 11:09 am ... and nothing else was installed, which is good.

Whelp, right away I am getting errors with deeplake ... gonna install the target version of deeplake, then try again ... 

11) pip install deeplake==3.9.18 

Nice! That fixed the error. 'Chapter02/2_Embeddings_vector_store.ipynb' all runs locally, generating the local vector store into the directory 'VectorStore'.

12) mamba install conda-forge::sentence-transformers
13) pip install markdown
14) mamba install conda-forge::ipywidgets

'Chapter02/3_Augmented_Generation.ipynb' now all runs locally.

## Wednesday, November 13, 2024

Starting to go through Chapter 3. More packages are required, so let's make another backup of our environment. 

mamba create --name rag_genai_20241113 --clone rag_genai

 15) mamba install conda-forge::lllama-index  # this is the latest version, 0.11.23
 16) pip install llama-index-vector-store-deeplake  # this is the latest version, 0.2.2
 17) mamba install conda-forge::tabulate # this is the latest version, 0.9.0

To try running llamaindex using LMStudio, I had to install the following packages:

 18) pip install llama-index-llms-lmstudio  # this is the latest version, 0.2.1
 19) pip install llama-index-embeddings-huggingface # this is the latest version, 0.3.1
 20) pip install llama-index-embeddings-instructor # this is the latest version, 0.2.1

 ## Friday, November 15, 2024

 Hmm looks like we need flask ...

  21) mamba install conda-forge::flask

  And now we need OpenCV ...

  22) mamba install conda-forge::opencv # this is the latest version, 4.10.0 ... I did NOT run this, because it would have changed way too mnay things! Argh, same with versions 4.9.0, 4.8.1 and 4.8.0. So, I think I will first back up the current environment to, say, rag_genai_20241115, then try to install opencv 4.9.0 and see what happens.

  mamba create --name rag_genai_20241115 --clone rag_genai

I will install opencv to this 20241115 environment, then try to run the notebook.

The biggest change I see is replacing the cuda version of pytorch to the cpu only version ... 

## Thursday, December 12, 2024

Yup gonna get back to this today ... I currently have this ..

  rag_genai                /home/rob/miniforge3/envs/rag_genai
  rag_genai_20241111       /home/rob/miniforge3/envs/rag_genai_20241111
  rag_genai_20241113       /home/rob/miniforge3/envs/rag_genai_20241113
  rag_genai_20241115       /home/rob/miniforge3/envs/rag_genai_20241115

on the kitchen computer. 

I am going to try and run 'LMStudio/Chapter03/Deep_Lake_LlamaIndex_OpenAI_RAG.ipynb' in the rag_genai_20241115 environment.
