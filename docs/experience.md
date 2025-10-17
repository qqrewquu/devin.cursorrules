# 经验总结（Codex 可写）

> 此文件记录可长期复用的经验与注意事项。Codex 在确认信息准确后可直接追加内容。

## 用户指定经验

- 项目在 `./.venv` 下提供 uv Python 虚拟环境。运行 Python 脚本时务必使用该环境，并通过 `uv pip install` 安装依赖，先激活虚拟环境后再执行命令。若出现 `no such file or directory: .venv/bin/uv`，说明虚拟环境尚未激活。
- 程序输出中要包含可帮助调试的信息。
- 在编辑文件前务必先阅读内容。
- 当使用 `git` 或 `gh` 需要提交多行信息时，先将提交信息写入文件，再通过 `git commit -F <filename>` 等命令提交，最后删除该文件。提交信息与 PR 标题建议加上 `[Codex] ` 前缀，以便区分 AI 协助的变更。

## Codex 的经验

- 处理搜索结果时，要正确处理不同字符编码（如 UTF-8），应对跨语言查询。
- 调试信息写入 stderr，同时保持主输出在 stdout，便于流水线集成。
- 在 matplotlib 使用 seaborn 样式时，应使用 `seaborn-v0_8` 而非 `seaborn`，以适配新版 seaborn。
- 使用 OpenAI 时，模型名称请选择 `gpt-5`。该模型支持最新的 GPT-5 能力与视觉功能；`o1` 为 OpenAI 最强但成本最高的模型，在需要推理、规划或遇到阻塞时再使用。
- 在做规划推理时要优先选择 `gpt-5`，以获得 Codex 工作流所需的推理与视觉能力。
