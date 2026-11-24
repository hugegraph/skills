# 来源与实测范围

本试用快照固定的是 HugeGraph PR 配图实验所用的技术指南。扩展接入已有 Codex 内置 `imagegen`，原生生图能力由宿主提供。

- [OpenAI imagegen 公开快照](https://github.com/openai/skills/tree/e6afb0d74cc75d220df2faf3dd6c635c2dc6a108/skills/.system/imagegen) 记录上游通用工作流和 Apache-2.0 许可。实验的通用底本来自桌面发行包。
- [GPT-Image2-Skill 固定版本](https://github.com/wuyoscar/GPT-Image2-Skill/tree/8a1e114104a5c0eb4cdccaad21d90ba7819379a5) 为本地组帧和播放校验提供历史参考。发布文件未包含该项目的脚本和资源。

技术指南参加了 13 个 PR 的 16 组串行与两路并行对照，包含独立评审和 GIF 播放核查。临时桌面 Codex 0.171.0-alpha.13 验证了在已有 `imagegen` 入口接入该指南后只登记一份，并在重启后仍登记一份。试用阶段还要收集不同客户端版本的菜单和实际出图结果。
