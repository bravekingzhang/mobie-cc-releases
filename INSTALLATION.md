# Mobie CC 安装指南

Mobie CC 支持两种安装方式：通过 ZIP 文件手动安装，或在审核通过后从 Obsidian 官方第三方插件市场安装。两种方式安装的是同一组插件文件，已有 Vault 笔记不会被移动或改名。

## 方式一：通过 ZIP 文件手动安装

这种方式适合内测、尚未上架市场时安装，以及提前体验新版本。以下步骤以 Android 手机为主。

### 准备工作

1. 在 Obsidian 中确认目标仓库（Vault）的位置。
2. 向 Mobie CC 发布方获取 `mobie-cc-x.y.z.zip`。
3. 完全退出 Obsidian。不要只把它切到后台。
4. 如果文件管理器默认不显示以 `.` 开头的目录，请先打开“显示隐藏文件”。

### 首次安装

1. 解压 `mobie-cc-x.y.z.zip`，得到名为 `mobie-cc` 的文件夹。
2. 打开目标 Vault 下的 `.obsidian/plugins/`。如果 `plugins` 不存在，可以手动创建。
3. 将整个 `mobie-cc` 文件夹复制到 `plugins` 中。
4. 检查最终目录结构必须是：

   ```text
   <你的 Vault>/.obsidian/plugins/mobie-cc/
   ├── main.js
   ├── manifest.json
   └── styles.css
   ```

   不要把三个文件直接放进 `plugins`，也不要形成 `mobie-cc/mobie-cc/` 两层同名目录。

5. 重新打开 Obsidian，进入“设置 → 第三方插件”。如尚未允许第三方插件，请先关闭受限模式。
6. 在已安装插件列表找到 **Mobie CC**，打开右侧开关。
7. 进入“设置 → Mobie CC”，配置模型服务并点击“测试连接”。

例如 Vault 位于 `/storage/emulated/0/Documents/obsidian/local` 时，插件目录应为：

```text
/storage/emulated/0/Documents/obsidian/local/.obsidian/plugins/mobie-cc/
```

### 升级手动安装版本

1. 在“设置 → 第三方插件”中关闭 Mobie CC，并完全退出 Obsidian。
2. 备份 `.obsidian/plugins/mobie-cc/data.json`。该文件保存插件设置与状态，不包含构建代码。
3. 用新 ZIP 中的 `main.js`、`manifest.json`、`styles.css` 覆盖旧文件。
4. 不要删除或覆盖 `data.json`。
5. 重新打开 Obsidian 并启用 Mobie CC，在设置页确认版本与模型连接。

### 常见问题

- **第三方插件列表中看不到 Mobie CC**：重点检查目录名是否为 `mobie-cc`、三个文件是否都在这一层，以及 `manifest.json` 是否被文件管理器改成了 `manifest.json.txt`。
- **覆盖后还是旧版本**：完全结束 Obsidian 进程后再启动，必要时先关闭插件再覆盖。
- **模型无法回答**：到 Mobie CC 设置页运行“测试连接”，确认协议、Base URL、模型编码和 API Key；模型必须支持结构化工具调用。
- **试用结束后无法继续提问**：在 Mobie CC 设置页复制本机安装码，按发布方提供的方式获取并输入激活码。未激活不会锁住笔记和已有对话。
- **iPhone/iPad 手动安装**：只有当所用文件管理工具能够访问该 Vault 的隐藏 `.obsidian/plugins/` 目录时才适用；否则建议使用官方市场安装。

## 方式二：通过 Obsidian 官方第三方插件市场安装

> Mobie CC 只有在 Obsidian 官方目录的自动审查通过并发布后，才能通过下面的方法搜索到。目录页面可能显示“尚未经过 Obsidian 员工人工审核”，这是平台自动提供的安全状态，不影响已通过自动审查的插件安装。提交期间请使用 ZIP 手动安装。

1. 打开 Obsidian，进入“设置 → 第三方插件”。
2. 关闭受限模式，然后点击“浏览”。
3. 搜索 **Mobie CC**。
4. 打开详情页，点击“安装”。
5. 安装完成后点击“启用”。
6. 进入“设置 → Mobie CC”，配置模型服务并运行“测试连接”。
7. 首次加载有 24 小时完整试用；如需继续使用，在设置页按提示完成激活。

激活价格为永久版人民币 99 元、一个月版人民币 19.9 元；购买请联系老码小张：`1595819400@qq.com`。

市场版本更新后，可在“设置 → 第三方插件”中执行检查更新与升级。市场安装由 Obsidian 从对应版本的 GitHub Release 下载 `main.js`、`manifest.json` 和 `styles.css`，不需要用户自己处理 Vault 路径。

## 卸载

1. 先在“设置 → 第三方插件”中关闭 Mobie CC。
2. 如需保留会话和设置，先备份 `.obsidian/plugins/mobie-cc/data.json`。
3. 在 Obsidian 中卸载插件，或完全退出后删除 `.obsidian/plugins/mobie-cc/`。

Mobie CC 的长期记忆位于 Vault 根目录的 `.mobie-cc/context/`。卸载插件不会自动删除这个目录；是否保留或删除由用户决定。
