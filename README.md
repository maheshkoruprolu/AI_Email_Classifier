# AI-Powered Email Classification System (Linear SVM)

## Overview

This project implements an enterprise-oriented email classification system using Machine Learning for automated email categorization.

Multiple classification algorithms were trained and evaluated. Based on comparative performance analysis, **Linear Support Vector Machine (Linear SVM)** was selected as the final deployment model.

The system enables organizations to automate email triaging, improve routing efficiency, and reduce manual operational overhead.

---

## Problem Statement

Enterprises receive large volumes of emails daily. Manual categorization leads to:

- Delayed responses  
- Inconsistent labeling  
- Increased workload for support teams  

An automated NLP-based classification system improves scalability, response time, and consistency.

---

## Approach

### 1. Data Preparation

- Dataset: `merged_data.csv`  
- Email text cleaned and normalized  
- Stopwords removed  
- Train-test split performed  

### 2. Feature Engineering

- TF-IDF vectorization converts text into numerical feature vectors  
- Sparse high-dimensional representation optimized for linear models  

---

## Model Experiments

The following models were trained and evaluated:

- Logistic Regression  
- Naive Bayes  
- Random Forest  
- Linear Support Vector Machine (SVM)  

### Performance Comparison

| Model                 | Accuracy |
|------------------------|----------|
| **Linear SVM**        | **99.22%** |
| Random Forest         | 97.50% |
| Logistic Regression   | 96.10% |
| Naive Bayes           | 92.40% |

### Model Selection Decision

- Naive Bayes was computationally efficient but showed weaker class discrimination.
- Random Forest improved performance but increased model complexity.
- Logistic Regression performed well but slightly underperformed compared to SVM.
- **Linear SVM achieved the highest accuracy (99.22%) and demonstrated strong generalization on TF-IDF features.**

Therefore, Linear SVM was selected as the final production model.

---

## Final Model

- Algorithm: Linear Support Vector Machine  
- Serialized as: `svm_model.pkl`  
- Feature representation: TF-IDF  

Linear SVM is particularly effective for text classification because:

- Text produces high-dimensional sparse vectors  
- Linear margins perform strongly in NLP tasks  
- Efficient training and inference  
- Strong generalization properties  

---

## Training Workflow

Implemented in:

`Email_classification.ipynb`

Steps:

1. Data loading  
2. Text preprocessing  
3. Train-test split  
4. TF-IDF vectorization  
5. Training multiple models  
6. Comparative evaluation  
7. Selecting best-performing model  
8. Model serialization using Pickle  

---

## Project Structure

```
AI_Email_Classifier/
│
├── Email_classification.ipynb   # Model training & experimentation
├── app.py                       # Streamlit web application
├── merged_data.csv              # Training dataset
├── svm_model.pkl                # Final trained Linear SVM model
├── requirements.txt             # Python dependencies
└── .gitignore                   # Ignored files
```

---

## Running the Project

### 1. Clone Repository

```bash
git clone https://github.com/maheshkoruprolu/AI_Email_Classifier.git
cd AI_Email_Classifier
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

If required:

```bash
pip install streamlit pandas scikit-learn numpy
```

### 3. Run the Application

```bash
streamlit run app.py
```

The web interface will open in your browser.

---

## Web Application Features

The Streamlit application allows users to:

- Enter email content  
- Submit for classification  
- View predicted category instantly  
- Get real-time model output  

The trained model is loaded from `svm_model.pkl` and applied directly to user input.

---

## Evaluation Metrics

Models were evaluated using:

- Accuracy  
- Precision  
- Recall  
- F1-Score  
- Classification Report  

Linear SVM achieved the highest overall performance among all tested algorithms.

---

## Limitations

- Performance depends on dataset quality and balance  
- No integration with live email servers  
- No persistent database storage  
- Limited contextual understanding compared to transformer-based models  

---

## Future Improvements

- Hyperparameter tuning using GridSearchCV  
- Cross-validation for stronger generalization estimates  
- Transformer-based upgrade (BERT)  
- REST API deployment using FastAPI  
- Cloud deployment (AWS/GCP/Azure)  
- Model monitoring and logging  

---

## Technologies Used

- Python  
- Scikit-learn  
- Pandas  
- Streamlit  
- TF-IDF Vectorization  
- Linear Support Vector Machine  

---

## Conclusion

This project demonstrates a complete machine learning workflow including model experimentation, comparative evaluation, selection of the best-performing algorithm, and deployment through a web interface.

Linear SVM achieved the highest accuracy (99.22%) on the given dataset, making it an efficient and scalable solution for enterprise email classification.
