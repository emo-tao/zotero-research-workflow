# Zotero Research Workflow — Codex Skill

把 Zotero 文献收集、中文元数据、划词翻译、整篇 PDF 翻译、笔记和引用这几件事，整理成**一个可复用的 Codex skill**。核心是指导 AI 按目标选择插件、检查本机环境、定位故障，并用一篇真实论文验证结果。

本仓库提供工作流说明，**不包含或代替 Zotero、任何插件、翻译引擎及其安装包**。各组件由原项目维护，安装时请从上游发布页获取与你的 Zotero 版本兼容的版本。整篇 PDF 翻译只需要 Zotero、zotero-pdf2zh 插件、对应的本地 Server/引擎和可用翻译服务；其余插件按需选择。

## 一张图看分工

```text
浏览器 ── Zotero Connector ──> Zotero 文献条目与附件
                                 ├─ Jasminum：中文文献元数据
                                 ├─ Translate for Zotero：词句/段落翻译
                                 ├─ zotero-pdf2zh：整篇 PDF 翻译
                                 │    └─ 本地 Server → PDF 翻译引擎 → 翻译服务
                                 ├─ Better Notes：结构化笔记
                                 └─ Better BibTeX：引用键与 .bib 导出
```

“本地 Server”只描述任务处理位置；如果选用云端翻译服务，论文内容仍可能发送到该服务。使用前检查服务配置和文献的使用要求。

## 安装 Skill

将 [`skills/zotero-research-workflow`](skills/zotero-research-workflow/SKILL.md) 文件夹复制到你的 Codex skills 目录，例如 Windows 上的 `~/.codex/skills/zotero-research-workflow`。保留文件夹内的 `references/`。在新对话中使用 `$zotero-research-workflow`，并说明你的系统、Zotero 版本及想完成的任务。

示例：

> 用 `$zotero-research-workflow` 帮我在 Windows 上打通 Zotero 的整篇 PDF 翻译。先检查我已装的插件和 Server，再用一篇可公开测试的 PDF 验证中译版能否正确回挂到原条目。

Skill 会引导检查与排障；它不会自动取得登录信息、翻译 API 密钥，也不会把你的论文或日志上传到本仓库。

## 仓库内容

- [`SKILL.md`](skills/zotero-research-workflow/SKILL.md)：任务路由、完成标准与操作边界。
- [`plugin-map.md`](skills/zotero-research-workflow/references/plugin-map.md)：组件分工与最小组合。
- [`windows-setup.md`](skills/zotero-research-workflow/references/windows-setup.md)：Windows 搭建、验证与 PowerShell 注意点。
- [`troubleshooting.md`](skills/zotero-research-workflow/references/troubleshooting.md)：根据实际错误定位 Python、依赖和连接问题。
- [`sources-and-credits.md`](docs/sources-and-credits.md)：所有上游项目与来源说明。

## 验收标准

插件安装成功、Server 页面可打开，都只是中间状态。最后应能在**同一篇小型测试 PDF** 上完成翻译，确认输出文件存在、能打开、挂回正确的 Zotero 条目，并抽查正文、公式和参考文献的可读性。见 [Windows 搭建与验证](skills/zotero-research-workflow/references/windows-setup.md)。

本工作流来自作者 `emo-tao` 在 Windows 上整理的 Zotero 全文翻译环境搭建与排障记录；插件和引擎的原始项目、文档和授权均归各自维护者，详见[来源与致谢](docs/sources-and-credits.md)。

