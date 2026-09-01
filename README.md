# Relos_ECE2112_PA2
The content of this repository contains Programming Assignment 2 for the course "Advance Computer Programming" S.Y. 2026 - 2027. This project covers 3 python problems connected to Module 2 - Numerical Python (Numpy)

# A. REPRODUCIBLE NORMALIZATION PROBLEM
The goal of this problem is to Create a reproducible random 5 × 5 integer ndarray named X. Use the following two statements before
performing any calculation:
```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```
Normalize the complete array using

$$
Z = \frac{X - x}{\sigma}
$$

where x is the mean of all 25 elements and σ is their population standard deviation as returned by
NumPy’s default std() call. Store the normalized array in X normalized.

 **Full Code with Explanation**
 
```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
x = X.mean()
σ = X.std()
X_normalized = (X - x) / σ
x_normalized = X_normalized.mean()
σ_normalized = X_normalized.std()
```
`np.random.seed(2112)` uses the `seed()` function to set the starting point for generating random numbers, so the same numbers are produced every time. `X = np.random.randint(10, 101, size=(5, 5))` uses the `randint()` function to generate random whole numbers from 10 to 100 and stores the 5 × 5 array in `X`. `x = X.mean()` uses the `mean()` function to find the average of all the values in `X` and stores it in `x`, while `σ = X.std()` uses the `std()` function to find the standard deviation of the values and stores it in `σ`. `X_normalized = (X - x) / σ` normalizes the values using the mean and standard deviation and stores the new array in `X_normalized`. Finally, `x_normalized = X_normalized.mean()` uses the `mean()` function to find the mean of the normalized array and stores it in `x_normalized`, while `σ_normalized = X_normalized.std()` uses the `std()` function to find its standard deviation and stores it in `σ_normalized`. The normalized mean should be close to 0 and the normalized standard deviation should be close to 1.


```python
print(X)

print(X_normalized)

print(x_normalized)

print(σ_normalized)

np.save("X_normalized.npy",X_normalized)
```
`print(X)` displays the original 5 × 5 array stored in `X`. `print(X_normalized)` displays the normalized array stored in `X_normalized`. `print(x_normalized)` displays the mean of the normalized array, which should be close to 0. `print(σ_normalized)` displays the standard deviation of the normalized array, which should be close to 1. Finally, `np.save("X_normalized.npy", X_normalized)` uses NumPy's `save()` function to save the normalized array from `X_normalized` into a file named `X_normalized.npy`.

# B. CUBES DIVISIBLE BY 4 PROBLEM


**Readme File History:**

Sept 1 2026 - Initial Readme file upload, Started and finished 1st problem started on the 2nd problem
