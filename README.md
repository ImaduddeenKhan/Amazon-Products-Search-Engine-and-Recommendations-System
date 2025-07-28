# Amazon-Products-Search-Engine-and-Recommendations-System

## Project Overview
This project implements a **search engine and product recommendation system** built in **Python**. It is designed to work with a real **Amazon product dataset**. The primary goal is to allow users to input a product query and efficiently receive **10 highly relevant product recommendations** along with their descriptions. This system demonstrates a practical application of **Machine Learning** and **Natural Language Processing (NLP)** for building an effective recommendation engine, similar to those used in e-commerce platform.

## Features
*   **Search Engine Functionality**: Accepts user product queries as input.
*   **Top 10 Recommendations**: Displays the **top 10 most relevant product recommendations** for any given query.
*   **Detailed Product Information**: Provides product titles and descriptions for each recommendation.
*   **Scalable Approach**: Utilizes concepts widely used in large-scale e-commerce platforms .

## How It Works (Technical Details)
The core functionality of this recommendation system is built upon a series of NLP and Machine Learning techniques:

1.  **Data Preprocessing**:
    *   Product titles and descriptions are initially converted to **lowercase**.
    *   **Tokenization** is applied to break down sentences into individual words.
    *   **Stemming** is performed using **NLTK's SnowballStemmer** to reduce words to their base forms (e.g., 'loving', 'loved' become 'love').
    *   **Stopwords** are removed to enhance the relevance of search terms.
    *   The processed text for both titles and descriptions is stored in a new column called 'stem_tokens'.

2.  **Text Vectorization**:
    *   To enable machines to understand text, product descriptions and user queries are transformed into **numerical vectors**.
    *   This transformation is achieved using the **TF-IDF Vectorizer (Term Frequency-Inverse Document Frequency)** from Scikit-learn. This process converts raw text into a matrix of numerical features.

3.  **Similarity Calculation**:
    *   The system uses **Cosine Similarity** (from Scikit-learn's `pairwise` module) to measure the "closeness" or similarity between the numerical vector of the user's query and the vectors of all products in the dataset.
    *   The `cosine_similarity` function takes the transformed text vectors as input and returns their similarity scores.

4.  **Recommendation Logic**:
    *   A final function takes the user query, processes it through the same NLP steps, vectorizes it, and then calculates its similarity with all products in the dataset.
    *   The products are then **sorted by their similarity scores** in descending order.
    *   Finally, the **top 10 most similar products** (title and description) are returned as recommendations.

## Tech Stack

The project relies on the following key technologies and libraries:

*   **Python**: The primary programming language used for development .
*   **Pandas**: Utilized for efficient data manipulation and handling the Amazon product dataset .
*   **NumPy**: Used for numerical operations, often in conjunction with Pandas .
*   **NLTK (Natural Language Toolkit)**: Essential for various NLP tasks, including:
    *   **Tokenization**
    *   **Stemming** (specifically using `SnowballStemmer` for English)
    *   **Stopword Removal**
*   **Scikit-learn (sklearn)**: Provides machine learning functionalities, including:
    *   `TfidfVectorizer` for text vectorization
    *   `pairwise.cosine_similarity` for calculating product relevance


## Setup and Installation
To get this project up and running on your local machine, follow these steps:

1.  **Download the Dataset**: Obtain the Amazon product dataset (mentioned as being available in the block comment section of the original video).
2.  **Create Project Folder**: Create a new folder on your system and name it `search engine and Amazon product dataset`.
3.  **Place Dataset**: Place the downloaded Amazon product dataset file inside this newly created folder.
4.  **Create Python File**: Create a new Python file (e.g., `recommendation_system.py`) inside the same project folder.
5.  **Install Libraries**: Open your terminal or command prompt and install the necessary Python libraries using pip:
    ```bash
    pip install numpy pandas nltk scikit-learn
    ```
    *   You might also need to download NLTK data: `python -m nltk.downloader popular`

## Usage
1.  **Run the Python Script**: Execute your Python script (e.g., `python recommendation_system.py`).
2.  **Input Query**: The system allows you to input a product query (e.g., a product title or a search term) into a designated search bar or function call.
3.  **Get Recommendations**: Upon entering the query, the system will process it and display the **10 most relevant product recommendations** with their descriptions.


## Dataset
The project utilizes a real **Amazon product dataset**. This dataset contains columns such as `ID`, `Title`, `Description`, and `Category`. For this project, the `ID` column is removed, and the `Title` and `Description` columns are primarily used for generating recommendations.

## Future Enhancements (Potential Developments)

*   **Database Integration**: Future versions could integrate with databases to handle product data more robustly.
*   **Misspell Word Correction**: Functionality to correct misspelled words in user queries could be added to improve search accuracy.
*   **Web Interface**: Developing a full web interface to make the recommendation system more user-friendly.

---
