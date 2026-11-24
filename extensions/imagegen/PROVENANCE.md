# 来源与实测范围

这份技术指南源自 HugeGraph PR 配图实验。扩展接入已有 Codex 内置 `imagegen`，原生生图能力由宿主提供。

- [OpenAI imagegen 公开快照](https://github.com/openai/skills/tree/e6afb0d74cc75d220df2faf3dd6c635c2dc6a108/skills/.system/imagegen) 记录上游通用工作流和 Apache-2.0 许可。实验的通用底本来自桌面发行包。
- [GPT-Image2-Skill 固定版本](https://github.com/wuyoscar/GPT-Image2-Skill/tree/8a1e114104a5c0eb4cdccaad21d90ba7819379a5) 为本地组帧和播放校验提供历史参考。发布文件未包含该项目的脚本和资源。

早期的分工版指南参加了 13 个 PR 的 16 组串行与两路并行对照，包含独立评审和 GIF 播放核查。当前双图流程改为独立执行同一份生图提示。隔离环境用桌面随附的 Codex 0.171.0-alpha.13.2 和 CLI 0.169.0 交替启动，验证了按路径停用内置版后只有用户版 `imagegen` 启用，以及恢复内置版后的技能登记。试用阶段还要收集不同客户端版本的菜单和实际出图结果。

新版用两个静态 PR 在隔离的桌面会话中验证了两次初始调用使用相同提示和设置。三位评审独立盲评后，视觉综合分落在预设容差内。其中一例的容量色带补修后仍有比例偏差。需要精确比例时，仍应对照源码检查实际图形。

扩展说明中的前后对照采用当时默认配置的出图和接入指南后的并行精选图。三人复核的图形解释中位数为 3 分和 5 分，满分为 5 分。 [对照图片](README.md#效果对比) · [同一个公开 PR](https://github.com/apache/hugegraph/pull/3390)
