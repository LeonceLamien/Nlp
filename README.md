<div align="center">

# Natural Language Processing

*From classical text processing and statistical language models to transformer-based question answering*

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![NLTK](https://img.shields.io/badge/NLP-NLTK-orange.svg)
![PyTorch](https://img.shields.io/badge/Deep%20Learning-PyTorch-red.svg)
![Hugging%20Face](https://img.shields.io/badge/Models-Hugging%20Face-yellow.svg)

[About](#about) • [Projects](#projects) • [Tech Stack](#tech-stack) • [Getting Started](#getting-started) • [Repository Structure](#repository-structure)

</div>

---

## About

This repository is a hands-on exploration of **Natural Language Processing (NLP)**. Across three projects, it follows a progression from text preprocessing and probabilistic methods to distributed word representations and transformer-based question answering.

The work is implemented primarily in Jupyter notebooks and covers the practical steps of preparing text, building and evaluating models, and interpreting their predictions.

## Projects

### 1. Text Classification and N-gram Language Modeling

`p1/main.ipynb` develops classical NLP workflows using the provided training and test CSV files:

- Cleans HTML markup and tokenizes text.
- Builds a frequency-filtered vocabulary and handles out-of-vocabulary tokens.
- Implements Naive Bayes text classification with Laplace smoothing, including binary word features and negation-aware preprocessing.
- Builds a bigram language model and evaluates it using perplexity.

### 2. Word Embeddings and Context

`p2/main.ipynb` explores how words are represented through their surrounding context:

- Tokenizes and inspects a text corpus.
- Examines context windows around selected words.
- Trains and uses **Word2Vec** embeddings with Gensim.
- Explores pretrained word vectors.

### 3. Transformer Question Answering

The notebooks in `p3/` build an extractive question-answering pipeline on the **SQuAD** dataset using **DistilBERT**:

1. `question_answering_1.ipynb` loads and filters the dataset, tokenizes question-context pairs, handles long contexts with overlapping segments, and prepares tokenized datasets.
2. `question_answering_2.ipynb` maps answer spans to token positions, trains a question-answering model, generates answers, and evaluates predictions with **Exact Match** and **F1**.

The second notebook requires a GPU for practical model training. It loads datasets saved by the first notebook, so update the notebook's data paths to match your environment.

## Tech Stack

| Area | Tools |
|------|-------|
| Data processing | Python, pandas, NumPy |
| Classical NLP | NLTK |
| Word embeddings | Gensim, Word2Vec |
| Transformer models | PyTorch, Hugging Face Transformers |
| Datasets and evaluation | Hugging Face Datasets, Evaluate |
| Interactive development | Jupyter Notebook |

## Getting Started

### Prerequisites

- Python 3 and `pip`
- Jupyter Notebook
- A GPU is recommended for training the transformer model in Part 3

### Installation

Clone the repository and create an isolated Python environment:

```bash
git clone https://github.com/<your-username>/<your-repository>.git
cd <your-repository>
python3 -m venv .venv
source .venv/bin/activate
```

On Windows, activate the environment with:

```powershell
.venv\Scripts\activate
```

Install the libraries used across the notebooks:

```bash
python -m pip install --upgrade pip
python -m pip install jupyter pandas numpy nltk gensim torch transformers datasets evaluate accelerate
```

For GPU training, install the PyTorch build that matches your hardware and CUDA setup using the [official PyTorch installation selector](https://pytorch.org/get-started/locally/).

### Running the notebooks

Start Jupyter from the repository root:

```bash
jupyter notebook
```

Open and run the notebooks in order:

1. `p1/main.ipynb`
2. `p2/main.ipynb`
3. `p3/question_answering_1.ipynb`
4. `p3/question_answering_2.ipynb`

Run each notebook's cells from top to bottom. Some notebooks use paths from their original execution environment, so check the working directory and update dataset paths before running them. In particular, the Part 2 notebook expects `corpora/corpus.zip`, while the bundled archive is at `p2/data/corpus.zip`. The Part 3 notebooks download SQuAD through Hugging Face and save intermediate datasets; update the local or Google Drive paths as needed. The first question-answering notebook also relies on the filtering indices referenced in its instructions.

## Repository Structure

```text
Nlp/
├── p1/
│   ├── main.ipynb                 # Text preprocessing, Naive Bayes, and bigram model
│   └── ressources/
│       ├── train.csv              # Training data
│       └── test.csv               # Test data
├── p2/
│   ├── main.ipynb                 # Context windows and Word2Vec
│   ├── corpus.txt                 # Text corpus
│   └── data/
│       ├── corpus.txt
│       ├── corpus.zip
│       └── toy_corpus.txt
├── p3/
│   ├── question_answering_1.ipynb  # SQuAD preprocessing and tokenization
│   └── question_answering_2.ipynb  # Training, inference, and evaluation
└── README.md
```

---

<div align="center">

**A practical NLP journey: from statistical text models to neural question answering.**

</div>
