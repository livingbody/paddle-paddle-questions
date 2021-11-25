# Out of memory error on GPU  解决办法

## 1.现象

经常会在aistudio或者本地遇到类似的提示，原因是GPU显存爆了。

```bash
Out of memory error on GPU 0. Cannot allocate 9.492432MB memory on GPU 0, 4.000000GB memory has been allocated and available memory is only 0.000000B.
```

## 2.处理方法

缩小batch size即可，可以从小往大试，按比例计算。

## 3.云端方法

有时候aistudio的notebook停止运行显存不释放，需要 **重启notebook** 或者terminal下运行 **killall -9 python** 