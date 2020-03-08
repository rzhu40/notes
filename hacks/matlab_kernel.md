https://github.com/Calysto/matlab_kernel

install matlab engine from matlab root:

```bash
cd "matlabroot/extern/engines/python"
# for Mac it will be:
cd /Applications/MATLAB_R2019b.app/extern/engines/python
python setup.py install
```

install matlab_kernel: 

```bash
pip install matlab_kernel
```

-----

plot in matlab style

```matlab
%plot native
```

Back to inline

```matlab
%plot inline
```

------

Function (in notebook)

```matlab
%%file func_name.m
function output = func_name(input)
end
```

