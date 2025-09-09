一定要在MINGW64环境下运行一次 “go run ./src/main.go” 命令，确保服务正常运行

起一个cmd窗口，到当前目录下，执行
```
C:\msys64\msys2_shell.cmd -mingw64 -here

go run ./src/main.go

go build
```


我的配置文件，其他配置，按自己账号配置ASR TTS LLM

```

# 服务器基础配置(Basic server configuration)
server:
  # 服务器监听地址和端口(Server listening address and port)
  ip: 0.0.0.0
  port: 8000
  token: "test-token" # 服务器访问令牌
  # 认证配置
  auth:
    # 是否启用认证
    enabled: false
    # 认证存储配置
    store:
      type: memory # memory/file/redis
      expiry: 24 # 过期时间(小时)
    # 允许的设备ID列表
    allowed_devices: []
    # 有效的token列表
    tokens: []

# 传输层配置
transport:
  # WebSocket传输层
  websocket:
    enabled: true
    ip: "0.0.0.0"
    port: 8000

# Web界面配置
web:
  # 是否启用Web界面
  enabled: true
  # Web服务监听端口
  port: 8080
  # 由ota下发的WebSocket地址
  websocket: ws://127.0.0.1:8000
  vision: http://127.0.0.1:8080/api/vision
  activate_text: "Amine AI Chat" # 发送激活码时携带的文本

```

