# Company Name Generator

A character-level language model that generates realistic company names, built from scratch following Andrej Karpathy's makemore series. Two architectures are implemented and compared.

## Dataset
[Company Names Dataset](https://www.kaggle.com/datasets/tathagatanath/comapny-names) from Kaggle — cleaned by lowercasing, removing numbers and special characters, and splitting into 80/10/10 train/val/test sets.

## Architectures

### MLP (`mlp.ipynb`)
- Character-level MLP with 5 hidden layers (100 neurons each)
- 10-dimensional character embeddings with context window of 3
- BatchNorm after every linear layer
- Kaiming initialization
- Trained for 200,000 steps with learning rate decay (0.1 → 0.01)

### WaveNet (`wavenet_architecture.ipynb`)
- Hierarchical WaveNet-style architecture
- Characters combined in pairs across 3 layers
- 10-dimensional embeddings with context window of 8
- 100 hidden neurons per layer
- Trained for 200,000 steps with learning rate decay (0.1 → 0.01)

## Results

| Architecture | Train Loss | Val Loss |
|---|---|---|
| MLP | 1.703 | 1.842 |
| WaveNet | 1.451 | 1.771 |

WaveNet improves val loss by ~0.07 by learning hierarchical character patterns instead of flattening all context at once.

## Sample Generated Names

**MLP:**
```
freighting
ram solutics
governation
exporate engineers industries
```

**WaveNet:**
```
hargya industries
wiprebiog finance
syntel researchem
applied power genering comp
```

## How to Run
1. Download the dataset from Kaggle and place it in the project folder
2. Open either notebook in Jupyter
3. Run all cells in order
