# **Complete Pandas Library**

A comprehensive walkthrough of the Python Pandas library, updated with current best practices and features.  
This project includes clear explanations, practical examples, and hands-on code to help you build strong data analysis skills using Pandas.

## 📁 Project Files

All code used in this tutorial is included in the notebook:

**`Syntecxhub_Pandas_CSV_Reader_Basic_Analysis.ipynb`**

## Getting Started with Pandas (Local Setup)

Below are the steps to set up your local environment and begin working with Pandas.

### 1. Install Python

Make sure Python is installed on your device.  
You can download it from the official Python website.

### 2. Fork the Repository

Go to the main repository (**complete-pandas-tutorial**) and click **Fork** to create a copy in your own GitHub ac

### 3. Clone Your Fork

Open a terminal and run:

```bash
git clone https://github.com/mahpara810/Syntecxhub_Pandas-CSV-reader-basic-analysis.git
cd Syntecxhub_Pandas-CSV-reader-basic-analysis

### 4. Create a Virtual Environment (Optional but Recommended)

Create a virtual environment by running:

```bash
python -m venv myenv

**Windows**

Activate the virtual environment:

```bash
myenv\Scripts\activate

**macOS/Linux**

Activate the virtual environment:

```bash
source myenv/bin/activate

To deactivate the virtual environment, run:

```bash
deactivate

### 5. Install Required Packages

Install all necessary libraries using:

```bash
pip install -r requirements.txt

### 6. Open in Your Code Editor

Use VS Code, PyCharm, or any code editor of your choice.  
Open the cloned project folder to start working.

### 7. Create or Open a Jupyter Notebook

- In VS Code: create a new `.ipynb` file  
- In PyCharm: right-click → New → Jupyter Notebook  
- OR run the following command in your terminal:

```bash
jupyter notebook

## Using Google Colab

If you prefer working online, open **Google Colab** and start a new notebook.  
You can upload your CSV, Excel, or Parquet files and begin coding immediately.

## 📘 Pandas Cheat Sheet (My Notes)

### Creating DataFrames

```python
import pandas as pd
import numpy as np

df = pd.DataFrame(
    [[1, 2, 3], [4, 5, 6], [7, 8, 9], [10, 11, 12]],
    columns=["A", "B", "C"],
    index=["x", "y", "z", "zz"]
)

df.head()
df.tail(2)

### Loading Data

```python
pd.read_csv("Data/coffee.csv")
pd.read_parquet("Data/results.parquet")
pd.read_excel("Data/olympics-data.xlsx", sheet_name="results")

### Accessing Data

```python
df.columns
df.index
df.info()
df.describe()
df.nunique()
df['A'].unique()
df.shape
df.size

### Filtering Data

```python
bios[bios["height_cm"] > 215]
bios[(bios["height_cm"] > 215) & (bios["born_country"] == "USA")]
bios[bios["name"].str.contains("keith", case=False)]
bios[bios["name"].str.contains(r"^[AEIOUaeiou]", na=False)]

### Adding / Removing Columns

```python
coffee["price"] = 4.99
coffee["new_price"] = np.where(coffee["Coffee Type"] == "Espresso", 3.99, 5.99)
coffee.drop(columns=["price"], inplace=True)
coffee.rename(columns={"new_price": "price"}, inplace=True)
coffee["revenue"] = coffee["Units Sold"] * coffee["price"]

### Merging & Concatenation

```python
bios_new = pd.merge(bios, nocs, left_on="born_country", right_on="NOC", how="left")
pd.concat([usa, gbr])

### Handling Missing Values

```python
coffee["Units Sold"].fillna(0, inplace=True)
coffee["Units Sold"].interpolate(inplace=True)
coffee.dropna(subset=["Units Sold"], inplace=True)

### Aggregations

```python
bios["born_city"].value_counts()
coffee.groupby("Coffee Type")["Units Sold"].sum()
coffee.groupby("Coffee Type")["Units Sold"].mean()
coffee.pivot(columns="Coffee Type", index="Day", values="revenue")

### Advanced Operations

```python
coffee["cumsum"] = coffee["Units Sold"].cumsum()
latte["3day"] = latte["Units Sold"].rolling(3).sum()
bios["height_rank"] = bios["height_cm"].rank(ascending=False)
coffee["yesterday_revenue"] = coffee["revenue"].shift(1)

# 📌 About This Project

This repository contains all the concepts, examples, and code I learned while completing a full Pandas tutorial.  
The content has been rewritten in my own words, with added explanations to make it easier for beginners and intermediate users to understand Pandas.



