# Mobie CC

Mobie CC 是运行在 Obsidian 移动端里的知识与工作 Agent。它能从你的 Vault 找回旧观点、决定和素材，延续你确认过的表达偏好与工作方式，陪你推进当前任务，再把值得保留的结果整理成待审核内容。

Agent 编排、Vault 检索、工具执行、候选审核和长期记忆都在当前 Obsidian 设备内完成；模型推理会直接请求你自己配置的第三方模型 API。

## 核心能力

- 用自然语言搜索和阅读允许范围内的 Vault 笔记，并在回答中保留来源；
- 结合当前笔记补结构、论据、反例和旧素材；
- 通过 `@` 或“添加引用”明确选择笔记与文件夹上下文；
- 将知识或长期偏好整理成候选，先预览 diff，再由用户确认写回；
- 通过 Profile、Style、Work Mode 和 Vault 四类有界记忆逐渐理解你的目标与协作习惯；
- 读取公开 HTTPS 网页，并支持禁止域名列表；
- 隐私模式不向模型提供 Vault、网页、候选或长期记忆工具。

Mobie CC 不启动 Shell、Claude Code、Codex 或其他本地进程，也不会默认把整个 Vault 一次性上传给模型。

## 安装

### Obsidian Community Plugins

正式上架后，在 Obsidian 中打开“设置 → 第三方插件 → 浏览”，搜索 **Mobie CC**，点击“安装”并启用。

### ZIP 手动安装

从 [Releases](https://github.com/private-coder-zhang/mobie-cc-releases/releases) 下载 `mobie-cc-x.y.z.zip`，解压后把整个 `mobie-cc` 文件夹放入：

```text
<你的 Vault>/.obsidian/plugins/
```

最终目录必须直接包含 `main.js`、`manifest.json` 和 `styles.css`。完整步骤、升级和排障见 [安装指南](INSTALLATION.md)。

最低支持 Obsidian `1.13.6`。插件面向 Android 和 iOS/iPadOS 移动端设计；当前 Android 已完成主要真机回归，iOS/iPadOS 仍在验证。

## 配置模型

进入“设置 → Mobie CC”，填写模型协议、API Base URL、模型编码和 API Key，然后运行“测试连接”。模型必须支持结构化工具调用。

API Key 保存于 Obsidian `SecretStorage`。模型费用由用户与所选模型服务商结算，Mobie CC 不代收模型 API 费用。

## 试用、价格与激活

首次加载提供 24 小时完整 Agent 试用。试用结束后，新 Agent 轮次需要与本机安装码匹配的激活码：

- 永久激活码：人民币 99 元；
- 一个月激活码：人民币 19.9 元；
- 购买方式：联系老码小张，邮箱 `1595819400@qq.com`。

激活码与本机随机安装 ID 派生的安装码绑定，不读取 IMEI、Android ID 或硬件序列号。未激活或授权到期不会锁住笔记、已有对话、候选、长期记忆和设置。

## 网络与隐私披露

使用 Agent 时，对话、最近对话、已确认长期记忆，以及工具按需读取的相关笔记片段或网页内容，可能发送给用户配置的第三方模型服务。网页工具会访问公开 HTTPS URL。插件不包含客户端遥测，也不运营模型中转或授权服务器。

详细数据边界、删除方式和购买记录处理方式见 [隐私说明](PRIVACY.md)。

## 闭源披露

Mobie CC 是闭源商业插件。公开仓库只提供用户文档、manifest、版本映射和编译后的 Release 资产；TypeScript 源码不向普通用户公开。源码会按照 Obsidian 对闭源插件的逐案审查要求向审核方提供访问，不使用代码混淆隐藏插件用途。

## 支持

- 授权、购买、隐私与技术支持：老码小张 <1595819400@qq.com>
- 问题反馈：[GitHub Issues](https://github.com/private-coder-zhang/mobie-cc-releases/issues)

## License

Mobie CC Copyright (C) 2026 by 老码小张. All rights reserved. See [LICENSE](LICENSE).

Bundled open-source component notices are available in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
