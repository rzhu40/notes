In numpy, matrix solving is using BLAS

Specify number of cores used for matrix calculation:



```python
import os

os.environ['OMP_NUM_THREADS'] = '1'
os.environ['MKL_NUM_THREADS'] = '1'
```

