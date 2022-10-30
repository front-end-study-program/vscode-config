# 调试器配置

vscode 调试器的配置说明

## Chrome 调试配置

Chrome 分为两种模式：

- attach
- launch

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

### userDataDir
