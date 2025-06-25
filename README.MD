# 🎓 Student Performance Indicator (SPI) – End-to-End Machine Learning Project

This project is an **end-to-end machine learning application** that predicts a student's **math score** based on their socio-demographic and academic attributes. The project is modular, production-ready, and deployable using Flask.

---

## 📌 Problem Statement

Educational institutions often need early predictions of student performance to provide targeted support. This system helps in predicting **math scores** using attributes such as gender, lunch type, test preparation course, and parental education level.

---

## 🧰 Tech Stack Used

| Category             | Tools & Technologies                        |
|----------------------|---------------------------------------------|
| Language             | Python                                      |
| Data Analysis        | Pandas, NumPy, Seaborn                      |
| Machine Learning     | Scikit-learn, XGBoost                       |
| Data Visualization   | Matplotlib, Seaborn                         |
| Model Evaluation     | R² Score, GridSearchCV                      |
| Backend Deployment   | Flask, Gunicorn                             |
| Packaging            | `setup.py`, `requirements.txt`              |
| Web Interface        | HTML, CSS (Jinja Templates)                 |
| Deployment Ready     | `.ebextensions/python.config` for AWS       |
| Version Control      | Git                                         |
| IDE                  | VS Code                                     |

---

## 📂 Project Structure

```
SPI_ML/
├── .ebextensions/                  # AWS Elastic Beanstalk config
│   └── python.config
├── artifacts/                      # Stores output files (train/test data, models)
├── notebook/                       # Jupyter notebooks for EDA & model training
│   └── data/
│       ├── stud.csv                # Raw dataset
│       ├── EDA STUDENT PERFORMANCE.ipynb
│       └── MODEL TRAINING.ipynb
├── src/                            # Modularized Python codebase
│   ├── components/                 # Data pipeline components
│   │   ├── data_ingestion.py       # Read and split data
│   │   ├── data_transformation.py  # Preprocessing logic
│   │   └── model_trainer.py        # Model selection and training
│   └── pipeline/
│       ├── exception.py            # Custom error class
│       ├── logger.py               # Logging infrastructure
│       └── utils.py                # Reusable helper functions
├── static/                         # CSS files for front-end
│   └── style.css
├── templates/                      # HTML files for Flask frontend
│   ├── index.html
│   └── home.html
├── application.py                  # Flask web app
├── requirements.txt                # Python dependencies
├── setup.py                        # Project packaging
├── .gitignore                      # Git ignore rules
└── README.md                       # Project documentation
```

---

## 🔁 End-to-End Workflow

### 1. **Data Ingestion** (`data_ingestion.py`)

* Loads CSV from `notebook/data/`
* Splits into train and test datasets
* Saves files in `artifacts/`

### 2. **Data Transformation** (`data_transformation.py`)

* Defines preprocessing pipelines for numerical and categorical features
* Applies transformation using `ColumnTransformer`
* Saves preprocessor object for reuse

### 3. **Model Training** (`model_trainer.py`)

* Trains multiple models: Random Forest, Decision Tree, Gradient Boosting, XGBoost, etc.
* Performs hyperparameter tuning via GridSearchCV
* Evaluates using R² Score
* Saves best model as `model.pkl`

### 4. **Prediction Pipeline** (`application.py`)

* Built using Flask
* Takes form input from users
* Preprocesses input using saved preprocessor
* Returns predicted math score on the webpage

---

## 💡 Features

* ✅ Modular, scalable architecture
* ✅ Detailed logging and exception handling
* ✅ GridSearchCV-based model selection
* ✅ Reusable preprocessing pipeline
* ✅ Flask-based web UI for live predictions
* ✅ Ready for deployment (Elastic Beanstalk compatible)

---

## 🎨 Web Interface Snapshot

![Image](https://github.com/user-attachments/assets/c4bdc1b2-66ae-42a0-ac27-403634fa2ae9)


---

## 📊 Sample Input Data

| gender | race_ethnicity | parental_level_of_education | lunch    | test_preparation_course | reading_score | writing_score |
| ------ | -------------- | --------------------------- | -------- | ----------------------- | ------------- | ------------- |
| female | group B        | bachelor's degree           | standard | none                    | 72            | 74            |

---

## 📈 Sample Output

```
Predicted Math Score: 71.3
```

---

## 🛠 How to Run the Project Locally

1. **Clone the Repository**

```bash
git clone https://github.com/your-username/SPI_ML.git
cd SPI_ML
```

2. **Create Virtual Environment**

```bash
python -m venv venv
source venv/bin/activate  # For Linux/Mac
venv\Scripts\activate     # For Windows
```

3. **Install Dependencies**

```bash
pip install -r requirements.txt
```

4. **Run the Flask App**

```bash
python application.py
```

Then open your browser and go to:
`http://127.0.0.1:5000/`

---

## 🚀 Deployment Readiness

This project can be deployed on **AWS Elastic Beanstalk** using:

* `.ebextensions/python.config` for WSGI settings
* `application.py` as entry point
* `requirements.txt` and `setup.py` for environment creation

---

## 🙋‍♀️ Author

**Sharada Jibhau Sonaje**
💼 Aspiring Data Analyst / ML Developer
✉️ [sharadasonaje25@gmail.com](mailto:sharadasonaje25@gmail.com)
🌐 [LinkedIn](https://www.linkedin.com/in/sharada-s-83b958273)

---

## ⭐ Acknowledgements

* **SevenMentor** – for training and internship support
* **Scikit-learn & Flask** – for documentation
* **Mentor** – Mahesh Kankrale

> If you found this helpful, do ⭐ the repo and share it with fellow learners!