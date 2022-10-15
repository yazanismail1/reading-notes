# What is Jupyter Lab?

JupyterLab is a next-generation web-based user interface for Project Jupyter. JupyterLab enables you to work with documents and activities such as Jupyter notebooks, text editors, terminals, and custom components in a flexible, integrated, and extensible manner.

---
---

# NumPy Tutorial: Data Analysis with Python

NumPy is a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

**Why the use of Numpy?**

By using NumPy, you can speed up your workflow, and interface with other packages in the Python ecosystem, like scikit-learn.

**How to use Numpy?**

**Import Numpy **
```
import numpy as np
````

**Numpy Arrays**

Numpy has many built-in functions and capabilities. We won't cover them all but instead we will focus on some of the most important aspects of Numpy: vectors,arrays,matrices, and number generation.

We can create an array by directly converting a list or list of lists:

```
my_list = [1, 2, 3]
>> [1, 2, 3]

np.array(my_list)
>> array([1, 2, 3])

my_matrix = [[1,2,3],[4,5,6],[7,8,9]]
>> [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

np.array(my_matrix)
>> array([[1, 2, 3],
          [4, 5, 6],
          [7, 8, 9]])

```

**Built-in Methods**

arange; Return evenly spaced values within a given interval.

```
np.arange(0,10)
>> array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])

np.arange(0,11,2)
>> array([ 0,  2,  4,  6,  8, 10])
```

**Zeros and ones**

Generate arrays of zeros or ones

```
np.zeros(3)
>> array([ 0.,  0.,  0.])

np.zeros((5,5))
>> array([[ 0.,  0.,  0.,  0.,  0.],
          [ 0.,  0.,  0.,  0.,  0.],
          [ 0.,  0.,  0.,  0.,  0.],
          [ 0.,  0.,  0.,  0.,  0.],
          [ 0.,  0.,  0.,  0.,  0.]])

np.ones(3)
>> array([ 1.,  1.,  1.])

np.ones((3,3))
>> array([[ 1.,  1.,  1.],
          [ 1.,  1.,  1.],
          [ 1.,  1.,  1.]])
```

**Linespace**

Return evenly spaced numbers over a specified interval.

```
np.linspace(0,10,3)
>> array([  0.,   5.,  10.])

np.linspace(0,10,50)
>> array([  0.        ,   0.20408163,   0.40816327,   0.6122449 ,
            0.81632653,   1.02040816,   1.2244898 ,   1.42857143,
            1.63265306,   1.83673469,   2.04081633,   2.24489796,
            2.44897959,   2.65306122,   2.85714286,   3.06122449,
            3.26530612,   3.46938776,   3.67346939,   3.87755102,
            4.08163265,   4.28571429,   4.48979592,   4.69387755,
            4.89795918,   5.10204082,   5.30612245,   5.51020408,
            5.71428571,   5.91836735,   6.12244898,   6.32653061,
            6.53061224,   6.73469388,   6.93877551,   7.14285714,
            7.34693878,   7.55102041,   7.75510204,   7.95918367,
            8.16326531,   8.36734694,   8.57142857,   8.7755102 ,
            8.97959184,   9.18367347,   9.3877551 ,   9.59183673,
            9.79591837,  10.        ])
```

**Eye**

Creates an identity matrix

```
np.eye(4)
>> array([[ 1.,  0.,  0.,  0.],
          [ 0.,  1.,  0.,  0.],
          [ 0.,  0.,  1.,  0.],
          [ 0.,  0.,  0.,  1.]])
```

**Random**

Numpy also has lots of ways to create random number arrays:

**rand**

Create an array of the given shape and populate it with
random samples from a uniform distribution
over ``[0, 1)``.

```
np.random.rand(2)
>> array([ 0.11570539,  0.35279769])

np.random.rand(5,5)
>> array([[ 0.66660768,  0.87589888,  0.12421056,  0.65074126,  0.60260888],
          [ 0.70027668,  0.85572434,  0.8464595 ,  0.2735416 ,  0.10955384],
          [ 0.0670566 ,  0.83267738,  0.9082729 ,  0.58249129,  0.12305748],
          [ 0.27948423,  0.66422017,  0.95639833,  0.34238788,  0.9578872 ],
          [ 0.72155386,  0.3035422 ,  0.85249683,  0.30414307,  0.79718816]])
```

**randn**

Return a sample (or samples) from the "standard normal" distribution. Unlike rand which is uniform:

```
np.random.randn(2)
>> array([-0.27954018,  0.90078368])

np.random.randn(5,5)
>> array([[ 0.70154515,  0.22441999,  1.33563186,  0.82872577, -0.28247509],
          [ 0.64489788,  0.61815094, -0.81693168, -0.30102424, -0.29030574],
          [ 0.8695976 ,  0.413755  ,  2.20047208,  0.17955692, -0.82159344],
          [ 0.59264235,  1.29869894, -1.18870241,  0.11590888, -0.09181687],
          [-0.96924265, -1.62888685, -2.05787102, -0.29705576,  0.68915542]])
```

**randint**

eturn random integers from `low` (inclusive) to `high` (exclusive).

```
np.random.randint(1,100)
>> 44

