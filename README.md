# 🌸 Iris Flower Classification

**CodeAlpha Machine Learning Internship – Task 1**

A machine learning project that classifies Iris flowers into one of three species (*Iris-setosa*, *Iris-versicolor*, *Iris-virginica*) based on their sepal and petal measurements.

---

## 📌 Project Overview

The goal is to train a classification model that predicts the species of an Iris flower from four measurements, and to evaluate how well it performs on unseen data. This project covers the full basic machine learning workflow: data exploration, preprocessing, model training, model comparison, evaluation, and prediction on new data.

## 📊 Dataset

- **Source:** [Iris Dataset (Kaggle)](https://www.kaggle.com/datasets/saurabh00007/iriscsv)
- **Samples:** 150 (50 per species, perfectly balanced)
- **Features:**
  - `SepalLengthCm`
  - `SepalWidthCm`
  - `PetalLengthCm`
  - `PetalWidthCm`
- **Target:** `Species` (Iris-setosa, Iris-versicolor, Iris-virginica)
- **Data quality:** no missing values and no duplicate rows

## 🔄 Workflow

1. **Import libraries**
2. **Load the dataset**
3. **Exploratory data analysis:** data types, summary statistics, missing values, class balance
4. **Visualization:** pairplot and correlation heatmap
5. **Preprocessing:** dropped the `Id` column and encoded species labels with `LabelEncoder`
6. **Train/test split:** 80% train / 20% test, stratified, `random_state=42`
7. **Feature scaling:** `StandardScaler`, fitted on training data only to avoid data leakage
8. **Model training:** five classifiers compared
9. **Cross-validation:** 5-fold CV for a more reliable comparison
10. **Evaluation:** accuracy, classification report, confusion matrix
11. **Prediction:** tested the final model on new flower measurements

## 🤖 Models Used

- Logistic Regression
- K-Nearest Neighbors (KNN)
- Decision Tree
- Random Forest
- Support Vector Machine (SVM)

## 📈 Results

| Model | Test Accuracy | 5-Fold CV Accuracy |
|---|---|---|
| KNN | 0.9333 | 0.9667 |
| **SVM** | **0.9667** | **0.9667** |
| Logistic Regression | 0.9333 | 0.9583 |
| Random Forest | 0.9000 | 0.9500 |
| Decision Tree | 0.9000 | 0.9417 |

**SVM was selected as the best model.** It tied for the highest cross-validation accuracy (96.67%) and had the highest test accuracy (96.67%, 29 of 30 test samples correct).

> **Note:** The test set contains only 30 samples, so a single wrong prediction changes accuracy by about 3.3%. Cross-validation scores are a more reliable basis for comparing the models.

## 🔍 Key Insights

- **Petal length and petal width** are the most informative features for separating the species.
- *Iris-setosa* forms a clearly separate cluster, while *Iris-versicolor* and *Iris-virginica* overlap slightly.
- Simple models perform very well on small, clean datasets like Iris.
- Fitting the scaler on training data only prevents information from leaking from the test set.

## 🛠️ Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter / Kaggle Notebook

## 📁 Repository Structure

```
CodeAlpha_IrisFlowerClassification/
│
├── iris_flower_classification.ipynb   # Main notebook
├── Iris.xls                           # Dataset
└── README.md                          # Project documentation
```

## ▶️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/CodeAlpha_IrisFlowerClassification.git
   cd CodeAlpha_IrisFlowerClassification
   ```
2. Install the required libraries:
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
   ```
3. Open the notebook:
   ```bash
   jupyter notebook iris_flower_classification.ipynb
   ```
4. If running locally, update the dataset path in the notebook from the Kaggle path to `Iris.csv`:
   ```python
   df = pd.read_csv("Iris.xls")
   ```

## 🚀 Future Improvements

- Tune hyperparameters using `GridSearchCV`
- Try additional models such as Gradient Boosting or XGBoost
- Build a simple web app (Streamlit or Flask) where users enter measurements and get a prediction

## 👤 Author

**<Your Name>**
- LinkedIn: [<your-profile-link>](https://www.linkedin.com/in/feneti-tefera-748433404)
- GitHub: [<your-username>](https://github.com/teferafeneti1-coder/CodeAlpha_IrisFlowerClassification)

## 🙏 Acknowledgements

Thanks to **CodeAlpha** for the internship opportunity and the project guidance.

---

*This project was completed as part of the CodeAlpha Machine Learning Internship.*
