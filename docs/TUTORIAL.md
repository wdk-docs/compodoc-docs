# 教程

这是一个简单的教程，解释如何使用Compodoc轻松记录您的Angular应用程序。

我们将从一个空白的Angular CLI项目开始。

## 要求

- Angular CLI
- Node.js
- code editor or IDE

## 1. 运行Angular CLI

```js
ng new compodoc-tutorial
```

## 2. 用...安装

```js
npm i --save-dev @compodoc/compodoc
```

在package.json文件中添加npm脚本以生成文档 : 一代为一代，另一代为结合他们:

```js
...

    "ng": "ng",
    "doc:build": "compodoc -p src/tsconfig.app.json",
    "doc:serve": "compodoc -s",
    "doc:buildandserve": "compodoc -p src/tsconfig.app.json -s",
    "start": "ng serve",

...
```

## 3. 运行compodo

```js
npm run doc:buildandserve
```

您应该在终端中看到这些日志

![first-run](https://compodoc.github.io/website/assets/img/tutorial/first-run-terminal.png)

这在你的浏览器打开 http://localhost:8080

![first-run](https://compodoc.github.io/website/assets/img/tutorial/first-run-browser.png)

## 下一步即将推出...