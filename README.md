# Company Name Generator

A character-level language model that generates realistic company names, built from scratch following Andrej Karpathy's makemore series.

## Dataset
[Company Names Dataset](https://www.kaggle.com/datasets/tathagatanath/comapny-names) from Kaggle — cleaned by lowercasing, removing numbers and special characters, and splitting into 80/10/10 train/val/test sets.

## Architecture
- Character-level MLP with 5 hidden layers (100 neurons each)
- 10-dimensional character embeddings with context window of 3
- BatchNorm after every linear layer
- Kaiming initialization for weights
- Trained for 200,000 steps with learning rate decay (0.1 → 0.01)

## Results
| Split | Loss |
|---|---|
| Train | 1.703 |
| Val | 1.842 |

## Sample Generated Names
```
freighting
ram solutics
governation
piramal era autoyotive
interpriseing
exporate engineers industries
```

## How to Run
1. Download the dataset from Kaggle and place it in the project folder
2. Open `company_name_generator.ipynb` in Jupyter
3. Run all cells in order

