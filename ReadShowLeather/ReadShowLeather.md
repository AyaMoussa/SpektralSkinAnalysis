---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.15.1
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

```python
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib notebook

# Function to read and display the CSV file with correct delimiter
def read_and_display_csv(file_path):
    # Read the CSV file using semicolon as the delimiter
    df = pd.read_csv(file_path, delimiter=';')

    # Display the names of all columns
    print("Column Names:")
    print(df.columns.tolist())

    # Display the first few rows of the dataframe
    print("\nFirst Few Rows of Data:")
    return df

# Execute the function
df= read_and_display_csv("./data/Leder.csv")
df.head()
```

```python
# Ignoring the column names except for 'nm', let's plot the data
# We'll plot the numerical values of each row as separate lines in the plot
# Assuming 'nm' is the index or a similar identifier

# Re-reading the file with the first column as index
dfL = pd.read_csv("./data/Leder.csv", delimiter=';',decimal=",", index_col=0)

# Ignoring the column names except for 'nm', let's plot the data
# We'll plot the numerical values of each row as separate lines in the plot
# Assuming 'nm' is the index or a similar identifier

# Plotting
fig, axs  = plt.subplots(3,1,figsize=(6, 8))
#plt.subplots(131)
for col in dfL.columns:
    axs[0].plot(dfL.index, dfL[col])#, label=col)

plt.xlabel('nm')
axs[0].set_ylabel('Values')
plt.title('Data Visualization')
#plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left')
axs[0].grid(True)
#plt.show()


# Ignoring the column names except for 'nm', let's plot the data
# We'll plot the numerical values of each row as separate lines in the plot
# Assuming 'nm' is the index or a similar identifier

# Re-reading the file with the first column as index
dfH = pd.read_csv("./data/Holz.csv", delimiter=';',decimal=",", index_col=0)

# Ignoring the column names except for 'nm', let's plot the data
# We'll plot the numerical values of each row as separate lines in the plot
# Assuming 'nm' is the index or a similar identifier

# Plotting
#plt.figure(figsize=(12, 8))

#plt.subplots(132)
for col in dfH.columns:
    axs[1].plot(dfH.index, dfH[col])#, label=col)

plt.xlabel('nm')
axs[1].set_ylabel('Values')
plt.title('Data Visualization')
#plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left')
axs[1].grid(True)
#plt.show()


# Ignoring the column names except for 'nm', let's plot the data
# We'll plot the numerical values of each row as separate lines in the plot
# Assuming 'nm' is the index or a similar identifier

# Re-reading the file with the first column as index
dfF = pd.read_csv("./data/Fleisch.csv", delimiter=';',decimal=",", index_col=0)

# Ignoring the column names except for 'nm', let's plot the data
# We'll plot the numerical values of each row as separate lines in the plot
# Assuming 'nm' is the index or a similar identifier

# Plotting
#plt.figure(figsize=(12, 8))
#fig,ax = plt.subplots(133)
for col in dfF.columns:
    axs[2].plot(dfF.index, dfF[col])#, label=col)

plt.xlabel('nm')
axs[2].set_ylabel('Values')
plt.title('Data Visualization')
#plt.legend(bbox_to_anchor=(1.05, 1), loc='upper left')
plt.grid(True)
plt.show()

```

```python

```
