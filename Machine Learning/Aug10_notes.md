# Logistic Regression — Complete Study Notes

---


## 1. What is Logistic Regression? 

**Goal: Classification** — not prediction of a number, but prediction of a **category**.

Think of it this way:
- If you're predicting a **quantity** (like house price, stock value, temperature) → that's **Linear Regression**.
- If you're predicting a **label/category** (yes or no, spam or not spam, disease or no disease) → that's **Logistic Regression**.

>  **Important tip:** Despite having "regression" in the name, Logistic Regression is a **classification algorithm**, not a regression algorithm. Interviewers love asking this as a trick question.

### Key question it answers:
Is your target variable **qualitative** (also called **categorical data**)? If yes → Logistic Regression is a candidate model.

- **Qualitative/Categorical data** = data that falls into categories/labels (e.g., "Male/Female", "Diabetic/Not Diabetic") rather than a continuous number.

---

## 2. How Logistic Regression Relates to Linear Regression

Logistic Regression actually **builds on top of** Linear Regression.

**Linear Regression equation:**
```
y = mx + c
```
Where:
- `y` = predicted output
- `m` = slope (weight/coefficient)
- `x` = input feature
- `c` = intercept (bias)

### The key difference between Linear and Logistic Regression:

| | **Linear Regression** | **Logistic Regression** |
|---|---|---|
| **Output type** | Continuous number (actual value) | Class/category (which group something belongs to) |
| **Use case example** | Predicting price of land, stock market value | Predicting male/female, diabetic/non-diabetic |
| **What it finds** | Best-fit line through data points | Best **boundary line** (decision boundary) that separates classes |
| **Goal** | Minimize distance between line and data points | Find a line that **best divides** two (or more) classes |

>  **Important tip:** The line that separates classes in Logistic Regression is called the **decision boundary**. In Linear Regression, the analogous concept is called the **best-fit line/line of best fit**.

---

## 3. The Sigmoid Function

This is the **heart** of Logistic Regression — it's what converts a regression-style output into a classification output.

### What it does:
The **Sigmoid Function** takes any real number output (which could be anything from -∞ to +∞, like from a linear equation) and **squeezes/compresses** it into a value **between 0 and 1**.

```
Sigmoid function range: 0 to 1
```

### Why this matters:
A value between 0 and 1 can be interpreted as a **probability**. For example, 0.85 could mean "85% probability this belongs to Class 1."

>  **Important Tip — memorize this formula:**
> ```
> σ(z) = 1 / (1 + e^(-z))
> ```
> Where `z` is the output of the linear equation (like `mx + c`), and `e` is Euler's number (~2.718). This is called the **sigmoid** or **logistic function** — this is *why* the algorithm is called "logistic" regression.

### Threshold Value

Once you have a probability (0 to 1), you need a cutoff point to decide "this is Class 0" vs "this is Class 1." That cutoff is called the **threshold value**.

- Commonly the threshold is set at **0.5** by default (below 0.5 = Class 0, above 0.5 = Class 1), but it can be tuned.
- **How is the threshold value decided/optimized?** → This is determined using something called a **Cost Function**.

>  **Important tip:** The cost function commonly used in Logistic Regression is called **Log Loss** or **Binary Cross-Entropy**. (Your notes flagged "cost function" as the concept to explore next — this is the technical term for it.)

---

## 4. Handling More Than 2 Categories: Multinomial Logistic Regression & Softmax

So far we've talked about **binary classification** (only 2 outcomes, like Yes/No). But what if there are **more than 2 categories**? (e.g., classifying an animal as Cat, Dog, or Rabbit)

This is called **Multinomial Logistic Regression**.

### Softmax Function
To handle multiple (multinomial) classes, we use the **Softmax function** instead of (or as an extension of) the sigmoid function.

- **What it does:** Converts raw output values/scores into probabilities for **each class**.
- **Key rule:** The total sum of the probabilities of **all class labels must equal 1** (i.e., 100%).

> Important tip:** This distinction is very commonly asked in interviews.

| Aspect | Sigmoid | Softmax |
|---|---|---|
| Used for | Binary classification (2 classes) | Multiclass / multinomial classification (3+ classes) |
| Output | A single probability between 0 and 1 | A probability for each class |
| Sum of outputs | Not required to sum to 1 | Always sums to 1 (100%) |

---

## 5. Summary Table: Linear vs. Logistic Regression

| Aspect | Linear Regression | Logistic Regression |
|---|---|---|
| Example use case | Predicting price of land, stock market prices | Determining if someone is Male/Female, Diabetic/Non-diabetic |
| Output | **Actual/continuous value** | **Decides which class/category** a data point belongs to |
| What you're predicting | A number | A particular class label |

---

## 6. Evaluating a Classification Model

Once you've built a Logistic Regression model, how do you know if it's *good*? This is where **model evaluation metrics** come in.

### The Confusion Matrix

The **Confusion Matrix** is a table that compares your model's **predicted values** against the **actual values**. It's the foundation for almost every classification metric.

|  | **Actual: Positive (1)** | **Actual: Negative (0)** |
|---|---|---|
| **Predicted: Positive (1)** | TP (True Positive) | FP (False Positive) |
| **Predicted: Negative (0)** | FN (False Negative) | TN (True Negative) |

