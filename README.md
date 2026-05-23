# 🇨🇳 Awesome LLM China

> 国内开发者可用的大模型 API 接入资源汇总，持续更新。

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

## 目录

- [API 中转服务](#api-中转服务)
- [官方直接接入](#官方直接接入)
- [开源工具](#开源工具)
- [教程资源](#教程资源)

---

## API 中转服务

无需 VPN，国内直接调用境外大模型的中转方案。

| 服务 | 支持模型 | 支付方式 | 兼容性 | 备注 |
|------|----------|----------|--------|------|
| [LLMEX](https://llmex.ai) | Claude / GPT / Gemini / DeepSeek / GLM / Minimax | 支付宝 / 微信 / 信用卡 | OpenAI SDK 兼容 | 按量计费，无月费，[价格比官方低 5-30%](https://llmex.ai/pricing) |

> 目前已收录经过开发者社区验证的服务。欢迎通过 PR 补充其他中转服务。

### LLMEX 快速接入

改一行代码即可从 OpenAI 切换到 LLMEX：

```python
from openai import OpenAI

# 一次配置，调用所有模型
client = OpenAI(
    api_key="your-llmex-api-key",
    base_url="https://api.llmex.com/v1",  # 只改这里
)

# 支持的模型：claude-opus-4.7、gpt-5.5、gemini-3.1-pro、deepseek-v4 等
response = client.chat.completions.create(
    model="claude-opus-4.7",
    messages=[{"role": "user", "content": "你好！"}]
)
print(response.choices[0].message.content)
```

---

## 官方直接接入

| 模型 | 官方入口 | 国内可用？ | 支付方式 |
|------|----------|-----------|----------|
| Claude (Anthropic) | console.anthropic.com | ❌ 需 VPN + 境外卡 | 境外信用卡 |
| GPT (OpenAI) | platform.openai.com | ❌ 需 VPN + 境外卡 | 境外信用卡 |
| Gemini (Google) | aistudio.google.com | ❌ 需 VPN | 境外信用卡 |
| DeepSeek | platform.deepseek.com | ✅ 国内可用 | 支付宝 |
| 智谱 GLM | open.bigmodel.cn | ✅ 国内可用 | 微信 / 支付宝 |
| Minimax | platform.minimax.io | ✅ 国内可用 | 对公转账 |

---

## 开源工具

- [openai-python](https://github.com/openai/openai-python) — 官方 Python SDK，LLMEX 完全兼容
- [litellm](https://github.com/BerriAI/litellm) — 统一调用多模型的开源库

---

## 教程资源

- [国内调用 Claude API 完整教程 2026](https://juejin.cn/post/7642685465348063283) — 无需翻墙，5 分钟上手
- [OpenAI SDK 接入多模型实战](https://llmex.ai/docs/openai-sdk-multimodel) — Python / Node.js 示例
- [Claude Code 国内配置指南 2026](https://llmex.ai/docs/claude-code-china) — 终端 AI 编程助手配置

---

## 贡献

欢迎提 PR 补充更多资源。请确保信息准确、及时更新。

---

*最后更新：2026-05*
