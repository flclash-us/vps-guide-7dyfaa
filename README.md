# Subconverter 订阅转换完全指南

Subconverter 可以将订阅链接在不同格式之间转换，是管理多客户端的利器。

## 自建服务（推荐）

```bash
# 安装
pip install subconverter

# 运行
./subconverter -s 8080

# 或 Docker
docker run -d --name subconverter -p 8080:8080 \
  -v $(pwd)/profiles:/etc/subconverter/profiles \
  --restart always tindy2013/subconverter
```

## API 使用

### 基础转换

```
GET http://your-server:8080/sub?target=clash&url=YOUR_SUBSCRIPTION_URL
```

### 参数说明

| 参数 | 说明 | 示例 |
|------|------|------|
| target | 目标格式 | clash/surge/v2ray |
| url | 原始订阅链接 | (URL编码) |
| remove-emoji | 移除节点名表情 | true |
| sort | 排序节点 | true |
| filter | 筛选节点 | (正则) |

### 完整示例

```
http://your-server:8080/sub?target=clash&url=https://xxx.com/sub&remove-emoji=true&sort=true
```

## 常用订阅转换服务

| 服务 | 地址 | 说明 |
|------|------|------|
| sub.v1.mk | 在线 | 免费使用 |
| 自建 | 你的VPS | 隐私安全 |

## 常见问题

**转换后节点少？** 检查订阅链接是否有效。

**emoji 不去除？** 确保 `remove-emoji=true` 参数。

---

推荐工具：

- [Clash for Windows](https://clashforwindows.site/)
- [ClashMI](https://clashmi.site/)
- [FlClash](https://flclash.us/)
