# 修复ModuleNotFoundError: No module named 'pip’这个错误

> 升级pip，自动卸载，安装未成功会提示：
> **ModuleNotFoundError: No module named ‘pip’**
> 别慌，有解决办法！

**一般是升级pip失败造成的。 可通过下面命令修复：**

```python
 python -m ensurepip python -m pip install --upgrade pip
```

