# fitsize-site · GitHub Pages 发布包（docs 内草稿）

状态：**待用户审阅，未发布**。本目录是 FitSize 公开支持页与隐私政策的静态网站源文件，内容来自 [隐私事实核查](../copy/privacy-facts.md)。本轮未创建 GitHub 仓库、未 push、未开启 Pages。

## 用户已定（2026-11-09，经 Grok Bot / 项目经理转达）

- 托管：GitHub Pages，账号 **Hahhahha123**，单独仓库 **fitsize-site**（公开仓库，`main` 分支根目录发布）。
- 支持邮箱：**yueyang295513@gmail.com**。
- 中英双语。

## 目录

| 文件 | 用途 | 预计网址 |
| --- | --- | --- |
| `index.html` | 双语首页，链接到四个页面 | https://hahhahha123.github.io/fitsize-site/ |
| `zh-Hans/support.html` | 中文支持页（联系邮箱 + 常见问题） | https://hahhahha123.github.io/fitsize-site/zh-Hans/support.html |
| `zh-Hans/privacy.html` | 中文隐私政策 | https://hahhahha123.github.io/fitsize-site/zh-Hans/privacy.html |
| `en/support.html` | English support page | https://hahhahha123.github.io/fitsize-site/en/support.html |
| `en/privacy.html` | English privacy policy | https://hahhahha123.github.io/fitsize-site/en/privacy.html |
| `support.html`、`privacy.html` | 根目录语言选择页，给只能填一个网址的地方用 | https://hahhahha123.github.io/fitsize-site/support.html 、…/privacy.html |
| `.nojekyll` | 让 Pages 原样发布静态文件 | — |

每个页面自带内联样式，不依赖外部 CSS、字体、脚本或 Cookie，可以直接复制进 App 包做离线版。

## App Store Connect 填写

| 字段 | 简体中文页 | English (U.S.) 页 |
| --- | --- | --- |
| Support URL | `…/fitsize-site/zh-Hans/support.html` | `…/fitsize-site/en/support.html` |
| Privacy Policy URL | `…/fitsize-site/zh-Hans/privacy.html` | `…/fitsize-site/en/privacy.html` |
| Marketing URL | 可留空，或填首页 | 同左 |

`FITSIZE_PRIVACY_POLICY_URL`（App 内「在线版本」链接，`Config/FitSize.xcconfig:6`）只有一个值，建议填根目录语言选择页 `https://hahhahha123.github.io/fitsize-site/privacy.html`；若工程改为按语言本地化该键，则分别填两种语言的页面。xcconfig 中 `//` 会被当作注释，写法见 `docs/release/app-store/submission.md:87`。

## 发布步骤（工程师执行，需用户的 GitHub 账号登录）

1. 在 Hahhahha123 下新建公开仓库 `fitsize-site`。
2. 把本目录除 `README.md` 外的全部文件（含 `.nojekyll`、`zh-Hans/`、`en/`）放到 `main` 分支根目录。
3. 仓库 Settings → Pages → Build and deployment：Source 选 Deploy from a branch，分支 `main`、目录 `/(root)`，保存；确认 Enforce HTTPS 已开启。
4. 用无痕窗口逐个打开上表网址，确认无需登录、HTTPS 有效、中英互链和邮箱链接可用。
5. 给 yueyang295513@gmail.com 发一封测试信，确认能收到。
6. 把实际网址回填到 `docs/tasks.md` 的 FS-08-E2，再填入 App Store Connect。

实际路径以 Pages 上线后的结果为准；若与上表不同，同步更新本文件和商店字段。

## 上线前核对

- **界面名称要和发布的版本一致。** 用户已拍板采用修订后名称（会员→基础版/高级版，系统工具→工具，接续处理→继续处理）；支持页已按新词书写。工程师正在改 App UI。下表保留对照，便于核对旧版 1.0（1）界面与新版差异；若网站必须在旧版 App 仍在架时上线，可临时改回右列名称：

| 支持页写法（已拍板） | 旧 App 1.0（1）里的名称 |
| --- | --- |
| 工具 / Tools | 系统工具 |
| 基础版与高级版 / Basic & Pro | 会员权益 |
| 继续处理 / Continue | 接续处理 |
| 换视频 / Change Video | 换片 |
| 在这里压缩 / Compress Here | 在面板中压缩 |
| 去掉声音 / Mute | 静音去脂 |
| 最高 30 fps / Max 30 fps | 锁 30 fps |
| 原片已在上限内 · 直接共享 | 原片已达标 · 直接共享 |

- **App 内离线政策**与网页同文。网页版多出的「关于本网站」一段对 App 内版本同样成立，可保留。修改政策时两处一起改，生效日期一起更新。
- 现有 `docs/release/app-store/web/`（仅中文，支持页联系方式为占位）保留为历史，不再作为发布源。
