# NaiCode Desktop 发行版

下载：见 [Releases](../../releases)。每个版本包含：

- Windows 桌面版（x64、arm64）
- macOS 桌面版（Apple 芯片、Intel；没有 Apple 签名和公证）
- Linux 桌面版（x64、arm64；AppImage、deb、rpm、pacman）
- 命令行 CLI 单文件（Windows、macOS、Linux 各 x64 / arm64）
- Android 手机远控 App

## 维护者：怎么出一个版本

Actions → 「打包全部客户端」→ Run workflow，填要打包的分支、标签或提交（默认 `wip-snapshot`）。全部平台都成功后自动建一个预发布 Release；任一平台失败就不发布，已成功平台的产物留在那次运行的 Artifacts 里。

工作流需要以下仓库 secrets（Settings → Secrets and variables → Actions）：

| Secret | 内容 |
| --- | --- |
| `SOURCE_REPO` | 源码仓库，`owner/name` 格式 |
| `SOURCE_REPO_TOKEN` | 细粒度 Personal access token：仓库只选源码仓库，权限 Contents 只读 |
| `ANDROID_KEYSTORE_BASE64` | Android 发版密钥库文件（.jks）的 Base64 |
| `ANDROID_KEYSTORE_PASSWORD` | 密钥库密码 |
| `ANDROID_KEY_ALIAS` | 密钥别名 |
| `ANDROID_KEY_PASSWORD` | 密钥密码 |
