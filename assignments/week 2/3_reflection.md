
# Cleaning Log and Reflection
I cleaned the teaching_prices_messy.csv file using Python and pandas.

Problem 1: Missing Price
Decision: KEEP
I left the missing price as NaN because I didn't know the correct value.

Problem 2: Price 1250
Decision: MODIFY
The price was too high. I changed it to NaN.

Problem 3: Price 9999
Decision: MODIFY
This price was unrealistic. I changed it to NaN.

Problem 4: Incorrect Item
Decision: MODIFY
I changed "oil b" to "Staple A" because the price was 108.5.

Problem 5: Duplicate Row
Decision: KEEP
I removed the repeated row.

Before and After:
Rows: 97 to 96
Missing prices: 1 to 3
Duplicates: 1 to 0
Item labels: 5 to 4

AI Suggestions:
KEEP: Making a copy of the dataset.
MODIFY: I had to fix the price conversion code because it gave an error.
KEEP: Marking suspicious prices as NaN.
KEEP: Removing duplicate rows.
KEEP: Removing the extra prices column.

Reflection:
I learned how to find missing values, duplicates and incorrect prices using pandas. Some AI code gave errors, so I had to change it. I also learned that AI suggestions should be checked before using them.

AI Use:
I used ChatGPT for coding help, fixing errors and understanding the cleaning process.

Final File:
teaching_prices_clean.csv
96 rows and 6 columns.
