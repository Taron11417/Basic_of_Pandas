


import pandas as pd

# Create DataFrame
data = {
    "Industry": ["Textile", "Tannery", "Food Processing", "Plastic", "Pharma"],
    "COD_mg_L": [340, 550, 210, 430, 310],
    "BOD_mg_L": [120, 200, 90, 160, 130]
}

df = pd.DataFrame(data)

# Display data
print(df)

# Basic info
print(df.info())
print(df.describe())

# Access specific column
print(df["COD_mg_L"])

# Add new column
df["COD_BOD_Ratio"] = df["COD_mg_L"] / df["BOD_mg_L"]

# Filter data
high_pollution = df[df["COD_mg_L"] > 400]
print(high_pollution)

# Save to CSV
df.to_csv("basic_pandas_output.csv", index=False)