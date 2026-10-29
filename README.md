# floria-card-media

Floria 工作区预览卡片「本地媒体资源库」——把本地运行的媒体库站点嵌进 Floria 预览面板。

## 功能

- 以 iframe 承载本地媒体库站点，全屏铺满卡片区域
- 通过网关 `/gateway/backend` 做后端地址解析与鉴权（自动带 label 与票证）
- 顶部覆盖层提供刷新 / 退出等操作
- 单文件、零构建

## 数据接口

| 接口 | 用途 |
|---|---|
| `GET /gateway/backend?label=<项目 label>` | 解析该项目配置的本地后端地址 |
| `?token=<网关 token>` | 非浏览器授权场景下的鉴权参数 |

## 使用

把 `index.html` 放到 `<工作区>/.claude/preview/media/index.html`，并在同级 `preview.json` 里注册：

```json
{
  "id": "media",
  "title": "本地媒体资源库",
  "icon": "dshImage",
  "host": "view",
  "path": "media/index.html"
}
```

卡片本身只是外壳，真正的内容由你本地的媒体库服务提供。
