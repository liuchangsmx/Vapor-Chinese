# 目录结构
---
创建一个应用首先要了解其目录结构。如果你通过 CLI 或者 模版 创建项目，对应的目录结构已经被创建完毕。

如果你正在创建 Vapor 应用，以下内容将指导你如何进行设置。

## 最小化目录结构
---
我们建议将 Swift 代码放在 ```App/``` 目录中，你可以创建 ```App/``` 子目录来放置模型或者其它的文件。

如下目录结构与 Swift package manager 规则最匹配。

##### Text
```
.
├── App
│   └── main.swift
├── Public
└── Package.swift
```

``` Public ``` 目录应该存放所有可公开访问的文件。当路由中找不到 URL 请求的时候将每次自动检查该目录。


## Models
---
```Models ``` 目录建议存放数据库和其它模型，它遵循 MVC 模式。

##### Text
```
.
├── App
.   └── Models
.       └── User.swift
```

## Controllers
---
```Controllers``` 目录建议存放各类路由控制器，它遵循 MVC 模式。

##### Text
```
.
├── App
.   └── Controllers
.       └── UserController.swift
```

## Views
---
创建视图时 ```View()``` 类将查询 ```Resources``` 中的 ```Views``` 目录。

##### Text
```
.
├── App
└── Resources
    └── Views
         └── user.html
```

如下代码将加载 ```user.html``` 文件。

##### Swift
```
View(path: "user.html")
```

## Config
---
Vapor 拥有一个复杂的配置系统，它包含了配置重要性的层级。

##### Text
```
.
├── App
└── Config
  └── app.json       // defaults
    └── development
         └── app.json  // overrides defaults in dev env
    └── production
         └── app.json  // overrides defaults in prod env
    └── secrets
         └── app.json  // overrides defaults and env config
```

```.json``` 文件结构与 ```Config``` 目录类似。根据 ```.json``` 文件所在目录，配置将会被应用。

Application 章节中将讲述如何修改环境变量（```the --env=``` flag）。