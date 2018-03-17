# 路由

## 一般通知

按照样式指南，提供一个具有唯一名称的“路线”类型的常量 :

```js
const APP_ROUTES: Routes = [
    { path: 'about', component: AboutComponent },
    { path: '', component: HomeComponent}
];

...

RouterModule.forRoot(APP_ROUTES)
```

screenshot