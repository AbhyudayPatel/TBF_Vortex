# TBF_Vortex: Vibrational Analysis for Tunnel Booster Fans

This repository contains the code and data for a project that uses vibrational analysis to predict the life expectancy and maintenance needs of tunnel booster fans. The project leverages Convolutional Neural Networks (CNN) and Recurrent Neural Networks (RNN) to classify the operational status of the fans based on accelerometer data.

## Project Overview

Tunnel booster fans are critical components of a tunnel's ventilation system. Predicting their failure and scheduling maintenance proactively can prevent costly downtime and ensure safety. This project uses machine learning models to analyze vibrational data from these fans to determine if they are operating normally or are in a state of anomaly.

## Dataset

The dataset used in this project is `M02_Feb_2021_OP13_000.csv`. It contains accelerometer data with the following columns:

- `x`: Accelerometer reading on the x-axis.
- `y`: Accelerometer reading on the y-axis.
- `z`: Accelerometer reading on the z-axis.
- `status`: The operational status of the fan.
    - `1`: Normal operation.
    - `0`: Anomaly or failure.

## Methodology

The project follows these steps:

1.  **Data Loading and Exploration**: The data is loaded from the CSV file and explored to understand its structure and characteristics.
2.  **Data Preprocessing**: A sliding window approach is used to segment the time-series data into smaller chunks. This is a common technique for preparing time-series data for deep learning models.
3.  **Feature Engineering**: For some models, Fast Fourier Transform (FFT) is applied to the data to extract frequency-domain features.
4.  **Model Training**: Two main types of models are used:
    - **1D Convolutional Neural Network (CNN)**: The `cnn.ipynb` notebook implements a 1D CNN for classification. This model is well-suited for finding patterns in 1D signals like time-series data.
    - **Artificial Neural Network (ANN)**: The `model1.ipynb` notebook explores the data and builds an ANN model.
5.  **Model Evaluation**: The models are evaluated on a test set to assess their accuracy and other performance metrics. The CNN model achieves an accuracy of approximately 99%.

## Repository Structure

```
├── M02_Feb_2021_OP13_000.csv
├── README.md
├── ann_mod.h5
├── cnn.ipynb
├── model1.ipynb
└── requirements.txt
```

- **`M02_Feb_2021_OP13_000.csv`**: The dataset file.
- **`README.md`**: This file.
- **`ann_mod.h5`**: A trained and saved Keras model.
- **`cnn.ipynb`**: Jupyter notebook containing the implementation of the 1D CNN model.
- **`model1.ipynb`**: Jupyter notebook for data exploration, feature engineering, and an ANN model.
- **`requirements.txt`**: A list of Python dependencies required to run the notebooks.

## Getting Started

### Prerequisites

You will need Python 3 and the dependencies listed in `requirements.txt`.

### Installation

1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/TBF_Vortex.git
    ```
2.  Install the dependencies:
    ```bash
    pip install -r requirements.txt
    ```

### Usage

You can run the Jupyter notebooks `cnn.ipynb` and `model1.ipynb` to see the data processing, model training, and evaluation steps.

## Workflow for Diagram

Here is a textual representation of the project workflow, which can be used to create a flowchart or diagram:

1.  **Start**
2.  **Load Data**: Read `M02_Feb_2021_OP13_000.csv`
3.  **Preprocess Data**:
    - Apply Sliding Window to create time-series segments.
4.  **Feature Engineering (Optional)**:
    - Apply Fast Fourier Transform (FFT) to extract frequency features.
5.  **Split Data**: Divide data into Training and Testing sets.
