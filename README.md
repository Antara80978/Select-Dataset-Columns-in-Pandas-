# 📊 Task 18: Select Dataset Columns using Pandas

Welcome to my submission for **Task 18** of the **Veda Technology AI & ML Track**.

This task focuses on understanding how to **select and access specific rows and columns from a Pandas DataFrame** using the `loc` and `iloc` methods.

For this task, the **Iris Dataset** is used to demonstrate label-based and position-based indexing.

---

## 🎯 Objectives

The main objectives of this task are:

* Understand how to access specific parts of a DataFrame.
* Learn **label-based indexing** using `loc`.
* Learn **integer position-based indexing** using `iloc`.
* Select single and multiple columns from a DataFrame.
* Understand the difference between `loc` and `iloc`.
* Practice common Pandas indexing techniques used in data analysis.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **Jupyter Notebook / Python**
* **Iris Dataset**

---

## 📂 Dataset

The **Iris Dataset** is loaded directly from a publicly available CSV file.

The dataset contains information about iris flowers, including:

* `sepal_length`
* `sepal_width`
* `petal_length`
* `petal_width`
* `species`

---

## 💻 Implementation

### 1. Import Pandas and Load Dataset

```python
import pandas as pd

# Load the Iris dataset directly via URL
url = "https://raw.githubusercontent.com/mwaskom/seaborn-data/master/iris.csv"
df = pd.read_csv(url)

# Display the first 5 rows
print("--- First 5 Rows of the Dataset ---")
print(df.head(), "\n")
```

---

### 2. Using `loc` — Label-Based Selection

`loc` is used when selecting data based on **row labels and column names**.

#### Select specific rows and columns

```python
print("--- Using loc: Rows 0 to 4 and specific columns ---")

subset_loc = df.loc[0:4, ['sepal_length', 'sepal_width', 'species']]

print(subset_loc, "\n")
```

#### Select a single column

```python
print("--- Using loc: Single column ('species') ---")

single_col_loc = df.loc[:, 'species']

print(single_col_loc.head(), "\n")
```

---

### 3. Using `iloc` — Position-Based Selection

`iloc` is used when selecting data based on **integer positions**.

#### Select rows and columns using positions

```python
print("--- Using iloc: Rows 0:5 and columns 0:3 ---")

subset_iloc = df.iloc[0:5, 0:3]

print(subset_iloc, "\n")
```

#### Select specific non-contiguous rows and columns

```python
print("--- Using iloc: Specific rows [0, 2, 4] and columns [0, 3] ---")

custom_iloc = df.iloc[[0, 2, 4], [0, 3]]

print(custom_iloc, "\n")
```

---

## 📌 `loc` vs `iloc`

| Feature        | `loc`                      | `iloc`            |
| -------------- | -------------------------- | ----------------- |
| Selection type | Label-based                | Position-based    |
| Rows           | Index labels               | Integer positions |
| Columns        | Column names               | Integer positions |
| Example        | `df.loc[0:4, ['species']]` | `df.iloc[0:5, 4]` |
| Slice endpoint | Inclusive                  | Exclusive         |

### Example

```python
df.loc[0:4]
```

includes rows **0 through 4**.

Whereas:

```python
df.iloc[0:5]
```

selects positions **0 through 4**, because the ending position `5` is excluded.

---

## 💡 Interview Questions & Answers

### Q1. What is the difference between `loc` and `iloc`?

`loc` is **label-based indexing**. It allows us to select rows and columns using their labels or column names.

`iloc` is **integer position-based indexing**. It selects rows and columns using their numerical positions.

Also, `loc` slicing is **inclusive** of the ending label, while `iloc` follows standard Python slicing and excludes the ending position.

---

### Q2. How do you select a single column in Pandas?

A single column can be selected using:

```python
df['species']
```

or:

```python
df.loc[:, 'species']
```

Bracket notation such as `df['species']` is generally preferred because it works reliably with column names containing spaces or names that conflict with DataFrame methods.

---

### Q3. How do you select multiple columns?

Multiple columns can be selected by passing a list of column names:

```python
df[['sepal_length', 'sepal_width', 'species']]
```

or using `loc`:

```python
df.loc[:, ['sepal_length', 'sepal_width', 'species']]
```

---

## ▶️ How to Run

### 1. Install Pandas

If Pandas is not already installed:

```bash
pip install pandas
```

### 2. Run the Python file

```bash
python task18.py
```

Alternatively, the code can be executed directly in a **Jupyter Notebook**.

---

## 📁 Project Structure

```text
Task-18-Select-Dataset-Columns/
│
├── task18.py
├── README.md
└── screenshots/
    └── output.png
```

---

## 📚 Key Learnings

Through this task, I learned:

* How to load a dataset using Pandas.
* How to select rows and columns from a DataFrame.
* How `loc` performs label-based selection.
* How `iloc` performs position-based selection.
* How to select single and multiple columns.
* The difference between inclusive and exclusive slicing.
* Practical Pandas indexing techniques used in data analysis.

---

## 👩‍💻 Author

**Antara Sarvade**

AI & ML Track
Veda Technology

---

⭐ **Task 18 completed successfully!**
