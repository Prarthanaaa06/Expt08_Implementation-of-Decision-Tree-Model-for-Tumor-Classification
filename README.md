# BLENDED_LEARNING
# Implementation of Decision Tree Model for Tumor Classification

## AIM:
To implement and evaluate a Decision Tree model to classify tumors as benign or malignant using a dataset of lab test results.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm

1. **Start**

2. **Import Libraries**

   * Import required libraries:

     * `pandas`
     * `train_test_split`
     * `DecisionTreeClassifier`
     * `seaborn`, `matplotlib`
     * Evaluation metrics (`accuracy`, `classification_report`, `confusion_matrix`)

3. **Load Dataset**

   * Read dataset `tumor.csv` into a DataFrame
   * Display:

     * First few rows (`head()`)
     * Column names

4. **Select Features and Target**

   * Define input features `X`:

     * All columns except `Class`
   * Define target variable `y`:

     * `Class`

5. **Split Dataset**

   * Split data into:

     * Training set (30%)
     * Testing set (70%)
   * Use `random_state = 42`

---

### **Model Training**

6. **Create Decision Tree Model**

   * Initialize `DecisionTreeClassifier`

7. **Train Model**

   * Fit the model using training data (`X_train`, `y_train`)

---

### **Prediction**

8. **Make Predictions**

   * Predict class labels using test data (`X_test`)
   * Store predictions in `y_pred`

---

### **Model Evaluation**

9. **Calculate Accuracy**

   * Compute accuracy score

10. **Generate Classification Report**

* Display:

  * Precision
  * Recall
  * F1-score

11. **Compute Confusion Matrix**

* Generate confusion matrix comparing actual vs predicted values

---

### **Visualization**

12. **Plot Confusion Matrix**

* Use heatmap to visualize confusion matrix
* Add:

  * X-axis label → Predicted
  * Y-axis label → Actual
  * Title

13. **Display Plot**

14. **End**

---

## Program:
```
/*
Program to  implement a Decision Tree model for tumor classification.
Developed by: PRARTHANA D
RegisterNumber:  21225230213

import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
import seaborn as sns
import matplotlib.pyplot as plt
from sklearn.metrics import accuracy_score, classification_report,confusion_matrix

data = pd.read_csv("tumor.csv")
print(data.head())
print(data.columns)

X = data.drop(columns=['Class'])
y = data['Class']

X_train,X_test,y_train,y_test = train_test_split(X,y,train_size=0.3,random_state=42)

model = DecisionTreeClassifier()
model.fit(X_train,y_train)

y_pred = model.predict(X_test)

print("Name: PRARTHANA D")
print("Reg. No: 212225230213")

acc = accuracy_score(y_test,y_pred)
print("Accuracy :",acc)

class_rep = classification_report(y_test,y_pred)
print("Classification Report: \n")
print(class_rep)

conf_mat= confusion_matrix(y_test,y_pred)
sns.heatmap(conf_mat,annot=True,fmt="d",cmap = 'Reds')

plt.xlabel("Predicted")
plt.ylabel("Actual")
plt.title("Confusion Matrix")
plt.show()
*/
```

## Output:
<img width="1301" height="398" alt="image" src="https://github.com/user-attachments/assets/2499d760-c0fe-480b-b3db-c0253a8ae4f7" />

<img width="1027" height="807" alt="image" src="https://github.com/user-attachments/assets/7779861f-4940-4445-8c0d-bded44b33bca" />


## Result:
Thus, the Decision Tree model was successfully implemented to classify tumors as benign or malignant, and the model’s performance was evaluated.
