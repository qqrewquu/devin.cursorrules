# Lessons

## User Specified Lessons

- You have a uv python venv in ./.venv. Always use it when running python scripts. It's a uv venv, so use `uv pip install` to install packages. And you need to activate it first. When you see errors like `no such file or directory: .venv/bin/uv`, that means you didn't activate the venv.
- Include info useful for debugging in the program output.
- Read the file before you try to edit it.
- Due to Windsurf's limit, when you use `git` and `gh` and need to submit a multiline commit message, first write the message in a file, and then use `git commit -F <filename>` or similar command to commit. And then remove the file. Include "[Windsurf] " in the commit message and PR title.

## Windsurf learned

- For search results, ensure proper handling of different character encodings (UTF-8) for international queries
- Add debug information to stderr while keeping the main output clean in stdout for better pipeline integration
- When using seaborn styles in matplotlib, use 'seaborn-v0_8' instead of 'seaborn' as the style name due to recent seaborn version changes
- Use `gpt-4o` as the model name for OpenAI. It is the latest GPT model and has vision capabilities as well. `o3` is the most advanced and expensive model from OpenAI. Use it when you need to do reasoning, planning, or get blocked.
- Use `claude-sonnet-4-5-20250929` as the model name for Claude. It is the latest Claude model (Claude Sonnet 4.5) and has vision capabilities as well.
- When running Python scripts that import from other local modules, use `PYTHONPATH=.` to ensure Python can find the modules. For example: `PYTHONPATH=. python tools/plan_exec_llm.py` instead of just `python tools/plan_exec_llm.py`. This is especially important when using relative imports.

# Multi-Agent Scratchpad

## Background and Motivation

(Planner) 用户需要了解 Vercel 官方文档的最新内容，以便掌握最近的功能更新、指南调整等信息，从而指导后续的开发或部署决策。

## Key Challenges and Analysis

(Planner)
- Vercel 文档覆盖面广，需要辨识真正“最新”的部分（如平台公告、Changelog、Docs 首页）。
- 官方内容可能分布在多个板块，需要确认来源的权威性与更新时间。
- 需确保引用信息准确且有具体链接，避免遗漏关键更新。

## Verifiable Success Criteria

(Planner)
- 至少给出 1 个 Vercel 官方文档入口，并注明其最近的更新时间或版本说明。
- 总结 2-3 个近期的重要更新或新特性，并提供对应的官方链接。
- 输出一份包含主要参考链接的清单，方便用户后续查阅。

## High-level Task Breakdown

(Planner)
1. 查找 Vercel 官方文档站点上的最新更新来源（如 Docs 首页、Changelog）。
2. 浏览并提取最新或最重要的变更与指南内容。
3. 汇总关键信息并整理成易读的说明及链接列表。

## Current Status / Progress Tracking

- (Executor, 2025-10-16) ✅ 完成步骤（1）：访问 `https://vercel.com/docs/introduction` 并提取页面核心内容。
- (Executor, 2025-10-16) ✅ 完成步骤（2）：梳理页面核心要点，整理引用信息。
- (Executor, 2025-10-16) ✅ 完成步骤（3）：整理摘要与链接，准备回复用户。

## Next Steps and Action Items

(Planner)
- [x]（1）使用官方文档或 Changelog 收集近期更新信息及更新时间。
- [x]（2）记录更新细节，整理出 2-3 条关键要点及对应链接。
- [x]（3）编写供用户参考的摘要与链接清单。

## Executor's Feedback or Assistance Requests

(Executor: Write here when encountering blockers, questions, or need for more information during execution)
