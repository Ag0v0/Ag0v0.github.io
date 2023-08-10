---
title: Nginx 监听WS或WSS协议
date: 2023-08-10 10:04:42
categories:
  - 后端
tags:
  - Nginx
---
## Nginx 监听 WS 或 WSS 协议

要将 NGINX 配置为监听 WS 或 WSS 协议的请求，可以在 NGINX 配置文件中使用 `proxy_pass`指令。以下是一个示例：

```nginx
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://your_websocket_server;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "Upgrade";
    }
}
```

在这个示例中，NGINX 会在端口 80 上监听传入的 HTTP 请求，并使用 `proxy_pass`指令将它们代理到指定的 WebSocket 服务器。`proxy_http_version`和 `proxy_set_header`指令用于处理 WebSocket 协议的升级。

如果想使用安全的 WSS 协议，可以配置 NGINX 在端口 443 上监听，并使用 SSL 证书。以下是一个示例：

```nginx
server {
    listen 443 ssl;
    server_name example.com;

    ssl_certificate /path/to/certificate.crt;
    ssl_certificate_key /path/to/private_key.key;

    location / {
        proxy_pass http://your_websocket_server;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "Upgrade";
    }
}
```

将 `example.com`替换为自己的域名，将 `your_websocket_server`替换为实际 WebSocket 服务器的 URL 或 IP 地址。此外，请确保为 WSS 配置提供正确的 SSL 证书和私钥文件路径。

在进行这些更改后，请记得重新加载或重启 NGINX，以使更改生效。
