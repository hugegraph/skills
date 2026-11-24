# Codex imagegen 的 PR 配图扩展

把这份参考指南接入现有 `imagegen` 后，可以用原来的入口给 PR 配图。它会读取 PR 和相关代码，先确认要讲清的机制，再核对成图。有原生生图与委派能力时，会尝试双路生成和独立选图。GIF 依实际能力用原生工具或本地组帧，并检查播放。

`imagegen-preview-v0.1.0` 是固定试用快照。后续开发继续迭代，试用者按本页标签安装和反馈。

## 安装

需要能使用内置生图的 Codex 客户端。把下面的 Prompt 整段贴到 Codex，再根据它给出的文件位置核对改动。

```text
请把 HugeGraph 的 PR 配图扩展 imagegen-preview-v0.1.0 接到我当前正在使用的 Codex imagegen。

从固定版本读取参考文件 https://raw.githubusercontent.com/hugegraph/skills/imagegen-preview-v0.1.0/extensions/imagegen/technical-visuals.md ，校验 SHA-256 为 a5535c965ae2a28b27d3c5adb729fddf55e712c2d41dd6ab1b416547c9adc383。

先用当前工作目录的技能列表找出实际启用的 imagegen 和它的 SKILL.md。发现同名条目时先列出各自路径，由我确认使用哪一份。只有唯一条目时，先把 SKILL.md 和任何已有的同名参考文件备份到技能扫描目录之外。已有自定义的同名参考文件时，先问我是否替换。

在现有 imagegen 目录中保存 references/technical-visuals.md。在原 SKILL.md 的生图提示规划步骤加入一条按需引用，遇到 PR 链接配图或技术变化说明时、写生图提示前先读取该参考文件。已有等效引用时复用。保留现有通用生图流程，所有改动都在原 imagegen 目录内。

刷新技能列表，确认只登记一个 imagegen，路径还是原来的 SKILL.md，且引用能打开。核查失败就恢复备份。最后告诉我改动路径、备份位置和如何恢复。
```

## 验证与恢复

开一个新会话。在平时输入 `@` 或 `$` 的技能选择器里搜索 `imagegen`，确认只有一项。挑一个可读取的 PR，贴上链接并说「给这个 PR 配张图，重点讲清改了什么」。想检查动画时，可以明确要求「给这个 PR 生成一张 GIF，展示几个关键状态」。

临时 Codex 环境已验证原地接入、重启和回滚时的技能登记。客户端菜单、实际出图和本机兼容性按上面的步骤核查。客户端升级可能重新生成内置文件，届时用相同的固定标签重新核对和接入。

恢复时，让 Codex 还原安装时备份的 `SKILL.md` 和参考文件。如果参考文件是本次新增，移除该文件。重新加载后核对仍只登记一份 `imagegen`。

[来源与实测范围](PROVENANCE.md)
