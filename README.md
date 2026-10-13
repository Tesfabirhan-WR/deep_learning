# Deep Learning Based Text Classification Using Web Scraping

## Project Overview

This project explores the application of Deep Learning techniques for text classification using data collected from multiple web sources. The dataset was built through web scraping of articles from the Awate website and relevant content from Wikipedia.

The project includes a complete machine learning pipeline covering:

- Ethical web scraping practices
- Data collection and preprocessing
- Natural Language Processing (NLP)
- Deep Learning model development
- Model evaluation and comparison
- Performance analysis and visualization

The objective is to identify the most effective deep learning architecture for classifying textual content extracted from online sources.

---

## Data Sources

### 1. Awate

- Website: https://awate.com
- Source of news articles, opinion pieces, and historical content
- Scraping performed according to the site's robots.txt guidelines

### 2. Wikipedia

- Website: https://en.wikipedia.org
- Additional contextual and reference articles
- Public encyclopedia content used for enrichment and classification tasks

---

## Ethical Web Scraping

The web scraping process follows responsible data collection practices:

### User-Agent Configuration

A custom User-Agent header was implemented to properly identify the scraper.

Example:

```python
headers = {
    "User-Agent": "TPFormation/1.0 (greetaiates@gmail.com) python-requests)"
}
```

'''
import os, re, time
import requests, pandas as pd
from bs4 import BeautifulSoup
from urllib.robotparser import RobotFileParser

BASE = os.environ.get("WIKI_BASE", "https://en.wikipedia.org")     # le site visé
PAUSE = float(os.environ.get("WIKI_PAUSE", "1.0"))                 # secondes d'attente entre deux requêtes
ENTETES = {"User-Agent": "TPFormation/1.0 (greetaiates@gmail.com) python-requests"}   # ⚠️ remplacez par VOTRE contact

def controle(condition, ok, ko):
    print("✅", ok) if condition else print("❌", ko)
'''

### robots.txt Compliance

Before scraping, the robots.txt file of each website was checked to ensure that only permitted pages were accessed.

Example workflow:

1. Retrieve robots.txt
2. Verify allowed paths
3. Respect crawl restrictions
4. Introduce request delays when necessary

---

## Project Architecture

```text
Web Sources
     │
     ▼
Web Scraping
(Awate + Wikipedia)
     │
     ▼
Data Cleaning
     │
     ▼
Text Preprocessing
(Tokenization, Cleaning,
 Stopword Removal)
     │
     ▼
Text Vectorization
     │
     ▼
Model Training
     │
     ▼
Model Evaluation
     │
     ▼
Performance Comparison
```

---

## Technologies Used

### Programming Language

- Python 3.x

### Libraries

#### Web Scraping

- Requests
- BeautifulSoup4
- urllib.robotparser

#### Data Processing

- Pandas
- NumPy

#### NLP

- NLTK
- SpaCy
- Scikit-learn

#### Deep Learning

- TensorFlow
- Keras

#### Visualization

- Matplotlib
- Seaborn

---

## Data Preprocessing

The following preprocessing techniques were applied:

- HTML tag removal
- Lowercasing
- Tokenization
- Stopword removal
- Punctuation removal
- Text normalization
- Lemmatization
- Train/Test splitting

---

## Deep Learning Models Tested

Several deep learning architectures were implemented and compared.

### 1. Dense Neural Network (DNN)

A baseline feed-forward neural network used as a reference model.

**Advantages**

- Simple architecture
- Fast training time

---

### 2. Long Short-Term Memory (LSTM)

LSTM networks were used to capture sequential relationships within text.

**Advantages**

- Learns long-term dependencies
- Well suited for NLP tasks

---

### 3. Bidirectional LSTM

Processes text sequences in both forward and backward directions.

**Advantages**

- Better contextual understanding
- Improved classification performance

---

### 4. Gated Recurrent Unit (GRU)

Lightweight alternative to LSTM.

**Advantages**

- Faster training
- Fewer parameters

---

### 5. Convolutional Neural Network (CNN)

CNN architecture adapted for text classification.

**Advantages**

- Effective feature extraction
- Computationally efficient

---

## Model Evaluation

Models were evaluated using the following metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Training Loss
- Validation Loss

Example:

| Model | Accuracy | Precision | Recall | F1 Score |
|---------|---------|---------|---------|---------|
| DNN | XX% | XX% | XX% | XX% |
| CNN | XX% | XX% | XX% | XX% |
| LSTM | XX% | XX% | XX% | XX% |
| Bi-LSTM | XX% | XX% | XX% | XX% |
| GRU | XX% | XX% | XX% | XX% |

---

## Project Structure

```text
deep-learning-text-classification/
│
├── data/
│   ├── raw/
│   ├── processed/
│
├── notebooks/
│   └── exploratory_analysis.ipynb
│
├── scraping/
│   ├── awate_scraper.py
│   ├── wikipedia_scraper.py
│   └── robots_checker.py
│
├── preprocessing/
│   └── text_preprocessing.py
│
├── models/
│   ├── dnn_model.py
│   ├── cnn_model.py
│   ├── lstm_model.py
│   ├── bilstm_model.py
│   └── gru_model.py
│
├── evaluation/
│   └── model_comparison.py
│
├── requirements.txt
│
└── README.md
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/deep-learning-text-classification.git
```

Move to the project directory:

```bash
cd deep-learning-text-classification
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Running the Project

### Step 1: Run Web Scraping

```bash
python scraping/awate_scraper.py
python scraping/wikipedia_scraper.py
```

### Step 2: Preprocess Data

```bash
python preprocessing/text_preprocessing.py
```

### Step 3: Train Models

```bash
python models/lstm_model.py
```

or

```bash
python models/cnn_model.py
```

### Step 4: Compare Results

```bash
python evaluation/model_comparison.py
```

---

## Key Findings

- Deep learning models significantly outperformed traditional machine learning baselines.
- Recurrent architectures demonstrated superior performance on long text sequences.
- Bidirectional LSTM provided the best contextual understanding of article content.
- CNN models offered a favourable balance between accuracy and training efficiency.

---

## Future Improvements

- Transformer-based models (BERT)
- RoBERTa fine tuning
- Hyperparameter optimization
- Deployment through Flask or FastAPI
- Automated pipeline orchestration
- Cloud deployment on Azure

---

## Learning Outcomes

This project demonstrates skills in:

- Web Scraping
- Responsible Data Collection
- Natural Language Processing
- Deep Learning
- Text Classification
- Model Evaluation
- Python Development
- Data Engineering Fundamentals

---

## Author

Tesfabirhan

Aspiring Data Engineer & Machine Learning Practitioner
