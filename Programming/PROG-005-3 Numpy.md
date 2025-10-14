- As known as Numerical Python library first appeared in 2006 and is preferred Python array implementation. It offers a high-performance, richly functional n-dimensional array called ndarray.
- One of the many open-source libraries that the Anaconda Python distribution installs. Operations on arrays are up to 2 orders of magnitude faster than on lists.
- Big-data world in which applications may do massive amounts of processing on vast amounts of array-based data, this performance advantage can be critical. Many popular data science libraries such as Pandas, SciPy and Keras are built on depend on NumPy.
# Creating arrays from Existing Data
```python
import numpy as np
numbers = np.array([2, 3, 5, 7, 11])

# Type of onject that function array returns and display its contents
type(numbers)
# Output: numpy.ndarray

numbers
# Output: array([2, 3, 5, 7, 11])

# Multidimensional Arguments
np.array([1, 2, 3], [4, 5 ,6])
# Output ([[1,2,3],
#			4, 5, 6]])
```

# Array Attributes