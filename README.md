# 🧠 Feature Engineering Notes (Quick Revision)

This repository is focused on understanding and applying three important preprocessing techniques in machine learning:

* Simple Imputer
* Ordinal Encoding
* One-Hot Encoding
* ColumnTransformer (modern approach)

---

## 📂 Dataset Summary

Dataset used: **covid_toy**

Main features:

* `age` → numeric
* `gender` → categorical
* `fever` → numeric (contains missing values)
* `cough` → categorical (ordered)
* `city` → categorical (unordered)
* `has_covid` → target

---

# 🔧 Core Concepts

## 🟡 1. Handling Missing Values (Simple Imputer)

Used when a column has missing values.

👉 Example use case:

* `fever` column has null values

📌 Key Idea:

* Replace missing values with mean (default) or other strategies
* Learn from training data, then apply to test data

---

## 🟢 2. Ordinal Encoding

Used when categories have a **natural order**

👉 Example:

* `cough`: Mild < Strong

📌 Key Idea:

* Convert categories into numbers based on order
* Order must be defined manually

---

## 🔵 3. One-Hot Encoding

Used when categories have **no order**

👉 Example:

* `gender`, `city`

📌 Key Idea:

* Create separate columns for each category
* Avoids introducing fake order

---

## 🟣 4. Combining Features

After transforming each column:

* All features are combined into a single dataset
* Final output becomes a numeric matrix ready for ML models

📌 Important:

* All inputs must have same dimensions
* Sparse vs dense mismatch can cause errors

---

# 🚀 ColumnTransformer (Best Practice)

Instead of handling each column manually:

👉 Use **ColumnTransformer** to:

* Apply different transformations to different columns
* Keep pipeline clean and scalable
* Reduce chances of mistakes

📌 Why it's better:

* Less code
* More readable
* Industry standard approach

---

# ⚠️ Common Mistakes

* Applying learning (fit) on test data
* Mixing different data formats (sparse vs dense)
* Forgetting category order in ordinal encoding
* Manually combining arrays incorrectly

---

# 💡 When to Use What?

* Missing values → Simple Imputer
* Ordered categories → Ordinal Encoding
* Unordered categories → One-Hot Encoding
* Full pipeline → ColumnTransformer

---

# 🔁 Quick Revision

* Imputer → fills missing values
* Ordinal → keeps order
* One-hot → removes order
* ColumnTransformer → handles everything together

---

# 🎯 Goal

Convert raw data into a clean numerical format so machine learning models can understand and learn from it efficiently.

---
