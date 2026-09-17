# 🏠 Sydney Housing Price Prediction and Decision Support System

## Machine Learning Mini Project — 8.1 Distinction Task

**Student:** Miss P K Didulangana Fernando
**Project:** Sydney Housing Price Prediction and Decision Support System
**Task:** 8.1 Distinction — Machine Learning Mini Project

---

## 📌 Project Overview

This project develops a machine learning-based housing price prediction and decision support system for residential properties in Sydney, Australia.

The objective is to use property characteristics to estimate the sale price of a property and provide a simple web-based interface through which users can enter property information and receive a predicted sale price.

The project follows the complete machine learning lifecycle:

**Data Collection → Data Understanding → Preprocessing → Feature Engineering → Model Development → Model Evaluation → Prediction Failure Analysis → Deployment → Reflection**

The project focuses on three Sydney suburbs representing different housing market characteristics and uses manually collected sold-property data for model development and evaluation.

---

## 🎯 Objectives

The main objectives of this project are to:

* Investigate factors associated with Sydney residential property prices.
* Prepare and analyse a manually collected housing dataset.
* Explore differences in property prices between selected Sydney suburbs.
* Perform data preprocessing and feature engineering.
* Develop and compare three regression approaches.
* Evaluate model performance using appropriate regression metrics and k-fold cross-validation.
* Investigate properties associated with the largest prediction errors.
* Select an appropriate model based on experimental evidence.
* Deploy the selected model through a Streamlit web application.
* Reflect on the limitations, biases, challenges, and practical considerations of machine learning-based property valuation.

---

## 📊 Dataset

The dataset contains **100 sold Sydney residential properties** collected from publicly available property information.

The properties were selected from three Sydney suburbs:

* **Manly**
* **Parramatta**
* **Liverpool**

The suburbs were selected because they represent substantially different housing-market contexts, including differences in location, accessibility, property characteristics, and typical property values.

The prediction target is:

**Sale Price (AUD)**

The dataset includes property characteristics used as predictive features, such as property type and physical/property-related attributes.

### Data Quality Considerations

The dataset was manually constructed from publicly available property information. During collection, some property records contained incomplete or unavailable information. Manual collection also introduces potential inconsistencies in how property characteristics are recorded.

Potential limitations include:

* relatively small dataset size;
* differences in information available for individual properties;
* missing or incomplete property attributes;
* potential selection bias in the manually collected sample;
* differences in property condition and renovations that may not be captured by structured features;
* limited representation of the broader Sydney housing market.

Therefore, predictions produced by the model should be interpreted as estimates rather than exact property valuations.

---

## 🔬 Machine Learning Workflow

### 1. Data Understanding

The dataset was explored using statistical summaries and visualisations to investigate:

* sale-price distributions;
* differences between suburbs;
* relationships between property characteristics and sale prices;
* trends in the collected observations;
* unusual observations and potential outliers.

### 2. Data Preprocessing

The dataset was prepared for machine learning by handling the relevant data-quality issues and transforming variables into a format suitable for regression modelling.

### 3. Feature Engineering

Additional features were considered and engineered to provide the models with more useful representations of the available property information.

The feature-engineering decisions were compared against the initial expectations about which property characteristics would have the strongest influence on sale price.

### 4. Model Development

Three regression models representing different modelling approaches were developed and evaluated.

The models were compared using:

* **Mean Absolute Error (MAE)**
* **Root Mean Squared Error (RMSE)**
* **R²**
* **K-fold cross-validation**

The comparison also considered model complexity, generalisation, underfitting, and overfitting.

### 5. Final Model

Based on the experimental evaluation, **Gradient Boosting Regression** was selected as the final model for the deployed prototype.

The trained model is stored in:

```text
models/final_gradient_boosting_model.pkl
```

---

## 📈 Model Evaluation

The complete model-development and evaluation process is documented in:

```text
notebooks/Sydney_Housing_Price_Prediction.ipynb
```

The notebook contains the preprocessing workflow, exploratory analysis, feature engineering, model training, cross-validation, evaluation metrics, visualisations, and prediction-error analysis.

