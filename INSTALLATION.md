# Mobie CC 手机安装指南

Mobie CC 是闭源商业插件，目前提供两种安装方式：

1. **通过 BRAT 安装与更新（推荐）**：不需要操作隐藏目录，后续更新也更方便。
2. **通过 ZIP 手动安装**：适合无法使用 BRAT，或希望完全手动管理插件文件的用户。

两种方式安装的是同一套 `main.js`、`manifest.json` 和 `styles.css`，不会移动或改名已有的 Vault 笔记。Mobie CC 当前不在 Obsidian 官方 Community Plugins 目录中；BRAT 只是安装工具，不代表 Mobie CC 已被官方收录或人工审核。

## 安装前准备

- Obsidian 版本不低于 `1.13.6`；
- 确认当前打开的是准备安装 Mobie CC 的目标 Vault；
- 在“设置 → 第三方插件”中关闭受限模式，允许加载第三方插件；
- BRAT 安装需要手机能够访问 GitHub。

## 方式一：通过 BRAT 安装与更新（推荐）

### 第一步：安装 BRAT

1. 在手机 Obsidian 中打开目标 Vault。
2. 进入“设置 → 第三方插件 → 浏览”。
3. 搜索 **BRAT**。
4. 安装并启用 **Obsidian42 - BRAT**。

### 第二步：添加 Mobie CC

1. 打开 Obsidian 命令面板。
2. 执行：

   ```text
   BRAT: Add a beta plugin for testing
   ```

3. 粘贴下面任意一种仓库地址：

   ```text
   bravekingzhang/mobie-cc-releases
   ```

   或：

   ```text
   https://github.com/bravekingzhang/mobie-cc-releases
   ```

4. 点击 **Add Plugin**，等待 BRAT 下载完成。
5. 返回“设置 → 第三方插件”。如果暂时没有看到 Mobie CC，关闭设置页后重新打开。
6. 找到 **Mobie CC** 并打开启用开关。

安装 BRAT 后，也可以在手机上打开下面的 Obsidian URI，让 BRAT 自动进入添加页面：

```text
obsidian://brat?plugin=bravekingzhang/mobie-cc-releases
```

### 通过 BRAT 更新

打开命令面板，执行：

```text
BRAT: Check for updates to beta plugins and UPDATE
```

也可以进入 BRAT 设置，开启启动 Obsidian 时自动检查更新。GitHub 可能存在几分钟缓存；刚发布的新版本没有立即出现时，请稍后重试。

### BRAT 安装常见问题

- **提示无法访问 GitHub**：检查手机网络或代理后重试。
- **提示找不到 Release**：确认仓库地址没有空格，并使用上面给出的完整地址或短地址。
- **BRAT 显示安装完成，但列表没有 Mobie CC**：关闭并重新打开第三方插件设置；必要时重启 Obsidian。
- **更新后仍是旧版本**：在 BRAT 中执行单插件更新或重新安装，然后重启 Obsidian。

## 方式二：通过 ZIP 手动安装

### 第一步：下载安装包

1. 打开 [Mobie CC Releases](https://github.com/bravekingzhang/mobie-cc-releases/releases/latest)。
2. 下载最新的 `mobie-cc-x.y.z.zip`。
3. 完全退出 Obsidian，不要只切换到后台。
4. 在手机文件管理器中打开“显示隐藏文件”。

### 第二步：复制插件目录

1. 解压 ZIP，得到名为 `mobie-cc` 的文件夹。
2. 打开目标 Vault 下的 `.obsidian/plugins/`；如果 `plugins` 不存在，可以手动创建。
3. 把整个 `mobie-cc` 文件夹复制到 `plugins` 中。
4. 检查最终结构必须是：

   ```text
   <你的 Vault>/.obsidian/plugins/mobie-cc/
   ├── main.js
   ├── manifest.json
   └── styles.css
   ```

不要把三个文件直接放在 `plugins` 下，也不要形成 `mobie-cc/mobie-cc/` 两层同名目录。

当前 Android 真机 Vault 如果位于：

```text
/storage/emulated/0/Documents/obsidian/local
```

那么插件目录应为：

```text
/storage/emulated/0/Documents/obsidian/local/.obsidian/plugins/mobie-cc/
```

### 第三步：启用插件

1. 重新打开 Obsidian。
2. 进入“设置 → 第三方插件”。
3. 找到 **Mobie CC** 并启用。
4. 进入“设置 → Mobie CC”，配置模型服务并运行“测试连接”。

### 手动升级

1. 在第三方插件设置中关闭 Mobie CC，并完全退出 Obsidian。
2. 备份 `.obsidian/plugins/mobie-cc/data.json`。
3. 使用新 ZIP 中的 `main.js`、`manifest.json` 和 `styles.css` 覆盖旧文件。
4. 不要删除或覆盖 `data.json`。
5. 重新打开 Obsidian，启用 Mobie CC，并确认设置页版本与模型连接正常。

### ZIP 安装常见问题

- **插件列表中看不到 Mobie CC**：检查目录名是否为 `mobie-cc`，三个文件是否直接位于这一层，以及 `manifest.json` 是否被改成了 `manifest.json.txt`。
- **覆盖后仍显示旧版本**：完全结束 Obsidian 进程后重新启动。
- **出现两层同名目录**：把内层 `mobie-cc` 移到 `.obsidian/plugins/`，删除多余外层目录。
- **iPhone/iPad 无法访问隐藏目录**：改用 BRAT 安装。

## 首次使用

1. 打开“设置 → Mobie CC”。
2. 选择模型协议，填写 API Base URL、模型编码和 API Key。
3. 点击“测试连接”，确认模型支持结构化工具调用。
4. 打开 Mobie CC 聊天页开始使用。

首次加载提供 24 小时完整 Agent 试用。永久激活码为人民币 99 元，一个月激活码为人民币 19.9 元；购买请联系老码小张：`1595819400@qq.com`。未激活或授权到期不会锁住笔记、已有对话、候选和长期记忆。

## 卸载

1. 在“设置 → 第三方插件”中关闭 Mobie CC。
2. 如需保留会话和设置，备份 `.obsidian/plugins/mobie-cc/data.json`。
3. 如果通过 BRAT 安装，先在 BRAT 设置中停止跟踪 Mobie CC，再从第三方插件列表卸载。
4. 如果通过 ZIP 安装，完全退出 Obsidian 后删除 `.obsidian/plugins/mobie-cc/`。

长期记忆文件位于 Vault 根目录的 `.mobie-cc/context/`。卸载插件不会自动删除这些文件，是否保留由用户决定。
