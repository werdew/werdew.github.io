# K-means


```python
from ucimlrepo import fetch_ucirepo
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

# fetch dataset 
iris = fetch_ucirepo(id=53) 
  
# data (as pandas dataframes)
w = iris.data.original
X = iris.data.features 
y = iris.data.targets

# Summary
print("Features first 5 rows:")
print(X.head())
print("\nFeatures shape:", X.shape)
print("\nFeatures stats:")
print(X.describe())
print("\nTargets distribution:", y.value_counts())

# Overview plot:
sns.pairplot(w, hue= 'class')
plt.show()

# Simple rules model:
# if 8/3 petal width + petal_legth <= 4  -> iris-setosa
# if 2 petal width + petal_length <= 8 -> iris-versicolor
# else iris-virginica

# plot:
sns.scatterplot(
    data=w, 
    x="petal width", 
    y="petal length", 
    hue="class",
)

x = np.linspace(0, 8, 300)

plt.fill_between(x, 0, -8/3 * x + 4, 
                 color='blue', alpha=0.12)
plt.fill_between(x, -8/3 * x + 4, -2 *  x + 8, 
                 color='red', alpha=0.12)
plt.fill_between(x, -2 *  x + 8, 8, 
                 color='green', alpha=0.12)

plt.xlim(0, 3)
plt.ylim(0, 8)
plt.title('Rule-Based Classifier\n(petal width vs petal length)', 
          fontsize=14, fontweight='bold')
plt.show()

# implement rules:
def simple_rules(pw, pl):
    if ((8/3) * pw + pl) <= 4:
        return "Iris-setosa"
    elif (2 * pw + pl) <= 8:
        return "Iris-versicolor"
    else:
        return "Iris-virginica"

w["simple_rules"] = w.apply(lambda row: simple_rules(row["petal width"], row["petal length"\
]), axis=1)


# Evaluation metrics:
accuracy = (w['class'] == w['simple_rules']).mean() * 100
print(f"Overall Accuracy: {accuracy:.2f}%")

# Confusion Matrix
cm = pd.crosstab(
    w['class'], 
    w['simple_rules'], 
    rownames=['Actual class'], 
    colnames=['Predicted class']
)
print("\nConfusion Matrix:")
print(cm)



plt.scatter(X.["sepal width"], X["sepal length"])
plt.xlabel("sepal width")
plt.ylabel("sepal length")
plt.title("Sepal width/length Scatter Plot")
plt.show()

``` 
