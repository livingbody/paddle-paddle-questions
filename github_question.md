##  OpenSSL SSL_read: SSL_ERROR_SYSCALL, errno 10054问题解决办法

### 1.现象

```bash
fatal: unable to access 'https://github.com/livingbody/star_world/': OpenSSL SSL_read: SSL_ERROR_SYSCALL, errno 10054
(base) PS H:\livingbody\star_world>
```

### 2.原因



为了验证我的猜想，我需要查看这个项目的remote到底是什么，使用以下命令

```bash
(base) PS H:\livingbody\star_world\star_world> git config --get remote.origin.url
https://github.com/livingbody/star_world.git
```



### 3.解决办法

```bash
(base) PS H:\livingbody\star_world\star_world> git remote set-url origin git@github.com:livingbody/star_world.git
(base) PS H:\livingbody\star_world\star_world> git config --get remote.origin.url
git@github.com:livingbody/star_world.git
(base) PS H:\livingbody\star_world\star_world> git push
The authenticity of host 'github.com (52.78.231.108)' can't be established.
ECDSA key fingerprint is SHA256:p2QAMXNIC1TJYWeIOttrVc98/R1BUFWu3/LiyKgUfQM.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'github.com,52.78.231.108' (ECDSA) to the list of known hosts.
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 6 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 316 bytes | 158.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:livingbody/star_world.git
   de0b886..2c6504f  main -> main
```



## 4.总结分析



这次问题的解决涉及到两个核心知识。

### ssh keys的正确设置

只有git协议才可以使用ssh-keys文件，从而实现一键git push。https协议只支持账户密码输入。雪上加霜的是，在今年8月13日以后，git不再支持https协议。

###  remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead.