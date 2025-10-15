
# Global Earthquake-Tsunami Risk Assessment using Deep Learning

This project implements an end-to-end deep learning pipeline to predict the risk of a tsunami following an earthquake. The model is built using TensorFlow and Keras and is divided into three main components: data preprocessing, model training, and prediction.

---

## 📋 Table of Contents
* [Project Overview](#project-overview)
* [Dataset](#dataset)
* [Project Structure](#project-structure)
* [Methodology](#methodology)
* [Technologies Used](#technologies-used)
* [How to Use](#how-to-use)
* [Results](#results)

---

## 🚀 Project Overview

The goal of this project is to develop a reliable neural network model that can classify whether an earthquake will generate a tsunami based on various seismic features. The final application allows a user to input data for a new earthquake event and receive a tsunami risk prediction.

---

## 💾 Dataset

The dataset used for this project is sourced from a public CSV file containing global earthquake and tsunami data. The preprocessing script (`Global Earthquake Tsunami Risk - Data Preprocessing.ipynb`) loads this data directly.

**Source:** [earthquake_data_tsunami.csv](https://raw.githubusercontent.com/AbhishekBiswas-github/Python_Data_Science/refs/heads/main/Global%20Earthquake-Tsunami%20Risk%20Assessment/earthquake_data_tsunami.csv)

---

## 📂 Project Structure

The repository is organized into three Jupyter notebooks, each handling a specific part of the machine learning pipeline:

1.  **`Global Earthquake Tsunami Risk - Data Preprocessing.ipynb`**: This notebook is responsible for loading the raw data, cleaning it, balancing the target classes, scaling the features, and splitting the dataset into training, validation, and test sets. The processed data is saved into `.npz` files.
2.  **`Global Earthquake Tsunami Risk - Modelling.ipynb`**: This notebook loads the preprocessed data, defines the neural network architecture, compiles and trains the model, and evaluates its performance. The final trained model is saved as `Earthquake.keras`.
3.  **`Global Earthquake Tsunami Risk - Prediction.ipynb`**: This script loads the saved `.keras` model and provides a simple command-line interface for users to input new earthquake data and get a tsunami risk prediction.

---

## 🛠️ Methodology

### 1. Data Preprocessing
* **Data Loading**: The dataset is loaded from the source URL using **Pandas**.
* **Class Balancing**: To handle the imbalanced nature of the dataset, an undersampling technique was applied to the majority class.
* **Feature Scaling**: All input features were standardized using **Scikit-learn's** `preprocessing.scale()` to ensure they have a mean of 0 and a standard deviation of 1.
* **Data Splitting**: The dataset was shuffled and split into three parts: **80% for training**, **10% for validation**, and **10% for testing**.

### 2. Model Architecture
A sequential model was built using **TensorFlow/Keras** with the following layers:
* **Input Layer**: Accepts a vector of 10 input features.
* **Hidden Layer 1**: A `Dense` layer with 50 neurons and `relu` activation.
* **Hidden Layer 2**: A `Dense` layer with 50 neurons and `relu` activation.
* **Output Layer**: A `Dense` layer with 2 neurons and `softmax` activation for binary classification.

### 3. Training and Evaluation
* The model was compiled using the **Adam optimizer** and **sparse categorical cross-entropy** loss function.
* An **Early Stopping** callback was used during training to monitor validation loss and prevent overfitting.
* The model was trained for 50 epochs with a batch size of 100.

---

## 💻 Technologies Used
* Python
* TensorFlow & Keras
* NumPy
* Pandas
* Scikit-learn

---

## ⚙️ How to Use

To run this project, follow these steps in order:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    cd your-repo-name
    ```
2.  **Install dependencies:**
    ```bash
    pip install tensorflow numpy pandas scikit-learn
    ```
3.  **Run the notebooks:**
    * First, execute **`Global Earthquake Tsunami Risk - Data Preprocessing.ipynb`** to generate the `Earthquake_data_train.npz`, `Earthquake_data_validate.npz`, and `Earthquake_data_test.npz` files.
    * Next, run **`Global Earthquake Tsunami Risk - Modelling.ipynb`** to train the model and create the `Earthquake.keras` file.
    * Finally, run **`Global Earthquake Tsunami Risk - Prediction.ipynb`** to use the trained model for predictions on new data.

---

## 📈 Results

The trained model achieved a final accuracy of **87.24%** on the test set, demonstrating its effectiveness in assessing tsunami risk based on the provided earthquake data.

| Metric          | Score   |
| --------------- | ------- |
| Test Loss       | 0.33    |
| **Test Accuracy** | **87.24%** |
