# Data Science Practices

## PRAC 3: Data Classification using Classification Algorithm (R)

Perform the data classification using classification algorithm using R/Python

```r
install.packages("party")   # select 0-cloud
library("party")
data(readingSkills)

input.dat <- readingSkills[c(1:105), ]
png(file="decision_tree.png")

output.tree <- ctree(nativeSpeaker ~ age + shoeSize + score, data=input.dat)
plot(output.tree)
dev.off()
```

## PRAC 4: Data Clustering using Clustering Algorithm (R)

Perform the data clustering using clustering algorithm using R/Python

```r
newiris <- iris
print(newiris)
newiris$Species <- NULL
(kc <- kmeans(newiris, 3))
plot(newiris$Sepal.Length, newiris$Sepal.Width, col=kc$cluster, pch=16)
```

## PRAC 5: Linear Regression (R)

Perform the Linear regression on the given data warehouse data using R/Python.

```r
x <- c(110, 120, 130, 140, 150, 160, 170)
y <- c(10, 20, 30, 40, 50, 60, 70)

r <- lm(y ~ x)
print(r)
print(summary(r))

a <- data.frame(x=130)
res <- predict(r, a)
print(res)

plot(x, y, main="H AND W", xlab="W", ylab="H", cex=1.3, pch=16, col="red")
abline(lm(y ~ x), col="blue", lwd="2")
```

## PRAC 6: Logistic Regression (Python)

Perform the logistic regression on the given data warehouse data using R/Python

```python
import matplotlib.pyplot as plt
from sklearn.datasets import make_classification
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import roc_curve, roc_auc_score

X, y = make_classification(n_samples=1000, n_classes=2, random_state=1)
trainX, testX, trainy, testy = train_test_split(X, y, test_size=0.5, random_state=2)

model = LogisticRegression(solver='lbfgs').fit(trainX, trainy)

lr_probs = model.predict_proba(testX)[:, 1]
ns_probs = [0] * len(testy)

ns_auc = roc_auc_score(testy, ns_probs)
lr_auc = roc_auc_score(testy, lr_probs)

print(f'No Skill: ROC AUC={ns_auc:.3f}')
print(f'Logistic: ROC AUC={lr_auc:.3f}')

ns_fpr, ns_tpr, _ = roc_curve(testy, ns_probs)
lr_fpr, lr_tpr, _ = roc_curve(testy, lr_probs)

plt.plot(ns_fpr, ns_tpr, linestyle='--', label='No Skill')
plt.plot(lr_fpr, lr_tpr, marker='.', label='Logistic')
plt.xlabel('False Positive Rate')
plt.ylabel('True Positive Rate')
plt.legend()
plt.show()
```

## K-means Clustering (Python)

```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("customer.csv")
print(data.head())

x = data[['Annual (k$)', 'Spending']]
kmeans = KMeans(n_clusters=3)
kmeans.fit(x)

y_kmeans = kmeans.predict(x)

plt.scatter(x['Annual (k$)'], x['Spending'], c=y_kmeans)
plt.show()
```

## KNN Classification (Python)

```python
from sklearn.datasets import *
from sklearn.neighbors import *
from sklearn.model_selection import *

X, y = load_iris(return_X_y=True)

Xtr, Xte, ytr, yte = train_test_split(X, y, test_size=0.3, random_state=42)
k = KNeighborsClassifier(n_neighbors=3).fit(Xtr, ytr).score(Xte, yte)
print("Accuracy", k)
```

## PRAC 8: Data Visualization using Python

Perform data visualization using Python on any sales data.

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

df = pd.read_csv("book1.csv")
print(df.head())

sns.lineplot(x="Date", y="Sales", data=df, marker='o')
plt.xticks(rotation=45)
plt.show()
```
