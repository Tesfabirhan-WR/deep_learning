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

### robots.txt Compliance

Before scraping, the robots.txt file of each website was checked to ensure that only permitted pages were accessed.

Example workflow:

1. Retrieve robots.txt
2. Verify allowed paths
3. Respect crawl restrictions
4. Introduce request delays when necessary

### Summary of ethical web-scrapping applied

```
def get(url, params=None, essais=3):
    for n in range(essais):
        time.sleep(PAUSE)                                   # pause : on ne harcèle pas le serveur
        reponse = requests.get(url, params=params, headers=ENTETES, timeout=20)
        if reponse.status_code == 200:
            return reponse
        if reponse.status_code in (429, 503):               # « trop de requêtes » : on attend plus longtemps
            time.sleep(2 ** (n + 1))
            continue
        reponse.raise_for_status()
    raise RuntimeError("Échec après " + str(essais) + " essais : " + url)
```

### Technics applied

1. API
2. Crawling
3. Scraping
---

## Project Architecture
<div align="center">

<pre>

```text
`Web Sources
     │
     ▼
Web Scraping
(Awate + Wikipedia)
     │
     ▼
Loading data(corpus)
     │
     ▼
data clustering
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
`
```
</pre>

</div>

---

## Technologies Used

### Programming Language

- Jupyter  notebook in vs code

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
```
| Model                     | Accuracy |
| --------------------------| -------- |
| Neural Network Model(NNM) | 79.1%    |
| Regression Logistics      | 78.9%    |
```
---

## Project Structure

```text
deep-learning-text-classification/
│
├──data/
|   |__awate-articles.json
|   |__corpus-secours.csv
|   |__corpus.csv
│
├── scraping/
│   ├── corpus_scraper.py
│   ├── tpa-collecter-complete.ipynb
│
├── models/
│   ├──b-premier-reseau.ipynb
|   |__c-optimiser-complete.ipynb
│
└── README.md
```

## Training parameters
```
1. test size = 0.25 (25%)
2. random stae = 42
3. Maximum features = 2000
4. stop words = english
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
- Matrix confusion
- Model Evaluation
- Python Development
- Data Engineering Fundamentals

---

## Author

Tesfabirhan

Aspiring Data Engineer & Machine Learning Practitioner
