# 文档覆盖

## 一般信息

文档覆盖率仅适用于文件的所有语句，甚至装饰器。

私人功能不是计算的一部分。

The command -- coverageTest可以在CI环境下测试文档覆盖的级别。

screenshot

The command -- coverageMinimumPerFile能够指定每个文件的最小覆盖率。

The command -- coverageTestThresholdFail提供了指定命令是否会因错误而失败或仅警告用户的功能(true: error, false: warn) (默认: true)