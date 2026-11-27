# study-python-ml

My study notes and exercises from Udacity's AI / Machine Learning course: NumPy and Pandas basics, data visualization, neural networks from scratch, PyTorch, and transformers (including one built from scratch).

> **Heads-up:** much of the exercise material (starter notebooks, `helper.py` graders, `*Solution*` notebooks, and the `deep-learning-with-pytorch` lesson) was **provided by Udacity**. My own work is in the `Learning-*.ipynb` notebooks and in the solved `TODO`s of the exercise notebooks.

## Repository layout

| Path | What's inside |
| --- | --- |
| `Learning-Numpy.ipynb`, `Learning-Pandas.ipynb` | NumPy and Pandas fundamentals |
| `Learning-Matplotlib-Seaborn*.ipynb` | Univariate/bivariate visualization with Matplotlib and Seaborn |
| `Learning-Concepts*.ipynb` | Core ML concepts: error functions, gradient descent, multilayer perceptrons and backpropagation |
| `Learning-Training-NN.ipynb` | Training neural networks: overfitting, regularization, dropout, activation functions, batch vs. stochastic GD |
| `Learning-PyTorch-basic-functions.ipynb`, `Learning-Deep-Learning-PyTorch.ipynb` | PyTorch basics and deep learning with PyTorch |
| `Learning-Transformers.ipynb`, `Learning-Pre-Trained-Transformers.ipynb` | NLP and transformer theory (embeddings, RNNs, attention) and Hugging Face pre-trained models |
| `Learning-Creating-Transformer.ipynb` | A small character-level GPT-style transformer built from scratch (tokenizer, masked multi-head attention, training, generation) on Tiny Shakespeare |
| `Links.ipynb` | Useful external references |
| `numpy_exercise/`, `pandas_exercise/`, `matplot_seaborn_exercises/` | Practice exercises for each library |
| `ml_exercise/` | Perceptrons, softmax, cross-entropy, gradient descent, backpropagation, student admissions, and the *Deep Learning with PyTorch* lesson (parts 1–8) |
| `transformers_exercise/` | Data loader, validation loss and text-generation exercises for transformers |
| `data/` | Datasets used by the notebooks (`csvs/` and `tiny-shakespeare.txt`) |
| `imgs/` | Images referenced by the notebooks |
| `environments/` | Conda environment files (see below) |

## Environments

I used **two conda environments** (conda 26.1.1, Windows):

### `studying-ml` (Python 3.12.13)

Used for the NumPy / Pandas / visualization notebooks and the from-scratch ML exercises (`ml_exercise/`, except `deep-learning-with-pytorch/`).

| Package | Version |
| --- | --- |
| python | 3.12.13 |
| numpy | 2.4.4 |
| pandas | 3.0.2 |
| matplotlib | 3.10.8 |
| seaborn | 0.13.2 |
| notebook | 6.5.2 |
| jupyter | 1.0.0 |

### `pytorch-nn` (Python 3.14.7)

Used for `ml_exercise/deep-learning-with-pytorch/`, `Learning-Creating-Transformer.ipynb` and `transformers_exercise/` (parts 1 and 2).

| Package | Version | Installed with |
| --- | --- | --- |
| python | 3.14.7 | conda |
| torch | 2.14.0 | pip |
| torchvision | 0.29.0 | pip |
| numpy | 2.5.3 | pip |
| matplotlib | 3.11.2 | conda |
| notebook | 7.5.7 | conda |
| jupyter | 1.1.1 | conda |
| ipywidgets | 8.1.9 | conda |

### Setup

```bash
conda env create -f environments/studying-ml.yml
conda env create -f environments/pytorch-nn.yml

conda activate studying-ml   # or: conda activate pytorch-nn
jupyter notebook
```

The environment files were generated with `conda env export --from-history`, which keeps only the packages I explicitly installed rather than every transitive dependency. I then pinned the main package versions, added the packages that were installed with pip (conda's history doesn't track them) and removed the machine-specific `prefix:` line.

### Notes

- `transformers_exercise/3_text_generation_starter.ipynb` and `Learning-Pre-Trained-Transformers.ipynb` use Hugging Face `transformers`, which isn't part of either environment. The text-generation exercise was run on Udacity's hosted workspace (Python 3.10). To run them locally, use `pip install transformers` inside `pytorch-nn`.
- Notebooks with a `Python 3` / `Python 3 (ipykernel)` kernel and an older Python version in their metadata are untouched Udacity originals or were run in Udacity's workspace.
- The *Loading Image Data* and *Transfer Learning* notebooks need the Cat/Dog dataset, which isn't included here (it's git-ignored). The download link is in the notebooks.

## AI disclosure

This README is the **only** AI-generated text in this repository. It was written by an AI assistant using the GitHub Copilot SDK in VS Code, running **Anthropic's Claude Opus 5.5** model (`claude-opus-5.5`). The same assistant also tidied up the conda files in `environments/`, which come from my local environments. Everything else (notes, explanations, code and exercise solutions) is my own work or original Udacity course material.

During the course I also used an AI assistant as a **tutor, not as a code generator**. Its behaviour is defined in [`.github/instructions/ml-professor.instructions.md`](.github/instructions/ml-professor.instructions.md), which puts it in "ML Professor Mode": it must **not** give direct answers to `TODO`s or exercises. Instead it responds with hints, leading questions and conceptual explanations, escalating gradually, and it points out *what* is wrong and *why* in my code so I can fix it myself. I used it to get insights, clear up doubts and check my understanding of the math, but the code and notes are my own.
