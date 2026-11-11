# Initial attempt
I inspected the teaching_prices_messy.csv dataset using Python.
The dataset contains:

- 97 rows
- 6 columns
- 4 intended products
- 2 cities
- 12 dates

The columns are:

1. date
2. item
3. city
4. price
5. unit
6. data_label

# Identification of some problems.
 Problem 1: Missing Value
One price is missing for Pulse C in City 2 on 2026-01-01.
Decision: RETAIN and FLAG
Reason: The correct price is  unknown, so I should not invent a replacement.

Problem 2: Incorrect Price Format
One price is written as "1,250".
Decision: INVESTIGATE
Reason: The comma needs to be removed for numeric conversion, but the price also appears
unusually high.

Problem 3: Extreme Price
One price is 9999.
Decision: FLAG
Reason: It is much higher than the other prices and may be an error.

 Problem 4: Incorrect Item Label

One item is written as "oil b" and
has a price of 108.5.
Decision: INVESTIGATE
Reason: The item name is inconsistent. The price and surrounding records suggest
the observation may belong to Staple A.

Problem 5: Duplicate Record
One identical row appears twice.
Decision: EXCLUDE the extra copy
Reason: Duplicates can affect the analysis and should not be counted twice.

# Python evidence
```python
import pandas as pd

df = pd.read_csv("teaching_prices_messy.csv")

print(df.shape)
print(df.dtypes)
print(df.isna().sum())
print(df.duplicated().sum())
print(df["item"].value_counts())

prices = pd.to_numeric(
    df["price"].astype("string").str.replace(",", ""),
    errors="coerce"
)
print(prices.describe())
```
