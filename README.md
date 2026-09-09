# ECE-2112-PA-2
## Made by: Hera Marishka Aquino | 2-ECE-C
Programming Assignment 2 for Advanced Computer Programming (S.Y. 2026-2027). It includes solutions to three Python problems focusing on Module 2: Numerical Python (NumPy)

Before coding, make sure to import NumPy by using:
```python
import numpy as np
```

# 1. Reproducible Normalization Problem
Initialize a 5×5 NumPy array `⁠X`⁠ using random integers from 10 to 100 with seed ⁠`2112`⁠. Apply Z-score standardization across all 25 elements using NumPy's default ⁠`mean()`⁠ and ⁠`std()`⁠ functions, saving the standardized array to `⁠X_normalized⁠`.

1. Display `X` and `X_normalized`
2. Print the mean and standard deviation of `X_normalized` for validation.
3. Save `X_normalized` as an `.npy` file named `X_normalized.npy`
```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))

m = np.mean(X)
s = np.std(X)

X_normalized = (X - m) / s

print("Problem A values \n")
print("Array: \n", X)
print("\n X_normalized: \n", X_normalized)
print("\n Normalized Mean: \n", np.mean(X_normalized))
print("\n Normalized Standard Deviation: \n", np.std(X_normalized))

np.save("X_normalized.npy", X_normalized)
```

# 2. Cubes Divisible by 4 Problem
1. Construct a 10 x 10 NumPy array `⁠C`⁠ containing the cubes of integers from 1 through 100.
2. Apply a Boolean mask to `⁠C`⁠ to select elements divisible by 4 in row-major order and save the result to `⁠div_by_4`⁠.
3. Display ⁠`C.shape`⁠, `⁠div_by_4`⁠, and ⁠`len(div_by_4)`⁠ to confirm a 50-element array bounded by 8 and 1,000,000.
4. Export the resulting array as `⁠div_by_4.npy⁠`.
```python
integers = np.arange(1, 101)
cubes = integers ** 3
C = cubes.reshape(10, 10)

div_by_4 = C [C % 4 == 0]

print("Problem B values \n")
print("Shape of C: \n", C.shape)
print("\n Array Divisible by 4: \n", div_by_4)
print("\n Number of Selected elements: \n", len(div_by_4))

np.save("div_by_4", div_by_4)
```

# 3. Above-Mean Squares Problem
1. Construct a 6 x 6 NumPy array ⁠`S⁠` containing the squared values of the first 36 positive integers in row-major order.
2. Calculate the average of all elements as `⁠S_mean`⁠.
3. Apply a Boolean filter to select elements where `S > S (mean)`, saving the output to `⁠above_mean`⁠.
4. Display `⁠S`⁠, `⁠S_mean`⁠, `⁠above_mean`⁠, and its element count to confirm 15 items ranging from 484 to 1,296.
5. Export ⁠`above_mean⁠` to `⁠above_mean.npy`⁠.
```python
integers_36 = np.arange(1, 37)
squares = integers_36 ** 2
S = squares.reshape(6, 6)

S_mean = S.mean()

above_mean = S[S > S_mean]

print("Problem C: \n")
print("Array S: \n", S)
print("\n S_mean: \n", S_mean)
print("\n above_mean: \n", above_mean)
print("\n Number of Selected Elements: \n", len(above_mean))

np.save("above_mean.npy", above_mean)
 ```

Thank you so much for reading!

## ReadMe file Version History:
September 3, 2026 - Initial ReadMe output uploaded.
