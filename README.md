# EleMi

Elastic net regularized multi-regression (https://link.springer.com/chapter/10.1007/978-3-031-57515-0_13)

EleMi is used to infer soil ecological networks using abundance data.

## 1. Installation

### 1) Install Python
EleMi requires Python to run. If you don't have Python installed, you can install it in one of the following ways:

**Option a: Install from python.org**
1. Download Python (we recommend version 3.8.5) from the official website: https://www.python.org/downloads/.
2. During installation, make sure to check the box that says "Add Python to PATH".
3. After installation, you can verify that Python is installed by running:
   ```sh
   python --version
   ```
   or
   ```sh
   python3 --version
   ```

**Option b: Install via Anaconda (Recommended for beginners)**
1. Download and install Anaconda from: https://www.anaconda.com/download/success.
2. After installation, open a terminal (or Anaconda Prompt) and create a new environment with Python:
   ```sh
   conda create -n py385 python=3.8.5
   conda activate py385
   ```

### 2) Install required dependencies
   EleMi depends on [NumPy](https://numpy.org/). Please make sure it is installed before running the code.
   To install NumPy, run the following command:
   ```sh
   pip install numpy pandas
   ```

   Alternatively, if you are using Anaconda:
   ```sh
   conda install numpy pandas
   ```

## 2. Usage
EleMi takes as input an abundance matrix shaped like n × p where n is the number of samples and p is the number of taxa.
```python
from EleMi import EleMi, row_clr, col_normalize
import pandas as pd

data = pd.read_csv("example_data/otu.csv", index_col=0)
data = data.astype(float).values

data = row_clr(data)
data = col_normalize(data)

A = EleMi(data, 0.1, 0.01)
A = (A + A.T) / 2
```
