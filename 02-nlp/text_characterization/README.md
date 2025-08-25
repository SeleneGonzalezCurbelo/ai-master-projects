# Text Characterization with spaCy (NER & Hate Speech Detection)

This module focuses on **text characterization** and the use of **Named-Entity Recognition (NER)** with **spaCy** to analyze and detect relevant features in messages.

## Objectives
- Gain familiarity with the **spaCy** library.  
- Process natural language text to identify and label entities such as people, locations, currencies, and organizations.  
- Distinguish between **hate comments** and **non-offensive comments** through linguistic analysis.

---

## Description
The exercise is divided into two parts:  
1. **Text preprocessing**: initial code is provided to load and clean the data.  
2. **Analysis with spaCy**: students answer questions by implementing code snippets and explaining the results.

---

### Preprocessing steps:
- Removal of duplicates.  
- Removal of irrelevant columns.  
- Removal of null values in key fields.  
- Processing and storing documents with spaCy to avoid redundant operations.

---

## Key Findings
- **Hate comments** tend to be longer and contain more recognized entities (55.56% vs. 34.91%).  
- Hate messages mention **specific people** more often (11.11% vs. 8.49%).  
- Structural differences in gender and number: more masculine singular words in hate messages.  
- Most frequent lemmas:
  - **Hate**: *pp, responsible, clown, master, sánchez, communist, fascist, church, bishop, priest*.  
  - **Non-hate**: *thing, happen, life, madrid*.  

---

## Author
Selene González Curbelo  
Universidad Internacional de la Rioja (UNIR)  
Course: *Natural Language Processing*  
Date: 2024