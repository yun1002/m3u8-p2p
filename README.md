# 我爱云解析 (P2P 在线视频播放器)

一个基于 PHP 的在线视频播放聚合页，通过 URL 参数方式在多种主流播放器中切换播放，支持 **M3U8 / HLS 流媒体**与 **P2P 加速**。只需一条链接即可在浏览器中全屏、便捷地观看视频。

> 免责声明：本项目仅用于技术学习与演示。请确保你所播放的内容拥有合法授权，遵守当地法律法规及版权规定。

## ✨ 功能特性

- 🎬 **多播放器支持**：内置 ArtPlayer、DPlayer、CKplayer，支持一键切换
- 📡 **M3U8 / HLS 流播放**：集成 HLS 播放内核，流畅播放 `.m3u8` 片源
- ⚡ **P2P 加速**：ArtPlayer、DPlayer、CKplayer 均内置 P2P 模式，多端协同加载，提升缓冲体验
- 📲 **移动端适配**：兼容 H5、微信/UC/苹果浏览器全屏模式，并按设备自动选择合适的播放器
- 🔗 **URL 直链接入**：通过 `?url=` 参数直接传入视频地址，简单易用
- 🖥️ **桌面与移动双端**：响应式布局，PC 与手机均可流畅使用

## 📂 目录结构

```
本地m3u8-p2p加速/
├── index.html          # 首页聚合入口（纯前端，默认调用 DP-P2P）
├── index.php           # 首页聚合入口（PHP 版，默认调用 DP-P2P）
├── index1.html         # 辅助播放页：按设备自动调用 ArtPlayer（纯前端）
├── index1.php          # 辅助播放页：按设备自动调用 ArtPlayer（PHP 版）
├── pucms.css           # 页面样式
├── pucms.js            # 页面脚本
├── art/                # ArtPlayer 播放器（P2P 版）
├── ck/                 # CKplayer 播放器
├── ck2/                # CKplayer P2P 版
├── dp/                 # DPlayer 播放器
├── dp2/                # DPlayer P2P 版
└── LICENSE             # MIT 许可证
```

| 入口 | 说明 |
| --- | --- |
| `/art/?url=视频地址` | ArtPlayer + P2P 播放 |
| `/dp/?url=视频地址` | DPlayer 播放 |
| `/dp2/?url=视频地址` | DPlayer + P2P 播放 |
| `/ck/?url=视频地址` | CKplayer 播放 |
| `/ck2/?url=视频地址` | CKplayer + P2P 播放 |
| `/index1.php?url=视频地址` | 按设备自动调用 ArtPlayer |

## 🚀 使用方法

### 环境要求

- PHP 5.4+（建议 7.x）
- Apache / Nginx 任意 Web 服务器
- 无需数据库

### 部署步骤

1. 将项目文件上传至 Web 服务器根目录（或任意站点子目录）
2. 通过浏览器访问项目首页，或直接拼接播放地址：

   ```
   http://你的域名/dp2/?url=https://example.com/path/video.m3u8
   ```

3. 在首页点击对应入口可切换播放器模式

> `index.php` 中的播放器入口、跳转地址等为可配置项，请根据实际情况修改。

## 📄 许可证

本项目使用 [MIT](LICENSE) 许可证开源。

```
MIT License

Copyright (c) 2026 yun1002
```

### 第三方组件

本项目引用了以下第三方开源组件，其版权与许可证归各自作者所有，请在使用时一并遵守：

- [ArtPlayer](https://artplayer.org/) — MIT License (c) zhw2590582
- [DPlayer](https://github.com/DIYgod/DPlayer) — MIT License (c) DIYgod
- [CKPlayer](https://github.com/f4m3-coder/CKplayer) — GPL-3.0 License
- [hls.js](https://github.com/video-dev/hls.js) — Apache License 2.0 (c) Dailymotion, Brightcove
- [CDNBye / p2p-engine](https://www.cdnbye.com/) — P2P 加速内核（art / dp2 / ck2 使用的增强版 hls.js）
- [jQuery](https://jquery.com/) — MIT License

## ⚖️ 提示

本项目供二次学习与开发参考，请勿用于侵犯他人版权的用途。遵守法律法规，合理合法使用本工具。
