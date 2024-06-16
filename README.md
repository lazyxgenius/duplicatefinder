Overview of the Project
This project involves creating a system to identify duplicate records in a database. 
The system uses fuzzy matching techniques to compare rows in the database and identify potential duplicates. 
The identified duplicates are then classified using machine learning models.

Files and Their Functions
DBcreation.py:
This file creates a database connection using SQLAlchemy and fetches data from the doctorsdata table.
It preprocesses the data by replacing null values with empty strings and merging address lines.
It defines functions for calculating similarity scores using fuzzy matching techniques (partial ratio, word ratio, and token sort ratio).
It compares rows in the database based on these similarity scores and identifies potential duplicates.
The identified duplicates are labeled as "Duplicate" or "Not-Duplicate" based on their National Provider Identifier.

trainingMLmodel.py:
This file loads the preprocessed data from CSV files and trains various machine learning models -
(Logistic Regression, Decision Tree Classifier, K-Nearest Neighbors, Linear Discriminant Analysis, Naive Bayes, and Support Vector Machine) on the data.
It evaluates the performance of each model using cross-validation and selects the best model based on its accuracy.
The selected model is then used to classify the identified duplicates.

test.py:
This file loads the trained model and uses it to predict duplicates in the database.
It compares the predicted duplicates with the actual labels and evaluates the model's performance.



### Files
- `DBcreation.py`: Creates database connection, preprocesses data, and identifies potential duplicates.
- `trainingMLmodel.py`: Trains machine learning models on the preprocessed data and selects the best model.
- `test.py`: Uses the trained model to predict duplicates and evaluates its performance.
- `data_200.csv`: The dataset used.
- `BOXPLOT.png`: Different model comparison.
- `saved_DTC.joblib`: saved Decision Tree Model.
- `reports.png`: classification report of DTC.

### Usage
1. Run `DBcreation.py` to create the database connection and preprocess the data.
2. Run `trainingMLmodel.py` to train the machine learning models and select the best one.
3. Run `test.py` to use the trained model to predict duplicates and evaluate its performance.

### Requirements
- `pandas`
- `SQLAlchemy`
- `psycopg2`
- `fuzzywuzzy`
- `joblib`
- `scikit-learn`
