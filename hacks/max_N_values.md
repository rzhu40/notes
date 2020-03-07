Find N max values for each row in numpy 2-d array (or other way around for column):

```python
# for row
np.sort(array)[:,-N:]
# for column
np.sort(array, axis=0)[-N:,:]
```

