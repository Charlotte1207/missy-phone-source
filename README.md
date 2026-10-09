# Missy Phone

**公开源码 · 非商业使用 · AI 角色陪伴手机前端**

Missy Phone（Missy = “miss you”）是一个以单文件 `index.html` 为核心的 AI 角色陪伴前端。它将聊天、角色设定、记忆、世界书、桌面组件和外观设置等体验组织成类似手机的界面。

> [!IMPORTANT]
> **本项目禁止未经许可的商业使用。** 本项目采用 **CC BY-NC-SA 4.0**。使用、修改或再发布本项目时，必须遵守许可证全文。
>
> 本项目属于“公开源码、非商业授权”，不应将其描述为符合 OSI 定义的开源软件。Creative Commons 官方不建议把 CC 许可证用于软件代码；这里选择它，是为了沿用参考项目的非商业与相同方式共享授权思路。发布前请确认你理解此取舍，并确认你有权授权仓库内准备发布的内容。

## ✦ 项目特点

- **单文件部署：** 核心应用以根目录的 `index.html` 运行，无需 Node.js、npm 或编译构建流程。
- **自备 API：** 使用者自行配置兼容的 AI API 服务、Base URL、API Key 和模型名称。本项目不提供 AI 模型或 API 额度。
- **本地优先：** 应用数据主要保存在当前浏览器的 IndexedDB / localStorage 中；清理浏览器数据、更换浏览器或设备可能导致数据无法继续使用。
- **可配置体验：** 包含角色聊天、角色资料、记忆/世界书、桌面和外观设置等功能。实际功能以仓库当前版本为准。

## 🚀 部署教程

### 方法一：使用 Vercel（推荐）

#### A. 将 GitHub 仓库连接到 Vercel

1. 确保仓库根目录中有入口文件 **`index.html`**。README、LICENSE 等说明文件可以与它放在同一目录。
2. 登录 [Vercel](https://vercel.com/)。
3. 在 Vercel 控制台创建新项目，选择从 GitHub 导入仓库；首次使用时按提示授权 Vercel 访问对应仓库。
4. 选择 Missy Phone 仓库并进入项目配置。
5. 对于纯静态单文件项目，Framework Preset 选择 **Other**。
6. **Build Command（构建命令）留空**；如果有可覆盖的构建设置，请启用覆盖并保持为空。没有 `public` 目录时，输出目录使用项目根目录 `.`。
7. 点击 Deploy。部署完成后打开 Vercel 提供的网址，检查页面是否正常加载。
8. 之后向所连接的 GitHub 分支提交更新，Vercel 通常会自动进行新部署。

官方说明：[Vercel — Configuring a Build](https://vercel.com/docs/builds/configure-a-build)。

#### B. 继续使用手动上传部署

如果你已经在自己的 Vercel 账号里使用手动上传方式，可以继续沿用当前控制台支持的静态文件部署流程。上传内容的根目录应直接包含 `index.html`，而不是把它再套在一个未被选为项目根目录的子文件夹内。Vercel 控制台界面和手动部署入口可能变化，请以账号内实际显示的步骤为准。

### 方法二：使用 GitHub Pages

1. 确认 `index.html` 位于仓库根目录，且已经提交到默认分支（例如 `main`）。
2. 打开 GitHub 仓库，进入 **Settings → Pages**。
3. 在 **Build and deployment** 的 **Source** 中选择 **Deploy from a branch**。
4. 在 Branch 中选择 `main`（或实际使用的默认分支），目录选择 **`/(root)`**，然后点击 Save。
5. 等待 GitHub Pages 完成发布，然后在 Pages 设置页打开网站地址。
6. 后续将更新提交到所选分支和目录后，Pages 会按设置重新发布。

官方说明：[GitHub Pages — Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)。

### 🔑 配置 AI API

1. 打开已部署的 Missy Phone。
2. 进入应用中的“设置 → 全局 API 设置”（具体名称以当前版本界面为准）。
3. 按你的 API 服务商要求填写 Provider、Base URL、API Key 和模型名。
4. 保存后进行一次普通对话测试。如果请求失败，检查 Base URL、模型名、余额/额度、服务商的浏览器跨域（CORS）限制和网络连接。

**API Key 安全提示：** 这是前端应用。为发起 API 请求，浏览器会将你配置的密钥发送给对应的 API 端点。不要把真实密钥写入公开的 `index.html`、README、截图或提交历史；不要在不信任的设备上留下密钥。公开部署本身不会把你的 Key 自动变成安全的服务器端密钥管理方案。

## 💾 本地数据与隐私

- 角色、聊天和设置等数据主要保存在当前浏览器的本地存储中；这不等于有云端自动备份。
- 发送 AI 请求时，相应的提示词、消息内容以及请求所需参数会发往你配置的第三方 API 服务。该服务如何记录、处理或保留数据，取决于它自己的政策和设置。
- 需要迁移或保留数据时，请使用应用提供的导出功能，并妥善保存备份。分享备份前请检查内容是否包含私人资料。不要将个人备份放进公开仓库。
- 更换浏览器、设备、域名或清理网站数据时，原有本地数据可能无法自动迁移。
- 应用功能、兼容性和浏览器行为可能随版本、服务商或托管平台变化。

## 📜 许可证

本项目采用 **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International（CC BY-NC-SA 4.0）**。

基本要求：

- **署名（BY）：** 再分享时须给出适当署名、许可证链接，并说明是否做过修改。
- **非商业（NC）：** 不得将授权内容用于许可证定义下的商业目的。
- **相同方式共享（SA）：** 分享修改后的授权作品时，须按相同许可证条件共享。

以上是便于阅读的摘要，**不替代许可证全文**。具体定义、许可范围、例外和法律效力，以 [CC BY-NC-SA 4.0 官方法律文本](https://creativecommons.org/licenses/by-nc-sa/4.0/legalcode) 为准。若希望进行任何可能属于商业用途的使用，应在使用前取得著作权人的单独书面许可。

本许可证只适用于项目权利人有权授权且纳入本项目许可范围的内容；第三方组件、素材和服务仍受其各自条款约束。更多信息见 [LICENSE](./LICENSE) 与 [THIRD_PARTY_NOTICES.md](./THIRD_PARTY_NOTICES.md)。

## ⚠️ 免责声明

请在使用前阅读 [DISCLAIMER.md](./DISCLAIMER.md)。使用本项目不代表获得 AI 模型、第三方 API 或任何外部资源的授权。

## 🙋 问题与反馈

提问前请提供可复现的步骤、浏览器/设备信息，以及不包含 API Key、访问令牌、聊天隐私或其他秘密的错误信息。请勿在 Issue 中提交密钥、私密备份或个人聊天记录。
