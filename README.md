# Small-Scale Classification Benchmark with Scikit-learn and Spark

> Portfolio project by Dorsa Norouzi.  
> © 2026 Dorsa Norouzi. All rights reserved.

## Project Overview

This repository presents a focused portfolio version of a classification benchmark using the Mushroom dataset as a small categorical dataset.

The goal is to compare a Scikit-learn baseline workflow with a Spark-based Random Forest workflow and analyze whether Spark parallelization is useful for small-scale classification tasks.

The broader project context also included comparison with a larger text-based dataset, but this repository focuses on the small-dataset implementation, preprocessing workflow, model training, runtime comparison, and evaluation.

## Dataset

The Mushroom dataset contains categorical features describing physical mushroom characteristics such as cap shape, cap color, odor, gill size, gill color, population, and habitat.

The classification task is binary:

- edible
- poisonous

The dataset is useful for classification because the target class has practical importance and the features are categorical, requiring preprocessing before model training.

The raw dataset is not included in this repository.

## Methodology

This project compares two workflows.

### Scikit-learn Baseline

The baseline workflow uses:

- Pandas
- Ordinal encoding
- Train/test split
- Random Forest Classifier
- Accuracy, precision, recall, F1-score, and confusion matrix

### Spark-Based Workflow

The Spark workflow uses:

- PySpark
- Spark DataFrame
- StringIndexer for categorical feature encoding
- VectorAssembler for feature preparation
- Random Forest Classifier from Spark MLlib
- Partitioning and local multi-core execution
- Runtime and classification metric comparison

## Evaluation Focus

The project evaluates both model performance and runtime.

Metrics include:

- Training time
- Evaluation time
- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

Accuracy alone is not always sufficient, especially in classification tasks where one type of mistake may be more important than another. For this dataset, recall for the poisonous class is especially important because misclassifying poisonous mushrooms can have serious consequences.

## Results Summary

The Scikit-learn baseline achieved strong performance with very low runtime on the small dataset.

The Spark-based workflow also achieved strong classification performance, but introduced additional runtime overhead. This shows that Spark is not always beneficial for small datasets, even though it becomes more useful when working with larger datasets that are difficult to process with local Pandas/Scikit-learn workflows.

## Key Learning Outcomes

This project strengthened practical experience in:

- Binary classification
- Categorical data preprocessing
- Ordinal encoding
- PySpark StringIndexer and VectorAssembler
- Random Forest classification
- Comparing Scikit-learn and Spark MLlib workflows
- Runtime benchmarking
- Model evaluation using precision, recall, F1-score, and confusion matrix
- Understanding when Spark parallelization is useful and when it introduces unnecessary overhead

## Technologies Used

- Python
- Pandas
- Scikit-learn
- PySpark
- Spark MLlib
- Matplotlib
- Jupyter Notebook

## Repository Structure

```text
small-dataset-classification-spark-benchmark/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── mushroom_classification_sklearn_spark_clean.ipynb
│
├── results/
│   └── metrics_summary.csv
│
└── data/
    └── README.md
```

## Configuration

The raw dataset is not included in this repository.

To reproduce the project, place the Mushroom dataset locally using the following path:

```text
data/agaricus-lepiota.data
```

If your dataset is stored somewhere else, update the dataset path in the notebook.

## Installation

Install the required packages:

```bash
pip install -r requirements.txt
```

## How to Run

1. Clone this repository.
2. Install the required packages.
3. Place the Mushroom dataset in the `data/` folder.
4. Open the notebook in Jupyter Notebook or VS Code.
5. Update the dataset path if necessary.
6. Run the notebook cells in order.

## Author

Dorsa Norouzi  
GitHub: [DorsaNzy](https://github.com/DorsaNzy)

## Copyright

© 2026 Dorsa Norouzi. All rights reserved.

This repository is shared as a portfolio project to demonstrate practical experience in classification, preprocessing, Spark-based machine learning, runtime benchmarking, and model evaluation.