### The four building blocks (memorize these — very common interview question):

- **True Positive (TP):** A result that was **predicted positive** and **is actually positive**. (Model said "yes," and it was actually "yes.")
- **True Negative (TN):** Model predicted negative, and it was actually negative. (Correct rejection.)
- **False Positive (FP):** Model predicted positive, but it was actually negative. (Also called a **"Type I Error"** — a false alarm.)
- **False Negative (FN):** Model predicted negative, but it was actually positive. (Also called a **"Type II Error"** — a missed detection.)

> 💡 **Important tip:** A classic example is cancer diagnosis. A **False Negative** (telling a sick patient they're healthy) is usually far more dangerous than a **False Positive** (telling a healthy patient they might be sick) — so depending on the real-world context, you may care more about minimizing FN or FP specifically.

---

## 7. Key Evaluation Metrics

### 1. Accuracy
Measures: out of **all** predictions, how many were correct overall.

```
Accuracy = (TP + TN) / (TP + TN + FP + FN)
```
In plain English: **total correct classifications ÷ total number of classifications made.**

Important tip :** Accuracy can be **misleading** when your data is *imbalanced* (e.g., 950 healthy patients and only 50 sick patients). A model could just predict "healthy" every time and still get 95% accuracy while being useless at catching sick patients. This is exactly the problem your notes describe next ("high accuracy but performed poorly in terms of Precision & Recall").

### 2. Recall (also called Sensitivity or True Positive Rate)
Measures: out of **all the actual positive cases**, how many did the model correctly catch?

```
Recall = TP / (TP + FN)
```
Example from notes: Out of all cancer patients (say 180 total), how many did the model correctly identify as having cancer?

> Use Recall when **missing a positive case is costly** (e.g., missing a cancer diagnosis, missing fraud).

### 3. Precision
Measures: out of **all the cases the model predicted as positive**, how many were *actually* positive?

```
Precision = TP / (TP + FP)
```
In plain English: **A measure of, among all the positive predictions, how many are actually correct.**

> Use Precision when **false alarms are costly** (e.g., flagging legitimate emails as spam).

### 4. The Trade-off: F1 Score
There's often a **trade-off between Precision and Recall** — improving one can hurt the other. The **F1 Score** balances both into a single number.

```
F1 Score = 2 × (Precision × Recall) / (Precision + Recall)
```
This is the **harmonic mean** of Precision and Recall, and it gives **equal importance** to both.

>  **Important tip:** F1 Score is preferred over plain Accuracy when dealing with **imbalanced datasets**.

### 5. Specificity (True Negative Rate)
Measures how well the model identifies actual negatives.
```
Specificity = TN / (TN + FP)
```
(This is the "mirror image" of Recall — Recall focuses on catching positives, Specificity focuses on catching negatives correctly.)

---

## 8. ROC Curve and AUC

### ROC (Receiver Operating Characteristic) Curve
A graph used to visualize how well a classification model performs **across different threshold values** (remember the threshold concept from Section 3? This is where it comes back).

- **X-axis:** False Positive Rate (which equals `1 − Specificity`)
- **Y-axis:** True Positive Rate / Recall / Sensitivity

The curve shows the trade-off between catching true positives and accidentally flagging false positives, as you slide the threshold value up or down.

### AUC (Area Under the Curve)
- AUC helps you **choose the best model** when comparing multiple ROC curves.
- **The best model is the one with the maximum area under its ROC curve** — the closer AUC is to 1, the better the model is at distinguishing between classes. An AUC of 0.5 means the model is no better than random guessing.

> 💡 **Important tip:** AUC-ROC is one of the most frequently asked evaluation topics in data/ML interviews. Be ready to explain: *"A model with AUC = 0.9 correctly ranks a random positive example higher than a random negative example 90% of the time."*

---

## 9. Quick-Reference Cheat Sheet (for interview prep)

| Term | One-line Definition |
|---|---|
| **Logistic Regression** | A classification algorithm that predicts categories, not numbers |
| **Sigmoid Function** | Squeezes any value into a range between 0 and 1 (probability) |
| **Softmax Function** | Extension of sigmoid for multi-class (3+) classification; all class probabilities sum to 1 |
| **Threshold Value** | The cutoff probability (often 0.5) used to decide the final class |
| **Cost Function (Log Loss)** | The function used to measure and optimize model error, which determines the threshold |
| **Decision Boundary** | The line/boundary that separates predicted classes |
| **Confusion Matrix** | Table comparing predicted vs. actual outcomes (TP, TN, FP, FN) |
| **Accuracy** | % of total predictions that were correct |
| **Precision** | Of predicted positives, % that were actually correct |
| **Recall (Sensitivity)** | Of actual positives, % that were correctly caught |
| **Specificity** | Of actual negatives, % that were correctly caught |
| **F1 Score** | Harmonic mean balancing Precision and Recall |
| **ROC Curve** | Graph of True Positive Rate vs. False Positive Rate across thresholds |
| **AUC** | Area under the ROC curve; higher = better model |
| **Type I Error** | A False Positive |
| **Type II Error** | A False Negative |

---

