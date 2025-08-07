# 🗣️ Language Identification Project

This project implements and evaluates two distinct models for identifying the language of a given text from a selection of 10 languages. The goal is to compare a simple character-matching baseline against a more sophisticated deep learning model (biGRU).

## 📝 Project Overview

The core task is to classify a sentence into one of the following 10 languages: Arabic, Dutch, English, French, German, Italian, Persian, Russian, Spanish, and Turkish.

1.  **Baseline Model**: A simple model that works on the principle of character overlap. It identifies characters exclusive to each language and predicts the language based on which set has the most matches with the input text.
2.  **biGRU Model**: An advanced model using a Bidirectional Gated Recurrent Unit (biGRU) network. It processes 3-grams of characters to capture more complex patterns, achieving significantly higher accuracy.

## ✨ Features

-   **Data Collection**: Scripts to download sentence data for 10 languages from the [Tatoeba](https://tatoeba.org/) website.
-   **Text Preprocessing**: Cleans and structures raw text data into a format suitable for model training.
-   **Baseline Model**: Implements three strategies for language prediction based on unique characters.
    - Strategy 1 (First Overlap): Accuracy of 30.4%
    - Strategy 2 (Maximum Overlap): Accuracy of 41.1%
    - Strategy 3 (Subset Maximum Overlap): Accuracy of 94.0% on a 3-language subset.
-   **biGRU Model**: A powerful recurrent neural network that achieves **99.12% accuracy** on the test set.
-   **Evaluation**: Detailed performance analysis with metrics like accuracy, precision, recall, F1-score, and a confusion matrix.

## 📊 Dataset

The dataset consists of sentences from 10 languages, collected from the Tatoeba website. For model training and evaluation, a balanced dataset was created by selecting 5,000 sentences for each language, resulting in a total of 50,000 sentences.

## 🤖 Models

### Baseline Model
This model operates without any learning. It identifies characters unique to each language's training text. A new sentence is classified by finding which language's unique character set has the maximum overlap with the characters in the sentence. While simple, it performs well when languages have highly distinct character sets (e.g., Persian, English, and Russian).

### biGRU Model
This model uses a more advanced architecture for sequence processing:
-   **Input**: The model takes 3-grams of characters as input (e.g., "her" -> `[#he, her, er#]`). This captures sub-word features and is robust to typos.
-   **Architecture**: It uses an Embedding layer, 3 layers of Bidirectional GRUs, and a final linear layer to classify the language.
-   **Performance**: This approach proved to be highly effective, achieving an accuracy of **99.12%**.

## 🚀 How to Run

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/ArashNasrEsfahani/N-Gram-BiGRU-for-Multilingual-Language-Identification
    cd N-Gram-BiGRU-for-Multilingual-Language-Identification
    ```

2.  **Create a virtual environment and install dependencies:**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    pip install -r requirements.txt
    ```

3.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook
    ```

## 🛠️ Technologies Used

-   Python
-   PyTorch
-   Pandas
-   Scikit-learn
-   Matplotlib & Seaborn
-   Jupyter Notebook
-   TensorBoard
