# 技巧和窍门

## 设计文档

```js
compodoc -p src/tsconfig.json -y your_theme_styles/
```

在你的文件夹里面，你需要至少提供一个`style.css`文件，下面这5个导入文件。

```js
@import "./reset.css";
@import "./bootstrap.min.css";
@import "./bootstrap-card.css";
@import "./font-awesome.min.css";
@import "./compodoc.css";
@import "./prism.css";
@import "./tablesort.css";
```

Compodoc使用`bootstrap 3.3.7`。,您可以轻松自定义Compodoc。

`bootswatch.com`可以是一个很好的起点。
如果您想覆盖默认主题，只需提供一个`bootstrap.min.css`文件，它将覆盖默认主题。

```js
└── your_theme_styles/
    ├── style.css // the main css file with default imports
    └── bootstrap.min.css // your bootstrap theme
```

## 每个组件，模块，指令等的文档

在`xxx.component.ts`文件中，`JSDoc`注释之间的注释描述可能会稍微短一些。

Compodoc在每个组件的根文件夹中搜索默认的`xxx.component.md`文件，并将其添加到组件页面中的选项卡中。
类，模块等是一样的

```js
└── my-component/
    ├── my.component.ts
    ├── my.component.spec.ts
    ├── my.component.scss|css
    ├── my.component.html
    └── my.component.md
```

## 额外记录

Compodoc支持添加外部MD文件以扩展应用程序的代码注释和主要的README文件。

创建一个包含MD文件的文件夹并使用`--includes`标志来扩展文档。
你的文件夹应该包含一个说明结构和文件的`summary.json`文件：

summary.json

```json
[
    {
        "title": "A TITLE",
        "file": "a-file.md"
    },
    {
        "title": "A TITLE",
        "file": "a-file.md",
        "children": [
            {
                "title": "A TITLE",
                "file": "a-sub-folder/a-file.md"
            }
        ]
    }
]
```

链接支持像普通的MD链接。

## MD文件中的语法高亮显示

Compodoc使用Marked进行markdown分析并编译为html。
已添加prismjs.js以支持语法高亮显示。

只需在标记中使用正确的代码块并使用正确的语言: Github help

综合语言是: json, bash, javascript, markdown, html, scss, typescript

## 排除文件

为了从文档中排除文件，只需使用`tsconfig.json`文件的`exclude`属性即可。

您可以排除名称为`app/myfile.ts`的特定文件或者使用`glob`模式`**/*.spec.ts`。

## 包括文件

要从文档中包含文件，只需使用tsconfig.json文件的include属性即可。

您可以包含名称为`app/myfile.ts`的具体文件，或者使用`glob`模式`**/*.ts`