# NumPy Notes

## Why NumPy?

* Fast numerical computations.
* Written in C under the hood.
* Foundation of Pandas, Scikit-Learn, TensorFlow, and PyTorch.
* Used heavily in Data Science and Machine Learning.

---

## Creating Arrays

```python
sample_array = np.array([1, 2, 3])

ones = np.ones((2, 3))

zeros = np.zeros((2, 3))

range_array = np.arange(0, 10, 2)

random_array = np.random.randint(0, 10, size=(3, 5))

random_array_2 = np.random.random((5, 3))

random_array_3 = np.random.rand(5, 3)
```

---

## Array Attributes

```python
a1 = np.array([1, 2, 3])

a2 = np.array([[1, 2, 3.3],
               [4, 5, 6.5]])

a3 = np.array([[[1, 2, 3],
                [4, 5, 6],
                [7, 8, 9]],
               [[10, 11, 12],
                [13, 14, 15],
                [16, 17, 18]]])
```

### Shape

```python
a1.shape
a2.shape
a3.shape
```

* Returns dimensions of an array.

### Number of Dimensions

```python
a1.ndim
a2.ndim
a3.ndim
```

* Returns number of dimensions.

### Data Type

```python
a1.dtype
a2.dtype
a3.dtype
```

* Returns data type.

### Size

```python
a1.size
a2.size
a3.size
```

* Returns total number of elements.

---

## NumPy Random Seed

```python
np.random.seed(0)

random_array_4 = np.random.randint(10, size=(5, 3))

np.random.seed(7)

random_array_5 = np.random.random((5, 3))
```

* Produces the same random numbers every run.

---

## Viewing Arrays

### Unique Values

```python
np.unique(random_array_4)
```

### Slicing

```python
a3[:2, :2, :2]
```

### Higher-Dimensional Slicing

```python
a4 = np.random.randint(10, size=(2, 3, 4, 5))

a4[:, :, :, :4]
```

---

## Arithmetic Operations

```python
ones = np.ones(3)

a1 + ones
a1 - ones
a1 * ones
a1 / ones

a2 // a1

a2 ** 2

np.square(a2)

np.add(a1, ones)

a1 % 2

np.exp(a1)

np.log(a1)
```

---

## Aggregation Functions

```python
massive_array = np.random.random(100000)

np.sum(massive_array)

np.mean(a2)

np.max(a2)

np.min(a2)
```

* Used to summarize data.

---

## Variance and Standard Deviation

### Variance

```python
np.var(a2)
```

* Measures spread of data.

### Standard Deviation

```python
np.std(a2)

np.sqrt(np.var(a2))
```

* Measures average distance from mean.

### Example

```python
high_var_array = np.array([1, 100, 200, 300, 4000, 5000])

low_var_array = np.array([2, 4, 6, 8, 10])

np.var(high_var_array)

np.var(low_var_array)

np.std(high_var_array)

np.std(low_var_array)
```

---

## Reshape

```python
a2_reshape = a2.reshape((2, 3, 1))
```

* Changes dimensions without changing data.

---

## Transpose

```python
a2.T

a3.T.shape
```

* Swaps rows and columns.

---

## Dot Product (Matrix Multiplication)

### Rule

* Columns of first matrix must equal rows of second matrix.
* Middle numbers must match.
* Outer numbers become the answer shape.

### Example

```python
np.random.seed(0)

mat1 = np.random.randint(10, size=(5, 3))

mat2 = np.random.randint(10, size=(5, 3))

mat1 * mat2
```

### Matrix Multiplication

```python
mat3 = np.dot(mat1, mat2.T)

# or

mat3 = mat1 @ mat2.T
```

---

## Comparison Operators

```python
a1 > a2

a1 >= a2

a1 > 5

a1 < 5

a1 == a1

a1 == a2
```

* Returns Boolean values (`True` or `False`).

---

## Sorting

### Sort Values

```python
random_array = np.random.randint(10, size=(3, 5))

np.sort(random_array)
```

### Sort Indices

```python
np.argsort(random_array)
```

### Index of Minimum Value

```python
np.argmin(a1)
```

### Index of Maximum Value

```python
np.argmax(a1)
```

### Axis Operations

```python
np.argmax(random_array, axis=0)
```

* Column-wise operation.

```python
np.argmax(random_array, axis=1)
```

* Row-wise operation.

---

## NumPy and Pandas

```python
import pandas as pd

df = pd.DataFrame(a2)
```

* Convert NumPy arrays into Pandas DataFrames.

---

## Topics covered

1. Create Arrays
2. Shape, ndim, dtype, size
3. Random Seed
4. Indexing & Slicing
5. Arithmetic Operations
6. Aggregation Functions
7. Variance & Standard Deviation
8. Reshape
9. Transpose
10. Dot Product
11. Comparison Operators
12. Sorting
13. Axis Operations
14. Convert to Pandas DataFrame