The final model's evaluation results are reported in the project notebook and final report.

---

## ❌ Prediction Failure Analysis

The project investigates the five properties associated with the largest prediction errors.

For each property, the analysis considers:

* actual sale price;
* predicted sale price;
* prediction error;
* property characteristics;
* possible contextual factors contributing to the error.

This analysis is used to identify situations where structured property features may not provide enough information to accurately represent market value.

Potentially useful information that was unavailable or not incorporated includes factors such as:

* detailed property condition;
* renovation quality;
* exact micro-location;
* views;
* land characteristics;
* interior finishes;
* local market conditions at the time of sale;
* detailed agent descriptions and other unstructured property information.

---

## 🌐 Streamlit Application

A Streamlit-based web application was developed to demonstrate the practical use of the trained machine learning model.

Users can enter property characteristics into the application and receive an estimated sale price.

### Application Workflow

```text
User enters property information
            ↓
Input preprocessing
            ↓
Saved Gradient Boosting model
            ↓
Price prediction
            ↓
Estimated sale price displayed
```

### Run the Application

First install the required dependencies:

```bash
pip install -r requirements.txt
```

Then run:

```bash
streamlit run app/app.py
```

The application will open in a web browser.

---

## 📁 Repository Structure

```text
Sydney-Housing-Price-Prediction/
│
├── app/
│   └── app.py
│
├── data/
│   └── raw/
│       └── housing_data.csv
│
├── figures/
│   └── project analysis figures
│
├── models/
│   └── final_gradient_boosting_model.pkl
│
├── notebooks/
│   └── Sydney_Housing_Price_Prediction.ipynb
│
├── report/
│   └── final project report
│
└── requirements.txt
```

---

## 💻 Reproducibility

To reproduce the project:

### 1. Clone the repository

```bash
git clone <repository-url>
```

### 2. Open the project directory

```bash
cd Sydney-Housing-Price-Prediction
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Open the notebook

```text
notebooks/Sydney_Housing_Price_Prediction.ipynb
```

Run the notebook from start to finish to reproduce the analysis and model-development workflow.

### 5. Run the application

```bash
streamlit run app/app.py
```

---

## ⚠️ Limitations

This project is an academic machine learning prototype rather than a professional property valuation service.

Important limitations include:

* the dataset contains only 100 properties;
* only three Sydney suburbs are represented;
* manually collected data may contain inconsistencies;
* some potentially important property characteristics are unavailable;
* property prices can be affected by factors that are difficult to represent numerically;
* the model may perform differently on properties outside the characteristics represented in the training data;
* predictions should therefore not be interpreted as guaranteed market values.

The model should be treated as a decision-support tool rather than a replacement for professional property valuation.

---

## 🔮 Future Improvements

The system could be improved by:

* collecting a substantially larger dataset;
* including more Sydney suburbs;
* incorporating historical market indicators;
* adding geospatial features such as distance to CBD, transport, schools, and amenities;
* incorporating land size and more detailed property characteristics;
* using natural language processing on real-estate agent descriptions;
* collecting more detailed renovation and property-condition information;
* performing systematic hyperparameter optimisation;
* evaluating the system on a larger independent test dataset;
* deploying the application through a cloud platform.

---

## 🤖 GenAI Acknowledgement

Generative AI tools were used as a support tool during the development of this project. Assistance was used for activities such as explaining programming concepts, troubleshooting code, improving documentation, structuring written explanations, and supporting interpretation of machine learning concepts.

The student reviewed, tested, and adapted the generated suggestions and remains responsible for the submitted code, analysis, results, and conclusions.

---

## 📚 Project Documentation

The complete machine learning implementation is available in:

```text
notebooks/Sydney_Housing_Price_Prediction.ipynb
```

The deployed application source code is available in:

```text
app/app.py
```

The trained model is available in:

```text
models/final_gradient_boosting_model.pkl
```

The final report will be provided in:

```text
report/
```

---

## 👩‍💻 Author

**Miss P K Didulangana Fernando**

Machine Learning Mini Project — Sydney Housing Price Prediction and Decision Support System
