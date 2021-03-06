# 安装 CLI

## 安装 CLI
---
Vapor 命令行接口对通用任务提供了快捷帮助。让我们来安装它。

##### Shell
```
curl -L cli.qutheory.io -o vapor
chmod +x vapor
sudo mv vapor /usr/local/bin
```

> <font color="#56C0E0"> Swift是必需的 </font>
> 
> Vapor CLI 是 Swift 脚本文件，因此你需要先安装 Swift 3，并在对应 PATH 使用它。


## 验证
---
通过运行 help 查询来确保 CLI 已成功安装。你应该看见可用命令的输出。

##### Shell
```
vapor help
```

## 更快
---
你可以编译这个脚本使得它运行的更快。

##### Shell
```
vapor self compile
```

## 更新
---
CLI 可以自我更新。当你遇到任何问题的时候这可能会有帮助的。

##### Shell
```
vapor self update
```