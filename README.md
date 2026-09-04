# Harry-Chen-Dev.github.io

个人站点。同时承担 App Store 提交所需的 **技术支持网址** 和 **隐私政策网址**。

纯静态 HTML + 一个 CSS 文件，没有构建步骤，没有依赖。改完直接 push 就上线。

## 上线

GitHub 上新建一个**公开**仓库，名字必须正好是 `Harry-Chen-Dev.github.io`，然后：

```bash
cd ~/Developer/Harry-Chen-Dev.github.io
git init
git add -A
git commit -m "Personal site with Shotsort support and privacy pages"
git branch -M main
git remote add origin git@github.com:Harry-Chen-Dev/Harry-Chen-Dev.github.io.git
git push -u origin main
```

推完到仓库 **Settings → Pages**，Source 选 `Deploy from a branch`，分支 `main` / 目录 `/ (root)`。首次生效通常要 1–2 分钟。

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
