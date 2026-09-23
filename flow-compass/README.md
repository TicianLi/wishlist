# 流水罗盘 · Flow Compass（本站是外壳页）

微信流水监控 / 手账风格的个人记账与预算助手。

- **线上本体（完整功能）**：https://flow-compass.app.workbuddy.host/
- **本站**：整屏嵌入了上面那个地址的外壳页，功能与本体完全一致。

## 为什么是外壳页而不是代码副本

应用后端（登录 + 云数据库）对请求来源做**精确 Origin 白名单**校验，只放行它自己
注册的域名和 localhost。以 `ticianli.github.io` 为来源的请求会被直接拒绝：

```
403 {"error":"access_denied",
     "error_description":"the request origin is not allowed for this client"}
```

所以整份源码放到 GitHub Pages 上**能打开、但登不上也读不到数据**。
外壳里应用仍跑在自己的域名下，登录、同步、导入全部正常。

## 已知降级

跨源子框架里浏览器不允许弹文件选择器，账本「一键重导」会退回传统文件选择框
（可用，多一次点击）；「目录自动导入」不可用。其余功能不受影响。
