## 问题描述

经常遇到小伙伴下载的aistudio数据，后来上传aistudio，出现：

```python
/home/aistudio/home/aistudio/....
```

究其原因就是下载数据的时候自动打包的zip路径就是从 `/home/aistudio`写起的，解压时肯定默认就是多了这个路径了。

## 解决办法

下载前自己手动打压缩包，或者解压后mv数据文件。
