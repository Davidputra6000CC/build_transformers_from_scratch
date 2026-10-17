# Makemore — Building Character-Level Language Models

I'm working through Andrej Karpathy's [Neural Networks: Zero to Hero](https://github.com/karpathy/nn-zero-to-hero) lecture series, starting with character-level language models and building my understanding from the ground up.

This repository documents my implementations, experiments, and learning process as I work through the `makemore` lectures. I'm starting with a bigram language model and moving on to a multilayer perceptron (MLP), exploring how models learn patterns in text and generate new names.

My goal is to understand the ideas behind language models by implementing them step by step rather than relying entirely on pre-built models.

## What I'm Building

### 1. Bigram Language Model

A character-level language model that predicts the next character based on the current character.

- Building a vocabulary and encoding characters as integers
- Counting character transitions and estimating probabilities
- Generating names by sampling from probability distributions
- Understanding negative log-likelihood as a loss function
- Rebuilding the model as a simple neural network and training it with gradient descent

**Reference:** [Lecture 2 — Building makemore, Part 1: Bigrams](https://github.com/karpathy/nn-zero-to-hero/blob/master/lectures/makemore/makemore_part1_bigrams.ipynb)

### 2. Multilayer Perceptron (MLP)

Moving beyond single-character transitions to a neural network that uses a context of previous characters to predict the next one.

- Character embeddings and learned representations
- Context windows and embedding lookup tables
- Hidden layers, activation functions, and softmax probabilities
- Forward propagation, loss calculation, and gradient-based optimization
- Learning-rate experimentation
- Training, development, and test splits
- Understanding overfitting and model evaluation

**Reference:** [Lecture 3 — Building makemore, Part 2: MLP](https://github.com/karpathy/nn-zero-to-hero/blob/master/lectures/makemore/makemore_part2_mlp.ipynb)

## Project Structure

```text
build_transformers_from_scratch/
│
├── src/
│   ├── language_model_biagram.ipynb
│   ├── multi_level_perceptron.ipynb
│   └── names.txt
│
├── .gitignore
├── .python-version
├── README.md
├── pyproject.toml
└── uv.lock
```

The notebooks are the main learning material. I use them to work through the models step by step, inspect intermediate results, and experiment with the implementation.

## Getting Started

### Prerequisites

- Python version compatible with `.python-version` and `pyproject.toml`
- [uv](https://docs.astral.sh/uv/)
- Visual Studio Code with the Jupyter extension, or Jupyter Notebook

### 1. Clone the repository

```bash
git clone https://github.com/Davidputra6000CC/build_transformers_from_scratch.git
cd build_transformers_from_scratch
code .
```

### 2. Install uv

If you don't have uv installed, follow the [official installation instructions](https://docs.astral.sh/uv/getting-started/installation/).

On Windows, you can install it through PowerShell:

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 3. Create the environment and install dependencies

From the repository root, run:

```bash
uv sync
```

This creates a project virtual environment, normally `.venv`, and installs the dependencies specified in `pyproject.toml`, using `uv.lock` to reproduce the locked dependency versions where possible.

### 4. Activate the environment

**Windows PowerShell**

```powershell
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks script execution, allow activation for the current terminal session:

```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy RemoteSigned
.\.venv\Scripts\Activate.ps1
```

**Windows Command Prompt**

```cmd
.venv\Scripts\activate.bat
```

**macOS / Linux**

```bash
source .venv/bin/activate
```

Activation is optional when using commands such as `uv run`.

### 5. Open the notebooks

Open the repository in VS Code, select the `.venv` Python interpreter as your notebook kernel, and start with:

1. `src/language_model_biagram.ipynb`
2. `src/multi_level_perceptron.ipynb`

Run the cells sequentially to follow the experiments.

## Research Papers and Further Reading

These papers provide background for the language-modeling concepts explored in the lectures and the wider `makemore` progression.

### Neural Probabilistic Language Models

**Bengio, Y., Ducharme, R., Vincent, P., & Jauvin, C. (2003).** *A Neural Probabilistic Language Model.*

This paper introduces a neural approach to language modeling using learned distributed representations and a neural network conditioned on preceding context. It provides important background for the MLP language model.

[Read the paper — Journal of Machine Learning Research](https://www.jmlr.org/papers/v3/bengio03a.html)

### Related Research for Further Learning

These papers are relevant to the broader progression from recurrent language models to modern architectures. They are included as further reading, not as claims that all these architectures have been implemented in this repository.

- **Mikolov et al. (2010)** — [Recurrent Neural Network Based Language Model](https://www.fit.vut.cz/research/publication/9744)
- **Graves (2013)** — [Generating Sequences With Recurrent Neural Networks](https://arxiv.org/abs/1308.0850)
- **Cho et al. (2014)** — [Learning Phrase Representations using RNN Encoder–Decoder for Statistical Machine Translation](https://arxiv.org/abs/1406.1078)
- **van den Oord et al. (2016)** — [WaveNet: A Generative Model for Raw Audio](https://arxiv.org/abs/1609.03499)
- **Vaswani et al. (2017)** — [Attention Is All You Need](https://arxiv.org/abs/1706.03762)

For the complete lecture sequence and original references, visit [Andrej Karpathy's Neural Networks: Zero to Hero](https://github.com/karpathy/nn-zero-to-hero) and the [original makemore repository](https://github.com/karpathy/makemore).

## Learning Resources and Credits

This project is based on my study of Andrej Karpathy's open-source work and lectures.

- [Neural Networks: Zero to Hero — original lecture repository](https://github.com/karpathy/nn-zero-to-hero)
- [makemore — original implementation](https://github.com/karpathy/makemore)
- [Part 1: Bigram language model notebook](https://github.com/karpathy/nn-zero-to-hero/blob/master/lectures/makemore/makemore_part1_bigrams.ipynb)
- [Part 2: MLP language model notebook](https://github.com/karpathy/nn-zero-to-hero/blob/master/lectures/makemore/makemore_part2_mlp.ipynb)
- [Zero to Hero course page](https://karpathy.ai/zero-to-hero.html)

The original lectures, notebooks, and project belong to their respective authors. This repository documents my learning process, implementations, and experiments while following the lectures. Please refer to the original repositories for their licensing terms and canonical implementations.

## About Me

I'm Garv Sharma, learning machine learning and deep learning by understanding the fundamentals and implementing models step by step.

- **GitHub:** [Davidputra6000CC](https://github.com/Davidputra6000CC)
- **LinkedIn:** [Garv Sharma](https://www.linkedin.com/in/garv-sharma-157796395/)

This is an ongoing project. As I progress through the lectures, I'll continue documenting what I learn and extending the implementations.
