

# basic_pandas.py
# Author: Md Abul Hussain
# Purpose: Learn the basics of pandas for data analysis

import pandas as pd

# -----------------------------
# 1️⃣ Create a DataFrame (like an Excel table)
# -----------------------------
data = {
    "Industry": ["Textile", "Tannery", "Food Processing", "Plastic", "Pharma"],
    "COD_mg_L": [340, 550, 210, 430, 310],
    "BOD_mg_L": [120, 200, 90, 160, 130]
}

df = pd.DataFrame(data)
print("🔹 Original DataFrame:\n")
print(df, "\n")

# -----------------------------
# 2️⃣ View Basic Information
# -----------------------------
print("🔹 Basic Info:")
print(df.info(), "\n")

print("🔹 Summary Statistics:")
print(df.describe(), "\n")

# -----------------------------
# 3️⃣ Access Columns and Rows
# -----------------------------
print("🔹 COD Column Only:")
print(df["COD_mg_L"], "\n")

print("🔹 First Two Rows:")
print(df.head(2), "\n")

# -----------------------------
# 4️⃣ Add a New Column
# -----------------------------
df["COD_BOD_Ratio"] = df["COD_mg_L"] / df["BOD_mg_L"]
print("🔹 Added COD/BOD Ratio Column:\n")
print(df, "\n")

# -----------------------------
# 5️⃣ Filter Data
# -----------------------------
high_pollution = df[df["COD_mg_L"] > 400]
print("🔹 High Pollution Samples (COD > 400):\n")
print(high_pollution, "\n")

# -----------------------------
# 6️⃣ Save to CSV
# -----------------------------
df.to_csv("basic_pandas_output.csv", index=False)
print("✅ Data saved to 'basic_pandas_output.csv'")



