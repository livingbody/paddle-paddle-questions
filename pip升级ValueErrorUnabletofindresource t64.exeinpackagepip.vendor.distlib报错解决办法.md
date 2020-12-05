# pip升级报错解决办法
>pip升级频率很高，不升级经常会遇到这样哪样的异常。有一种异常，我相信你一定遇到，话不多说，上错误信息。

## 1.错误现象
```bash
(paddle2) D:\github\PGL>python.exe -m pip install --upgrade pip
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Collecting pip
  Using cached https://pypi.tuna.tsinghua.edu.cn/packages/cb/28/91f26bd088ce8e22169032100d4260614fc3da435025ff389ef1d396a433/pip-20.2.4-py2.py3-none-any.whl (1.5 MB)
Installing collected packages: pip
  Attempting uninstall: pip
    Found existing installation: pip 20.2.3
    Uninstalling pip-20.2.3:
      Successfully uninstalled pip-20.2.3
  Rolling back uninstall of pip
  Moving to c:\users\administrator\appdata\roaming\python\python37\scripts\
   from c:\users\administrator\appdata\roaming\python\python37\~cripts
  Moving to c:\users\administrator\appdata\roaming\python\python37\site-packages\pip-20.2.3.dist-info\
   from c:\users\administrator\appdata\roaming\python\python37\site-packages\~ip-20.2.3.dist-info
  Moving to c:\users\administrator\appdata\roaming\python\python37\site-packages\pip\
   from c:\users\administrator\appdata\roaming\python\python37\site-packages\~ip
ERROR: Exception:
Traceback (most recent call last):
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\cli\base_command.py", line 228, in _main
    status = self.run(options, args)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\cli\req_command.py", line 182, in wrapper
    return func(self, options, args)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\commands\install.py", line 406, in run
    pycompile=options.compile,
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\req\__init__.py", line 90, in install_given_reqs
    pycompile=pycompile,
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\req\req_install.py", line 822, in install
    requested=self.user_supplied,
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\operations\install\wheel.py", line 860, in install_wheel
    requested=requested,
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\operations\install\wheel.py", line 762, in _install_wheel
    generated_console_scripts = maker.make_multiple(scripts_to_generate)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_vendor\distlib\scripts.py", line 418, in make_multiple
    filenames.extend(self.make(specification, options))
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_internal\operations\install\wheel.py", line 498, in make
    return super(PipScriptMaker, self).make(specification, options)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_vendor\distlib\scripts.py", line 407, in make
    self._make_script(entry, filenames, options=options)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_vendor\distlib\scripts.py", line 307, in _make_script
    self._write_script(scriptnames, shebang, script, filenames, ext)
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_vendor\distlib\scripts.py", line 242, in _write_script
    launcher = self._get_launcher('t')
  File "C:\Users\Administrator\AppData\Roaming\Python\Python37\site-packages\pip\_vendor\distlib\scripts.py", line 386, in _get_launcher
    raise ValueError(msg)
ValueError: Unable to find resource t64.exe in package pip._vendor.distlib
WARNING: You are using pip version 20.2.3; however, version 20.2.4 is available.
You should consider upgrading via the 'd:\Miniconda3\envs\paddle2\python.exe -m pip install --upgrade pip' command.

```
## 2.解决办法
>如上图所示，你用pip install --upgrade pip 也无济于事。那么怎么处理呢？
### 2.1卸载 setuptools

```bash
python -m pip uninstall pip setuptools
```

```bash
(paddle2) D:\github\PGL> python -m pip uninstall pip setuptools
Found existing installation: pip 20.2.3
Uninstalling pip-20.2.3:
  Would remove:
    c:\users\administrator\appdata\roaming\python\python37\scripts\pip.exe
    c:\users\administrator\appdata\roaming\python\python37\scripts\pip3.7.exe
    c:\users\administrator\appdata\roaming\python\python37\scripts\pip3.exe
    c:\users\administrator\appdata\roaming\python\python37\site-packages\pip-20.2.3.dist-info\*
    c:\users\administrator\appdata\roaming\python\python37\site-packages\pip\*
Proceed (y/n)? y
  Successfully uninstalled pip-20.2.3
Found existing installation: setuptools 50.3.0.post20201006
Uninstalling setuptools-50.3.0.post20201006:
  Would remove:
    d:\miniconda3\envs\paddle2\lib\site-packages\_distutils_hack
    d:\miniconda3\envs\paddle2\lib\site-packages\easy_install.py
    d:\miniconda3\envs\paddle2\lib\site-packages\pkg_resources
    d:\miniconda3\envs\paddle2\lib\site-packages\setuptools
    d:\miniconda3\envs\paddle2\lib\site-packages\setuptools-50.3.0.post20201006-py3.7.egg-info
    d:\miniconda3\envs\paddle2\scripts\easy_install-script.py
    d:\miniconda3\envs\paddle2\scripts\easy_install.exe
Proceed (y/n)? y
  Successfully uninstalled setuptools-50.3.0.post20201006
```

### 2.2 升级pip

```bash
(paddle2) D:\github\PGL> pip3 install --upgrade pip
Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Requirement already up-to-date: pip in d:\miniconda3\envs\paddle2\lib\site-packages (20.2.4)
```
### 2.3 重新安装 setuptools
>可以不需要这一步，不过为了以后万一用到准备。
```bash
pip install --upgrade setuptools 
```
