# Boilerplate-mean-variance-standard-deviation-calculator
Create a function named calculate() in mean_var_std.py that uses Numpy to output the mean, variance, standard deviation, max, min, and sum of the rows, columns, and elements in a 3 x 3 matrix.

The input of the function should be a list containing 9 digits. The function should convert the list into a 3 x 3 Numpy array, and then return a dictionary containing the mean, variance, standard deviation, max, min, and sum along both axes and for the flattened matrix.

The returned dictionary should follow this format:

```Python
{
  'mean': [axis1, axis2, flattened],
  'variance': [axis1, axis2, flattened],
  'standard deviation': [axis1, axis2, flattened],
  'max': [axis1, axis2, flattened],
  'min': [axis1, axis2, flattened],
  'sum': [axis1, axis2, flattened]
}
```

If a list containing less than 9 elements is passed into the function, it should raise a ValueError exception with the message: "List must contain nine numbers." The values in the returned dictionary should be lists and not Numpy arrays.

For example, ``` calculate([0,1,2,3,4,5,6,7,8]) ```should return:

```Python
# Import the library 
import numpy as np

# Define s function named calculate
def calculate(list):
    if(len(list) !=9):
      raise ValueError("List must contain nine numbers.")

    lst = np.array(list) 
    print(lst)

    mean_rows = [lst[[0,1,2]].mean(), lst[[3,4,5]].mean(), lst[[6,7,8]].mean()]
    mean_columns = ([lst[[0,3,6]].mean(), lst[[1,4,7]].mean(), lst[[2,5,8]].mean()])

    var_rows = [lst[[0,1,2]].var(), lst[[3,4,5]].var(), lst[[6,7,8]].var()]
    var_columns = ([lst[[0,3,6]].var(), lst[[1,4,7]].var(), lst[[2,5,8]].var()])

    std_rows = ([lst[[0,1,2]].std(), lst[[3,4,5]].std(), lst[[6,7,8]].std()])
    std_columns = ([lst[[0,3,6]].std(), lst[[1,4,7]].std(), lst[[2,5,8]].std()])

    max_rows = ([lst[[0,1,2]].max(), lst[[3,4,5]].max(), lst[[6,7,8]].max()])
    max_columns = ([lst[[0,3,6]].max(), lst[[1,4,7]].max(), lst[[2,5,8]].max()])

    min_rows = ([lst[[0,1,2]].min(), lst[[3,4,5]].min(), lst[[6,7,8]].min()])
    min_columns = ([lst[[0,3,6]].min(), lst[[1,4,7]].min(), lst[[2,5,8]].min()])

    sum_rows = ([lst[[0,1,2]].sum(), lst[[3,4,5]].sum(), lst[[6,7,8]].sum()])
    sum_columns = ([lst[[0,3,6]].sum(), lst[[1,4,7]].sum(), lst[[2,5,8]].sum()])


    return {
      'mean': [mean_columns, mean_rows, lst.mean()],
      'variance': [var_columns, var_rows, lst.var()],
      "standard deviation": [std_columns, std_rows, lst.std()],
      "max": [max_columns, max_rows, lst.max()],
      "min": [min_columns, min_rows, lst.min()],
      "sum": [sum_columns, sum_rows, lst.sum()]

    }
```
<img width="800" alt="Screenshot 2023-08-31 003413" src="https://github.com/Marvykeys/Boilerplate-mean-variance-standard-deviation-calculator/assets/130637591/dcdb4d62-3067-43ed-acfd-db063498798f">
