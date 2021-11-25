## The third-party dynamic library (cudnn64_7.dll) that Paddle depends on is not configured correctly解决办法

```
如果遇到The third-party dynamic library (cudnn64_7.dll) that Paddle depends on is not configured correctly. (error code is 126)。
```

原因是cudnn与cuda不匹配。 10.1的cuda，配7.6.5的cudnn放进v10.1里面就可以了！