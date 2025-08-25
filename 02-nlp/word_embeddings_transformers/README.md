# Text Classification with Word Embeddings and Transformers

## Objectives
- Compare different text classification models using **word embeddings** and **Transformers**.  
- Learn to apply neural architectures for text classification tasks.  
- Understand the impact of preprocessing, tokenization, and dataset splitting on model performance.  

---

## Description
This project implements and evaluates two approaches to text classification:  
1. **Classical embedding-based neural network**  
2. **Transformer-based model**  

The workflow includes:  
- Dataset preparation and preprocessing.  
- Tokenization with spaCy.  
- Training with different validation splits.  
- Comparative evaluation of model performance.  

The focus is on analyzing accuracy, generalization capacity, and overfitting behavior.  

---

## Preprocessing / Methodology
- **Tokenization**: Used spaCy’s tokenizer to compute token statistics.  
  - For 15 random files in `comp.graphics`, the **average number of tokens** was **171.6**.  
- **Header removal**: The first **10 lines** of each file (metadata) were discarded, as they contained irrelevant email headers.  
- **Validation split**: Controlled via the parameter `validation_split` (0.1, 0.2, 0.3).  
- **Vectorization**: Fixed output sequence length of **200 tokens**, balancing between information retention and training efficiency.  

---

## Results / Key Findings
### Model Accuracy (Train vs. Validation)
| Validation Split | Model       | Train Acc. | Val. Acc. |
|------------------|-------------|------------|-----------|
| 0.1              | Classical   | 0.9572     | 0.7025    |
|                  | Transformer | 0.9626     | 0.8319    |
| 0.2              | Classical   | 0.9604     | 0.6579    |
|                  | Transformer | 0.9640     | 0.8389    |
| 0.3              | Classical   | 0.9592     | 0.6641    |
|                  | Transformer | 0.9613     | 0.8282    |

---

**Interpretation**:  
- The **classical model** shows strong overfitting: high training accuracy but low validation accuracy.  
- The **Transformer** generalizes much better, maintaining stable validation accuracy across different splits.  

### Qualitative Analysis (Example Predictions)
| Validation Split | Phrase | Classical Prediction | Transformer Prediction |
|------------------|--------|----------------------|-------------------------|
| 0.1              | F1     | comp.graphics        | comp.graphics           |
|                  | F2     | misc.forsale         | talk.politics.guns      |
|                  | F3     | sci.med              | talk.religion.misc      |
| 0.2              | F1     | comp.graphics        | comp.graphics           |
|                  | F2     | talk.politics.guns   | talk.politics.misc      |
|                  | F3     | rec.autos            | alt.atheism             |
| 0.3              | F1     | comp.graphics        | comp.graphics           |
|                  | F2     | talk.politics.guns   | talk.politics.guns      |
|                  | F3     | comp.graphics        | talk.religion.misc      |

**Insights**:  
- The Transformer demonstrates better **semantic understanding** and **stability across categories**.  
- The classical model produces inconsistent and sometimes nonsensical predictions (e.g., classifying autos as atheism).  

### Limitations
- **Classical model**:  
  - Overfits easily, struggles with ambiguous or domain-specific texts.  
  - Poor generalization, especially on complex contexts (e.g., mixing religion with cars).  
- **Transformer**:  
  - More robust, but still misclassifies ambiguous sentences.  
  - Requires significantly higher computational resources.  

---

## Adaptation to Spanish
To adapt this pipeline to **Spanish text classification**:  
- **Dataset**: Use a Spanish corpus (e.g., Spanish news groups or sentiment datasets).  
- **Preprocessing**:  
  - Replace English stopwords with Spanish ones.  
  - Use lemmatization with `es_core_news_sm` (spaCy) or NLTK’s SnowballStemmer.  
  - Handle accents and special characters (`sí` vs `si`).  
- **Modeling**: Train from scratch with Spanish data, or use a **pre-trained Spanish Transformer** (e.g., BETO or multilingual BERT).

---

## Author
Selene González Curbelo  
Universidad Internacional de la Rioja (UNIR)  
Course: *Natural Language Processing*  
Date: 2025