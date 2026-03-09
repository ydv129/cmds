# Data Science Practices

## PRAC 3: Data Classification using Classification Algorithm

Using R with the `party` package for decision tree classification:

```r
install.packages("party")   # select 0-cloud
library("party")
data(readingSkills)

input.dat <- readingSkills[c(1:105)]
png(file="decision_tree.png")

output.tree <- ctree(nativeSpeaker ~ age + shoeSize + score, data=input.dat)
plot(output.tree)
dev.off()
```

---

## PRAC 4: Data Clustering using Clustering Algorithm

Using R with k-means clustering on the iris dataset:

```r
newiris <- iris
print(newiris)
newiris$Species <- NULL 
(kc <- kmeans(newiris, 3))
plot(newiris$Sepal.Length, newiris$Sepal.Width, col=kc$cluster, pch=16)
```

---

## PRAC 5: Linear Regression

Performing linear regression analysis on height and weight data using R:

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

---

## PRAC 6: Logistic Regression

Performing logistic regression with ROC curve analysis using Python and scikit-learn:

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
