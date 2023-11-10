# EleMi

Elastic net regularized Multi-regression

The package is used to infer soil ecological networks using abundance data.

# Usage

`from EleMi import EleMi, row_clr, col_normalize

A = EleMi(data, 0.1, 0.01)

A = (A + A.T) / 2`
