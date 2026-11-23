# Open-Science 研究案例

把一个案例页交给本机 AI 助手，按通用指南准备 Open-Science、校验并导入研究包，再打开对应的研究会话。阅读已有归档不需要重新运行研究或额外发送模型消息。

**[打开黄色线虫案例页](https://lingjinli1986-stack.github.io/open-science-cases/helixlife-worm-longevity.html)** · **[当前英文指南 v0.2.3](https://lingjinli1986-stack.github.io/open-science-cases/instruction-v0.2.3.md)**

## 使用方法

打开案例页，点击 **复制给 AI 助手**，将原文粘贴到 WorkBuddy 等本机助手的新聊天。也可以直接转发下面这句提示词：

> 请按案例页中的「AI 助手打开指南」，在我电脑的 Open-Science 中打开[线虫长寿基因与人类长寿证据](https://lingjinli1986-stack.github.io/open-science-cases/helixlife-worm-longevity.html)。

提示词只需一个案例页链接。页面静态 HTML 中明确提供指南与 `.science` 下载链接，助手继续读取即可；不要根据案例名字猜下载地址。如果链接无法读取，助手应说明具体缺失项。

## 保留的指南

| 版本 | 用途 |
| --- | --- |
| [v0.1.0](instruction-v0.1.0.md) | 第一版，原样保留，供对照和回退。`instruction.md` 保留相同内容，兼容旧英文页面。 |
| [v0.2.3 · 2026-11-23 修订](instruction-v0.2.3.md) | 黄色页面使用。按官网检查安装与版本；允许在产品支持时暂缓 CodeBuddy／模型配置；按本次导入 ID 定位；确认 OS 窗口并引导最后一次点击。 |

本次按维护要求将当天的交接修订合并到 v0.2.3。原 v0.2.3、v0.2.4 和其他中间版本保留在 Git 提交历史，当前目录不再维护中间测试入口。版本名与修订日期一起标识当前文稿。

[整理前的固定快照](https://github.com/lingjinli1986-stack/open-science-cases/tree/e295f00c67846f56fd63f21c2514d7ab70a82ac7)保留原文件及原始版本内容，供对照和回退。

## 当前验证状态

| 路径 | 结果 |
| --- | --- |
| Mac + WorkBuddy + 已安装 OS 1.3.3 | 研究包校验和导入成功，OS 自动到前台，用户点击一次 Open imported Session 后显示正确正文。 |
| 已有 CodeBuddy 中国站订阅 | Agent 与主模型就绪检查通过；主模型由测试者在官方设置界面接手选择，并非 WorkBuddy 全自动完成。 |
| 一个链接的精简提示词 | 检查页面、指南与研究包的链接关系；尚未重跑完整 WorkBuddy 流程。 |
| 首次安装、配置失败后 Skip、Windows、其他 Agent | 当前修订仍待对应实机验证。 |

区分三个结果：**导入成功、OS 到前台、正文显示**。事后截图不能证明正文自动打开。日常流程不发送模型测试消息。

## 页面与文件

| 文件 | 说明 |
| --- | --- |
| `helixlife-worm-longevity.html` | 当前黄色中文案例页；研究短片和 Replay 视频仍为占位。 |
| `instruction-v0.2.3.md` | 当前通用英文指南。 |
| `instruction-v0.1.0.md` / `instruction.md` | 第一版及兼容入口。 |
| `index.html` | 原英文线虫页面，保留原地址。 |
| `ai-or-human-what-story-structure-reveals.html` | 原故事案例页面，保留原地址。 |

## 如何新增案例

1. 以当前黄色页面为模板，更新案例标题、正文、图片及唯一的 `.science` 链接。
2. 保留可直接读取的 **AI 助手打开指南** 链接和 **下载研究包** 链接。指南继续使用同一份通用文件。
3. 复制按钮自动使用当前页面地址和案例标题，不把案例名称写死在指南里。
4. 发布后在未登录浏览器检查页面与指南；核对复制文本只有目标案例页链接，研究包对应正确案例。
5. 单独记录安装、配置、导入、前台及用户点击结果，不把静态网页检查当作完整流程验收。

## 维护边界

公开仓库保存可分享页面、指南和使用说明；私有维护仓库保存过程记录及内部资料。不会将账号、凭据或个人研究记录写入公开文件。
