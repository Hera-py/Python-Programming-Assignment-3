# ECE-2112-PA-3
## Made by: Hera Marishka Aquino | 2-ECE-C
Programming Assignment 3 for Advanced Computer Programming (S.Y. 2026-2027). It includes solutions to three Python problems focusing on Module 3: Pandas

Before coding, make sure to import Pandas by using:
```python
import pandas as pd
```
Also input a created list (optional):
```python
cars = pd.read_csv('cars.csv')
cars
```

# 1. Positional and Label-Based Slicing
After initializing the `cars` DataFrame, perform the following tasks:

1. Output the dataset's shape and full list of column headers.
2. Create `cars_6_to_10` by extracting rows 6 through 10 (1-indexed) via `.iloc`.
3. Select and display the columns `Model`, `mpg`, `cyl`, `hp`, and `gear` in order using column labels.
```python
print("Car Shape: ", cars.shape)
print("Column Names: ", list(cars.columns))

cars.head()
cars.tail()

cars_6_to_10 = cars.iloc[6:11]
data = {'Model': ['Duster 360', 'Merc 240D', 'Merc 230', 'Merc 280', 'Merc 280C'],
     'mpg': [14.3, 24.4, 22.8, 19.2, 17.8],
     'cyl': [8, 4, 4, 6, 6],
     'hp': [245, 62, 95, 123, 123],
     'gear': [3, 4, 4, 4, 4]}

df = pd.DataFrame(data, columns = ['Model', 'mpg', 'cyl', 'hp', 'gear'])
df
```

# 2. Model Lookup
Using conditional filtering on the `Model` column, complete the following:

1. Toyota Corolla: Locate and display its entire row. Assign this DataFrame to `toyota`.
2. Pontiac Firebird: Extract its row, retaining only the `Model`, `mpg`, `hp`, and `wt` columns. Assign this DataFrame to `pontiac`.
  Note: Both lookups must use dynamic Boolean conditions instead of hard-coded row numbers.
```python
df = cars
df

toyota = df[cars['Model'] == 'Toyota Corolla']
display(toyota)

pontiac = df.loc[cars['Model'] == 'Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
display(pontiac)
```

# 3. Multi-Model Subsetting
1. Filter `cars` using the `Model` column to extract entries for `"Datsun 710"`, `"Lotus Europa"`, and `"Ferrari Dino"`.
2. Subset the resulting rows to include only the columns `Model`, `mpg`, `cyl`, `hp`, and `gear`, storing the result in `selected_cars`.
3. Print `selected_cars` and `selected_cars.shape`.
   Constraint: Select records strictly by model value, verifying the final dimensions are (3, 5).
```python
df

data = {'Model': ['Datsun 710', 'Lotus Europa', 'Ferrari Dino'],
        'mpg': [22.8, 30.4, 19.7],
        'cyl': [4, 4, 6],
        'hp': [93, 113, 175],
        'gear': [4, 5, 5]}

selected_cars = pd.DataFrame(data, columns = ['Model', 'mpg', 'cyl', 'hp', 'gear'])
selected_cars

print("Selected Cars Shape: ", selected_cars.shape)
 ```

Thank you so much for reading!

## ReadMe file Version History:
September 9, 2026 - Initial ReadMe output uploaded.
