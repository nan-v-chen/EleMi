# EleMi

Elastic net regularized multi-regression (https://link.springer.com/chapter/10.1007/978-3-031-57515-0_13)

EleMi is used to infer soil ecological networks using abundance data.

## 1. Installation
1. **Install required dependencies in Python**
   EleMi depends on [NumPy](https://numpy.org/). Please make sure it is installed before running the code.
   To install NumPy, run the following command:
   ```sh
   pip install numpy
   ```

   Alternatively, if you are using Anaconda:
   ```sh
   conda install numpy
   ```

## 2. Usage

```
from EleMi import EleMi, row_clr, col_normalize


data = row_clr(data)
data = col_normalize(data)

A = EleMi(data, 0.1, 0.01)
A = (A + A.T) / 2
```
