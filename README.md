# Harry-Chen-Dev.github.io

个人站点。同时承担 App Store 提交所需的 **技术支持网址** 和 **隐私政策网址**。

纯静态 HTML + 一个 CSS 文件，没有构建步骤，没有依赖。改完直接 push 就上线。

## 上线

已经上线：<https://harry-chen-dev.github.io/>

仓库 `Harry-Chen-Dev/Harry-Chen-Dev.github.io`，公开，GitHub Pages 从 `main` 分支根目录发布。用户站点（`<用户名>.github.io`）推上去 Pages 会自动开，不用去 Settings 里点。

之后改动直接推，一两分钟生效：

```bash
git add -A && git commit -m "..." && git push
```

## 填进 App Store Connect 的网址

| App Store Connect 字段 | 填这个 |
|---|---|
| Support URL（必填） | `https://harry-chen-dev.github.io/shotsort/support/` |
| Privacy Policy URL（必填） | `https://harry-chen-dev.github.io/shotsort/privacy/` |
| Marketing URL（选填） | `https://harry-chen-dev.github.io/shotsort/` |

App 内的设置页也要放一个可点开的隐私政策链接，指向同一个隐私政策地址 —— 这是 5.1.1(i) 的明确要求，只在 App Store Connect 里填不够。

## 结构

```
.
├── index.html                     首页：我是谁 + 作品目录 + 联系方式
├── assets/style.css               唯一的样式表
└── shotsort/
    ├── index.html                 App 介绍页（Marketing URL）
    ├── support/index.html         技术支持页（Support URL）
    └── privacy/index.html         隐私政策页（Privacy Policy URL）
```

`.nojekyll` 让 GitHub Pages 跳过 Jekyll，直接按原样发布这些文件。

## 上线后要改的三处

1. **App 上架后**：`shotsort/index.html` 里「Get it」那段换成 App Store 链接（文件里有注释标好位置），首页那张卡的状态从 `Coming soon` 改成 `On the App Store`。
2. **Mac 应用定名后**：首页第二条目前是无名占位，补上名字和链接。
3. **隐私政策一旦有实质变化**：改 `shotsort/privacy/index.html` 顶部的 Effective 日期。旧版本 App 仍适用发布当时的版本。

## OpenPreview

新增 OpenPreview 介绍、支持与隐私页面，中英双语：

| 语言 | 介绍 | 支持 | 隐私 |
|---|---|---|---|
| English | `/openpreview/` | `/openpreview/support/` | `/openpreview/privacy/` |
| 简体中文 | `/openpreview/zh/` | `/openpreview/zh/support/` | `/openpreview/zh/privacy/` |

域名为 `https://harry-chen-dev.github.io`。首发采用一次性付费；尚未上架，保持 Coming soon。上架后仅在取得真实商店地址时补入下载链接。其他项目条目保留。

OpenPreview 的远程图片需主动许可；不要套用其他应用“绝不联网”的表述。其政策还区分系统最近文件/缓存、支持邮件、GitHub Pages 和 Google Fonts。纯 HTML，共用唯一 CSS，无新增脚本或构建依赖。中文政策与英文政策需一起更新。
