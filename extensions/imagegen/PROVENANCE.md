# 来源与实测范围

这份技术指南源自 HugeGraph PR 配图实验。扩展接入已有 Codex 内置 `imagegen`，原生生图能力由宿主提供。

- [OpenAI imagegen 公开快照](https://github.com/openai/skills/tree/e6afb0d74cc75d220df2faf3dd6c635c2dc6a108/skills/.system/imagegen) 记录上游通用工作流和 Apache-2.0 许可。实验的通用底本来自桌面发行包。
- [GPT-Image2-Skill 固定版本](https://github.com/wuyoscar/GPT-Image2-Skill/tree/8a1e114104a5c0eb4cdccaad21d90ba7819379a5) 为本地组帧和播放校验提供历史参考。发布文件未包含该项目的脚本和资源。

早期的分工版指南参加了 13 个 PR 的 16 组串行与两路并行对照，包含独立评审和 GIF 播放核查。当前双图流程改为独立执行同一份生图提示。隔离环境用桌面随附的 Codex 0.171.0-alpha.13.2 和 CLI 0.169.0 交替启动，验证了按路径停用内置版后只有用户版 `imagegen` 启用，以及恢复内置版后的技能登记。试用阶段还要收集不同客户端版本的菜单和实际出图结果。

新版用两个静态 PR 在隔离的桌面会话中验证了两次初始调用使用相同提示和设置。三位评审独立盲评后，视觉综合分落在预设容差内。其中一例的容量色带补修后仍有比例偏差。需要精确比例时，仍应对照源码检查实际图形。

扩展说明中的前后对照采用当时默认配置的出图和接入指南后的并行精选图。三人复核的图形解释中位数为 3 分和 5 分，满分为 5 分。 [对照图片](README.md#效果对比) · [同一个公开 PR](https://github.com/apache/hugegraph/pull/3390)

## Excalidraw 构图实测

现行技术指南记为 `current V1`（`0ba87ef`）。候选 E 借鉴了同一对象跨状态的画法。先用源码核对一个具体例子，固定未变部分的位置和标记，再用形状、位置或填色突出变化。结论取决于大小或空间能否容纳时，共用原点和比例尺。 [Excalidraw Diagram Skill](https://github.com/coleam00/excalidraw-diagram-skill/blob/8646fcc9f74f38539c6cdb4c969723336a96ddcd/SKILL.md)

10 个案例共 40 张原生图。每例三位评审独立盲评，综合分中可读性占 35%。4 个同提示案例用于观察原生出图波动。

| 范围 | current V1 | 候选 E | 加权差值 |
| --- | ---: | ---: | ---: |
| 全部 10 例 | 4.245 | 4.358 | +0.113 |
| 应用新规则的 6 例 | 4.342 | 4.504 | +0.163 |
| 其中新增的 4 例 | 4.338 | 4.556 | +0.219 |
| 同提示对照的 4 例 | 4.100 | 4.138 | +0.038 |

任务 ID 案例提高 0.600 分。候选图清楚区分了显示编号、内部路由键和搜索命中。导入回滚案例的总分持平，可读性降了 0.5 分，其中一张候选图把删除箭头接错了对象。该图未过准确性门槛，试用版继续使用 `current V1`。 [任务 ID #889](https://github.com/apache/hugegraph-toolchain/pull/889) · [导入回滚 #880](https://github.com/apache/hugegraph-toolchain/pull/880)