np.random.randint(1,100,10)
>> array([13, 64, 27, 63, 46, 68, 92, 10, 58, 24])
```

**reshape**

Returns an array containing the same data with a new shape.

```
arr = np.random.randint(0,50,10)
>> array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24])

arr.reshape(5,5)
>> array([[ 0,  1,  2,  3,  4],
          [ 5,  6,  7,  8,  9],
          [10, 11, 12, 13, 14],
          [15, 16, 17, 18, 19],
          [20, 21, 22, 23, 24]])
```

**min, max, argmin, argmax**

These are useful methods for finding max or min values. Or to find their index locations using argmin or argmax

```
ranarr
>> array([10, 12, 41, 17, 49,  2, 46,  3, 19, 39])

ranarr.max()
>> 49

ranarr.argmax()
>> 4

ranarr.min()
>> 2

ranarr.argmin()
>> 5
```

**dtype**

You can also grab the data type of the object in the array:

```
arr.dtype
>> dtype('int64')
```

**NumPy Indexing and Selection**

```
arr = np.arange(0,11)
>> array([ 0,  1,  2,  3,  4,  5,  6,  7,  8,  9, 10])

arr[8]
>> 8

arr[1:5]
>> array([1, 2, 3, 4])
```

**Broadcasting**

Numpy arrays differ from a normal Python list because of their ability to broadcast, note that it change the original array.

```
arr[0:5]=100
>> array([100, 100, 100, 100, 100,   5,   6,   7,   8,   9,  10])

```

**copying**

```
arr_copy = arr.copy()
```
**Indexing a 2D array (matrices)**

The general format is **arr_2d[row][col]** or **arr_2d[row,col]**. I recommend usually using the comma notation for clarity.

```
arr_2d = np.array(([5,10,15],[20,25,30],[35,40,45]))
>> array([[ 5, 10, 15],
          [20, 25, 30],
          [35, 40, 45]])

arr_2d[1]
>> array([20, 25, 30])

arr_2d[1][0]
>> 20

arr_2d[1,0]
>> 20

arr_2d[:2,1:]
>> array([[10, 15],
          [25, 30]])
```

**Selection**

```
arr = np.arange(1,11)
>> array([ 1,  2,  3,  4,  5,  6,  7,  8,  9, 10])

arr > 4
>> array([False, False, False, False,  True,  True,  True,  True,  True,  True], dtype=bool)

bool_arr = arr>4
arr[bool_arr]
>> array([ 5,  6,  7,  8,  9, 10])

arr[arr>2]
>> array([ 3,  4,  5,  6,  7,  8,  9, 10])
```

**Operations**

```
arr = np.arange(0,10)

arr + arr
>> array([ 0,  2,  4,  6,  8, 10, 12, 14, 16, 18])

arr * arr
>> array([ 0,  1,  4,  9, 16, 25, 36, 49, 64, 81])

arr - arr
>> array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0])

arr/arr

# Warning on division by zero, but not an error!
# Just replaced with nan

>> /Users/marci/anaconda/lib/python3.5/site-packages/ipykernel/__main__.py:1: RuntimeWarning: invalid value encountered in true_divide
  if __name__ == '__main__':
array([ nan,   1.,   1.,   1.,   1.,   1.,   1.,   1.,   1.,   1.])

1/arr
# Also warning, but not an error instead infinity

>> /Users/marci/anaconda/lib/python3.5/site-packages/ipykernel/__main__.py:1: RuntimeWarning: divide by zero encountered in true_divide
  if __name__ == '__main__':
array([        inf,  1.        ,  0.5       ,  0.33333333,  0.25      ,
        0.2       ,  0.16666667,  0.14285714,  0.125     ,  0.11111111])

arr**3
>> array([  0,   1,   8,  27,  64, 125, 216, 343, 512, 729])

np.sqrt(arr)
>> array([ 0.        ,  1.        ,  1.41421356,  1.73205081,  2.        ,  2.23606798,  2.44948974,  2.64575131,  2.82842712,  3.        ])

np.exp(arr)
>> array([  1.00000000e+00,   2.71828183e+00,   7.38905610e+00,
         2.00855369e+01,   5.45981500e+01,   1.48413159e+02,
         4.03428793e+02,   1.09663316e+03,   2.98095799e+03,
         8.10308393e+03])

np.sin(arr)
>> array([ 0.        ,  0.84147098,  0.90929743,  0.14112001, -0.7568025 ,
       -0.95892427, -0.2794155 ,  0.6569866 ,  0.98935825,  0.41211849])

np.log(arr)
>> /Users/marci/anaconda/lib/python3.5/site-packages/ipykernel/__main__.py:1: RuntimeWarning: divide by zero encountered in log
  if __name__ == '__main__':
array([       -inf,  0.        ,  0.69314718,  1.09861229,  1.38629436,
        1.60943791,  1.79175947,  1.94591015,  2.07944154,  2.19722458])
```

---
---

## Things I want to know more about

- Data Science

---
---

## References

[1] Project Jupyter, Feb, 2018, _JupyterLab_, jupyterlab.com, accessed 15 October 2022, <https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html>

[2] Vik Paruchuri, Oct 18, 2016, _NumPy Tutorial: Data Analysis with Python_, dataquest.io, accessed 15 October 2022, <https://www.dataquest.io/blog/numpy-tutorial-python/>
