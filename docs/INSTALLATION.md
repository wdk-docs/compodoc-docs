# 安装

## Node.js 版本

Compodoc仅通过LTS版本进行测试：v8.9.1，v6.12.0和v4.8.6

## Angular-CLI

Compodoc支持最新的Angular-CLI版本：1.5

只需在新的或现有的项目中运行Compodoc。

## 全局安装

从npm安装：

```js
npm install -g @compodoc/compodoc
```

如果您在Windows上使用PowerShell，请添加引号：

```js
npm install -g "@compodoc/compodoc"
```

## 本地安装

```js
npm install --save-dev @compodoc/compodoc
```

## 运行

在你的package.json中为它定义一个脚本任务：

```js
"scripts": {
  "compodoc": "./node_modules/.bin/compodoc -p src/tsconfig.app.json"
}
```

并像正常的npm脚本那样运行它：

```js
npm run compodoc
```

请参阅用法了解更多详情。

## tsconfig文件在代码库中的位置

Compodoc从带有-p选项的tsconfig文件的文件夹级别开始。

Angular CLI项目的示例：

```js
.
├── src
│ ├── app
│ │ ├── app.component.ts
│ │ └── app.module.ts
│ ├── main.ts
│ ├── ...
│ └── tsconfig.app.json
└── tsconfig.json
compodoc -p src/tsconfig.app.json
```