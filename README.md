# 视频导演 · DeepSeek Harness 插件

在 Harness 原来的聊天里交代目标、提供素材、看成片、继续修改。统一入口 `video-director`，自动安排动画、真实录屏或混合镜头。

## 复制链接安装

打开 Harness 的 **插件 → 添加插件**，将下面这一整行粘贴到安装输入框：

```text
https://github.com/200966371/harness-video-director/releases/download/v0.1.0/lifei-harness-video-director-0.1.0.tgz
```

点击 **安装 → 立即启用**，随后重启 Harness。无需自己下载、解压或寻找文件路径。

首次安装如果提示依赖安装脚本被阻止，并列出 `esbuild`，点击 Harness 提供的 **「允许这些脚本并重试」**，等待安装完成后再点「立即启用」。这是渲染依赖的安装步骤，无需改文件或手动执行命令。

插件已包含 `video-director`、`lifei-tutorial-video`、`frame-smith`，不需要另装两个 Skill，也不需要安装 Codex。

## 第一次使用

先配置好自己的 Harness 模型并确认能正常聊天。然后在任意聊天发送：

> 请使用视频导演插件，做一个 10 秒的横屏无声动画，1920×1080，带中文字幕。内容是：把资料分成“待处理”“处理中”“已完成”三类。让文件卡片实际移动到对应分类里，文字清楚。自动安排镜头，完成后在本聊天给我可播放的视频。

有配音、录屏或图片时，直接拖进聊天并说明制作要求。成片在同一聊天展示，继续说“第二段文字大一点，配音别动”即可修改。

完整说明见 [快速上手](快速上手.html)；可从 [Releases](https://github.com/200966371/harness-video-director/releases) 下载 HTML 后打开阅读。

## 环境与数据

- 已验证：macOS Apple Silicon、Harness **0.2.1-rc.2**。其他系统及版本尚未验证。
- 使用自己的 Harness 模型配置；安装包没有作者的账号、API key 或个人素材。
- 首次安装通常需要访问 GitHub 与 npm 安装源，自动获取 Remotion、React、TypeScript 依赖。
- Node.js 24+；Harness 桌面版自带运行时。渲染优先使用已有 Chrome/Chromium/Edge，找不到时下载 Chromium。
- 视频在本机渲染；项目默认保存在 `~/.dsh/data/lifei-video-director`。
- 当前不内置自动配音、任意软件自动录屏或自动发布。已有音频和真实录屏可以导入。

## 命令行安装

```sh
dsh plugin --profile desktop add https://github.com/200966371/harness-video-director/releases/download/v0.1.0/lifei-harness-video-director-0.1.0.tgz
```

## 发布与来源

本仓库用于分发安装包与说明。插件的文本源码、模板和三个 Skill 都包含在 `.tgz` 中；校验信息见 [SHA256SUMS](SHA256SUMS)。

`frame-smith` 基于 [mouse-lin/frame-smith](https://github.com/mouse-lin/frame-smith)，包内保留上游 MIT 许可证及本地适配来源记录。其他资源的来源和许可见安装包中的 `THIRD_PARTY_NOTICES.md` 与各自 `SOURCE.md`，不将组合包统一重新声明为 MIT。
