# Application
---
```Application``` 是提供访问大量 Vapor 工具的核心类。它负责注册路由，启动服务，添加中间件等等。


## 初始化
---
正如你所见，创建 ```Application``` 实例唯一需要做的就是导入 Vapor 。

##### Swift
```
import Vapor

let app = Application()

// your magic here

app.start()
```

通常在 ```main.swift``` 中创建 ```Application``` 。


## Environment
---
包含了当前应用的运行环境。通常分为 development、 testing 或者 production。

##### Swift
```
if app.config.environment == .production {
    ...
}
```

可访问指南的 Environment 部分以获取更多关于如何配置和使用 Environment 的内容。


## Working Directory
---
该属性包含应用当前启动时的相对工作路径。默认情况下，是假设从它的根目录启动应用的。

##### Swift
```
app.workDir = "/var/www/my-project/"
```

你可以动态修改工作路径，或者执行的时候覆写默认值。

##### Shell
```
vapor run --workDir="/var/www/my-project"
```


## Resources Directory
---
资源目录是只读属性，它构建了工作目录中的资源目录的路径。

##### Swift
```
print(app.resourcesDir)
```

## Customization
---
application 有一些自定义属性。

大多数 Vapor 插件来自 ```Provider``` ，它们负责具体的配置。想要了解更多请参考 Providers 章节。

##### Swift
```
Application(
    workDir: String? = nil,
    config: Config? = nil,
    localization: Localization? = nil,
    hash: HashDriver? = nil,
    console: ConsoleDriver? = nil,
    server: ServerDriver.Type? = nil,
    router: RouterDriver? = nil,
    session: SessionDriver? = nil,
    providers: [Provider] = [],
    arguments: [String]? = nil
)
```