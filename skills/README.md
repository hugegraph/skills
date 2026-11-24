# 独立技能目录

独立 skill 按工作流分目录，每个目录提供一个可单独安装的入口。已有 skill 的按需指南放在 [`extensions/`](../extensions/) 下。

## 目录约定

```text
skills/<skill-name>/
├── SKILL.md
├── references/    # 可选，入口明确指向要按需读取的资料
├── scripts/       # 可选，可重复执行的辅助脚本
└── assets/        # 可选，输出所需的资源
```

`SKILL.md` 以 YAML frontmatter 开头，至少包含 `name` 和 `description`。`name` 与目录名一致，使用小写字母、数字和连字符。`description` 写清用途和触发条件。具体字段见 [Agent Skills 规范](https://agentskills.io/specification)。

## 当前目录

独立技能发布后会列在 [仓库索引](../README.md#技能与扩展)。现可试用的 PR 配图流程通过 [imagegen 扩展](../extensions/imagegen/README.md) 接入现有入口。
