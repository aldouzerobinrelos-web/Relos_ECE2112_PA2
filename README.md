# Relos_ECE2112_PA2
The content of this repository contains Programming Assignment 2 for the course "Advance Computer Programming" S.Y. 2026 - 2027. This project covers 3 python problems connected to Module 2 - Numerical Python (Numpy)

# A. REPRODUCIBLE NORMALIZATION PROBLEM
The goal of this problem is to make a 5 × 5 array of random numbers and make sure the same numbers are generated every time the code is run. The values in the array are then normalized using the formula:

$$
Z = \frac{X - x}{\sigma}
$$

where $x$ is the mean of the 25 values and $\sigma$ is their population standard deviation. The normalized array is stored in `X_normalized` and saved as `X_normalized.npy`.

---

```python
np.random.seed(2112)
X = np.random.randint(10, 101, size=(5, 5))
```

`np.random.seed(2112)` uses the `seed()` function to set the starting point for the random numbers, so the same numbers are generated every time. `X = np.random.randint(10, 101, size=(5, 5))` uses the `randint()` function to generate random whole numbers from 10 to 100 and stores them in the 5 × 5 array `X`. 

```python
x = X.mean()
σ = X.std()
```


`x = X.mean()` uses the `mean()` function to find the average of all the values in `X` and stores it in `x`, while `σ = X.std()` uses the `std()` function to find the population standard deviation and stores it in `σ`. 

```python
X_normalized = (X - x) / σ
x_normalized = X_normalized.mean()
σ_normalized = X_normalized.std()
```

`X_normalized = (X - x) / σ` uses the mean and standard deviation to normalize the values and stores the result in `X_normalized`. Then, `x_normalized = X_normalized.mean()` finds the mean of the normalized array and stores it in `x_normalized`, 
while `σ_normalized = X_normalized.std()` finds its standard deviation and stores it in `σ_normalized`.

```python
display(X)

display(X_normalized)

display(x_normalized)

display(σ_normalized)

np.save("X_normalized.npy", X_normalized)
```

`display(X)` displays the original 5 × 5 array stored in `X`. `display(X_normalized)` displays the normalized array stored in `X_normalized`. `display(x_normalized)` displays the mean of the normalized array, which should be close to 0, while `display(σ_normalized)` displays its standard deviation, which should be close to 1. Finally, `np.save("X_normalized.npy", X_normalized)` uses NumPy's `save()` function to save the normalized array as `X_normalized.npy`.


# B. CUBES DIVISIBLE BY 4 PROBLEM
The goal of this problem is to make a 10 × 10 array using the cubes of the numbers from 1 to 100. The code then finds the cubed values that are divisible by 4 and stores them in `div_by_4`. The result should contain 50 values, which are then saved as `div_by_4.npy`.

---

```python
c = (np.arange(1, 101)**3).reshape(10, 10) 
```

`np.arange(1, 101)` uses the `arange()` function to create the numbers from 1 to 100 and excludes the last number. `**3` cubes each number, and `.reshape(10, 10)` arranges the 100 values into a 10 × 10 array and stores it in `c`. 

```python
div_4 = c % 4 == 0
```

`c % 4 == 0` checks which values in `c` are divisible by 4 and stores the results in `div_4`. 

```python
div_by_4 = c[div_4].reshape(5, 10)
```

`c[div_4]` selects the values where the condition is `True`, and `.reshape(5, 10)` arranges the 50 selected values into a 5 × 10 array stored in `div_by_4`.

```python
display(c.shape)

display(div_by_4)

display(div_by_4.size)

np.save("div_by_4.npy", div_by_4)
```

`display(c.shape)` displays the shape of `c`, which should be `(10, 10)`. `display(div_by_4)` displays the cubed values that are divisible by 4. `display(div_by_4.size)` displays the number of selected values, which should be 50. Finally, `np.save("div_by_4.npy", div_by_4)` saves the selected values as `div_by_4.npy`.

# C. ABOVE-MEAN SQUARES PROBLEM
The goal of this problem is to make a 6 × 6 array containing the squares of the numbers from 1 to 36. The code then finds the average of all the values and uses it to select the numbers that are greater than the average. These values are stored in `above_mean`. The result should contain 15 values and is saved as `above_mean.npy`.

---

```python
S = (np.arange(1, 37)**2).reshape(6, 6)
```
`np.arange(1, 37)` uses the `arange()` function to create the numbers from 1 to 36 excludes the last number. `**2` squares each number, and `.reshape(6, 6)` arranges the 36 values into a 6 × 6 array and stores it in `S`. 

```python
S_mean = np.mean(S)
```

`np.mean(S)` uses the `mean()` function to find the average of all the values in `S` and stores it in `S_mean`. 

```python
above_mean = S[S > S_mean].reshape(3, 5)
```

`S[S > S_mean]` selects the values in `S` that are greater than the `s_mean`. `.reshape(3, 5)` arranges the 15 selected values into a 3 × 5 array and stores it in `above_mean`.

```python
display(S)

display(S_mean)

display(above_mean)

np.save("above_mean.npy", above_mean)
```

`display(S)` displays the 6 × 6 array of squared values. `display(S_mean)` displays the average of the values in `S`. `display(above_mean)` displays the values that are greater than the mean. Finally, `np.save("above_mean.npy", above_mean)` saves the selected values as `above_mean.npy`.

---

Thank you for reading!

For the main program for Programming Assignment 2 click this link

https://github.com/aldouzerobinrelos-web/Relos_ECE2112_PA2/blob/main/RelosECE2112_PA2.ipynb

then download, then open on Google Colab or Jupyter Notebook, and run every cell.

**Readme File History:**

Sept 1 2026 - Initial Readme file upload, Started and finished 1st problem started on the 2nd problem.

Sept 2 2026 - Remade 1st problem format, and finished 2nd problem.

Sept 3 2026 - finished work on problem 3, edited code print() to display(), finished readme file.
