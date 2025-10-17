# 附录 A：工具参考

> 仅在执行相关命令时再查阅。若需自动化操作，请先阅读对应 Python 脚本说明。

## 截图验证
- 捕获网页截图：`.venv/bin/python tools/screenshot_utils.py URL [--output OUTPUT] [--width WIDTH] [--height HEIGHT]`
- 结合 LLM 解析截图：`.venv/bin/python tools/llm_api.py --prompt "问题" --provider {openai|anthropic} --image path/to/screenshot.png`
- 示例：
  ```python
  from screenshot_utils import take_screenshot_sync
  from llm_api import query_llm

  img = take_screenshot_sync("https://example.com", "screenshot.png")
  resp = query_llm("页面背景颜色是什么？", provider="openai", image_path=img)
  print(resp)
  ```

## LLM 调用
- 快速调用：`.venv/bin/python tools/llm_api.py --prompt "问题" --provider "openai"`
- 支持的 provider：OpenAI (默认 gpt-5)、Azure OpenAI (gpt-4o-ms)、DeepSeek、OpenAI gpt-5（显式调用）、Gemini、Qwen 本地模型。
- 建议先阅读 `tools/llm_api.py` 了解可选参数，再根据任务需求选择模型。

## Web 抓取与搜索
- 抓取网页：`.venv/bin/python tools/web_scraper.py --max-concurrent 3 URL1 URL2 URL3`
- 站内搜索：`.venv/bin/python tools/search_engine.py "keyword"`
- 若抓取结果需要进一步分析，可结合 LLM 或自建脚本处理。
