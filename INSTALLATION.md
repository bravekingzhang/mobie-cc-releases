# Mobie CC 安装指南

Mobie CC 是闭源商业插件，当前通过两种方式安装：使用 BRAT 从 GitHub Release 安装与更新，或下载 ZIP 手动安装。两种方式安装的是同一组插件文件，已有 Vault 笔记不会被移动或改名。Mobie CC 不在 Obsidian 官方第三方插件目录中发布。

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
- **iPhone/iPad 手动安装**：只有当所用文件管理工具能够访问该 Vault 的隐藏 `.obsidian/plugins/` 目录时才适用；否则建议使用下方 BRAT 安装方式。

## 方式二：通过 BRAT 安装与更新（推荐）

BRAT（Beta Reviewer's Auto-update Tool）是 Obsidian 第三方插件目录中的安装辅助插件，可从 Mobie CC 的公开 GitHub Release 安装并检查更新：

1. 打开“设置 → 第三方插件 → 浏览”，搜索并安装 **BRAT**，然后启用它。
2. 打开命令面板，执行 `BRAT: Add a beta plugin for testing`；也可以进入 BRAT 设置页点击 `Add Beta Plugin`。
3. 粘贴公开分发仓库地址：

   ```text
   https://github.com/bravekingzhang/mobie-cc-releases
   ```

4. 点击添加并等待 BRAT 完成下载。
5. 返回“设置 → 第三方插件”，找到 **Mobie CC** 并启用。
6. 进入“设置 → Mobie CC”，配置模型服务并运行“测试连接”。
7. 后续可在 BRAT 中检查更新；首次加载仍有 24 小时完整试用。

激活价格为永久版人民币 99 元、一个月版人民币 19.9 元；购买请联系老码小张：`1595819400@qq.com`。

BRAT 和 ZIP 最终安装的是同一 Release 产物。BRAT 只是安装与更新工具；通过 BRAT 安装不表示 Mobie CC 已进入官方 Community Plugins 目录或经过 Obsidian 人工审核。

## 卸载

1. 先在“设置 → 第三方插件”中关闭 Mobie CC。
2. 如需保留会话和设置，先备份 `.obsidian/plugins/mobie-cc/data.json`。
3. 在 Obsidian 中卸载插件，或完全退出后删除 `.obsidian/plugins/mobie-cc/`。

Mobie CC 的长期记忆位于 Vault 根目录的 `.mobie-cc/context/`。卸载插件不会自动删除这个目录；是否保留或删除由用户决定。
