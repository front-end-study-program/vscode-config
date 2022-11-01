# 调试器配置

vscode 调试器的配置说明

## Chrome 调试配置

Chrome 分为两种模式：

- attach - 可以直接连接上一个已经在跑的浏览器
- launch - 启动一个对应 url 的网页，在 attach 到这个端口上

不同点在于 request 配置不同

```json
{
  "configurations": [
    {
      "name": "Launch Chrome",
      "request": "launch",
      "type": "chrome",
      "url": "http://localhost:8080",
      "webRoot": "${workspaceFolder}"
    },
  ]
}
```

```json
{
  "configurations": [
    {
      "name": "Attach to Chrome",
      "port": 9222,
      "request": "attach",
      "type": "chrome",
      "webRoot": "${workspaceFolder}"
    }
  ]
  
}
```

### 命令行启动 Chrome

通过命令行启动调试模式的 Chrome，可以通过 attach 的方式直接连接到调试模式 Chrome。需要退出 Chrome 浏览器。通过以下命令打开。

macos

```bash
/Applications/Google\ Chrome.app/Contents/MacOS/Google\ Chrome --remote-debugging-port=9222
```

windows

```bash
"C:\Program Files (x86)\Google\Chrome\Application\chrome.exe" --remote-debugging-port=9222
```

### userDataDir

是否使用一个临时的目录来保存用户的数据；设置为 true，之前浏览器安装的插件都会没有，需要重新安装。也需要重新登录过网页。默认为 true。设置为 false 可以保持以往的登录记录以及浏览器已安装的插件。也可以设置为一个临时保存的文件目录（同设置为 true 的情况一致）。

### runtimeExecutable

设置运行时调式 JS 的网页，可以设置为 [canary](https://www.google.com/intl/zh-CN/chrome/canary/)。开发者专用的每日构建版 Chrome。需要先安装。

### runtimeArgs

启动 Chrome 的时候，可以指定启动参数。

### sourceMaps

是否开启源码 sourceMap

### sourceMapPathOverrides

指定源码映射目录

### file

除了启动开发服务器然后连上 url 调试之外，也可以直接指定某个文件进行调试。

### pathMapping

把 url 映射到本地文件
