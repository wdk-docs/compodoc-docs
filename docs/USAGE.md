# 用法

```bash
compodoc <src> [options]
```

## 选项

| 选项 | 描述 |
| - | - |
|-h, --help | 输出使用信息 |
|-V, --version | 输出版本号
|-p, --tsconfig [config] | 一个tsconfig.json文件
|-d, --output [folder] | 在哪里存储生成的文档
|-y, --extTheme [file] | 外部造型主题
|-n, --name [name] | 文档的标题
|-a, --assetsFolder [folder] | 外部资产文件夹复制到生成的文档文件夹中
|-o, --open | 打开生成的文档
|-t, --silent | 在静默模式下，日志消息不会记录在控制台中
|-s, --serve | 服务生成的文档(默认 http://localhost:8080/)
|-r, --port [port] | 更改默认的服务端口
|-w, --watch | 在服务之后观看源文件并强制重建文档
|-e, --exportFormat [format] | 以指定格式导出 (json, html (默认))
|--theme [theme] | 选择一个可用主题，默认为'gitbook' (laravel, original, material, postmark, readthedocs, stripe, vagrant)
|--hideGenerator | 不要在页面底部打印Compodoc徽标
|--toggleMenuItems | 默认关闭菜单中的项目（默认['all']）值 : ['all'] 或其中之一['modules','components','directives','classes','injectables','interfaces','pipes','additionalPages'])
|--includes [path] | 包含外部降价文件的路径
|--includesName [name] | 外部md文件的项目菜单的名称 ( 默认 "Additional documentation")
|--coverageTest | 用阈值测试文档覆盖命令（默认 70)
|--coverageMinimumPerFile [minimum] | 至少测试每个文件的文档覆盖率命令 ( 默认 0)
|--coverageTestThresholdFail [boolean] | 文档覆盖率的测试命令（全局文件或每个文件）将失败并出现错误，或者只是警告用户 (true: error, false: warn) ( 默认: true)
|--disableSourceCode | 不要添加源代码标签和链接到源代码
|--disableGraph | 禁用依赖关系图的呈现
|--disableCoverage | 不要添加文档覆盖率报告
|--disablePrivate | 不要在生成的文档中显示私密文件
|--disableProtected | 不要在生成的文档中显示保护
|--disableInternal | 不要在生成的文档中显示@internal
|--disableLifeCycleHooks | 不要在生成的文档中显示Angular生命周期钩子
|--disableRoutesGraph | 不要添加路线图
|--customFavicon [path] | 使用自定义图标
|--gaID [id] Google | Google Analytics跟踪ID
|--gaSite [site] | Google Analytics网站名称（默认自动（默认：auto）

## 选项，报价和Windows使用情况

请记住，使用带有多个单词的选项需要在句子周围引用引号。

```bash
compodoc -p src/tsconfig.json -n 'My app documentation'
```

使用npm脚本，该命令托管在package.json文件中。
不要忘记用Windows系统的双引号进行转义。

```json
{
   ...
   "doc": "./node_modules/.bin/compodoc -p src/tsconfig.app.json -n \"My app documentation\""
   ...
}
```

## 渲染文档

文档在默认输出文件夹中生成，然后在该文件夹中运行HTTP服务器。

```bash
compodoc -p src/tsconfig.json
```

## 在提供源文件夹的同时呈现文档

```bash
compodoc src -p src/tsconfig.json
```

## 用compodoc生成文档

文档是在默认输出文件夹或特定文件夹中生成的，
本地HTTP服务器启动于http://localhost:8080

```bash
compodoc -s
# 要么
compodoc -s -d ./doc
```

## 渲染文档，并将其与compodoc一起提供

文档在默认输出文件夹中生成，
和一个本地HTTP服务器可在 http://localhost:8080

```bash
compodoc -p src/tsconfig.json -s
```