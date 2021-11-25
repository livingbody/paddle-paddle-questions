

# 近期PaddlePaddle遇到的deprecated警告解决方案

原因事python或者numpy升级，一些函数被deprecated了，所以会有这些提示，可以根据需求选择不同解决方案。

## 1.现象

```python
/opt/conda/envs/python35-paddle120-env/lib/python3.7/site-packages/paddle/tensor/creation.py:130: DeprecationWarning: `np.object` is a deprecated alias for the builtin `object`. To silence this warning, use `object` by itself. Doing this will not modify any behavior and is safe. 
Deprecated in NumPy 1.20; for more details and guidance: https://numpy.org/devdocs/release/1.20.0-notes.html#deprecations
  if data.dtype == np.object:
```

## 2.numpy降级解决办法

```bash
pip uninstall numpy

pip install numpy==1.19
```

## 3.代码修改法

![](https://ai.bdstatic.com/file/B84B98E0EE934A1A8FEFC68190730C47)

## 4.warning忽略法

```python
import warnings
warnings.filterwarnings("ignore")
```



