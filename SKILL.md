---
name: rakuten-shop-analysis
description: 调用云端 Rakuten 店铺分析后端。用户提供乐天店铺 URL 或 shop code 时使用，返回结构化 summary、可用 bucket 样本和降级原因码。适合竞品尽调、店铺结构分析和爆款样本提取。
metadata:
  openclaw:
    requires:
      bins: ["node"]
---

# Rakuten Shop Analysis

调用云端后端分析 Rakuten 店铺，输入只支持：

- 乐天店铺 URL
- 乐天 `shopCode`

普通用户默认**不需要**手动设置 `RAKUTEN_SKILL_API_BASE_URL`。
如果 skill 已正确安装，直接提供店铺链接或 `shopCode` 即可。

默认 API 地址：

```bash
RAKUTEN_SKILL_API_BASE_URL=https://rakuten.845817074.xyz
```

可选 token：

```bash
RAKUTEN_SKILL_API_TOKEN=...
```

运行方式：

```bash
node <skill_dir>/scripts/run.mjs <shopInput>
```

输出：

- 紧凑 JSON
- 包含 `summary`
- 包含所有 `availableBuckets`
- 包含 `degradedReasonCodes`

规则：

- 未配置 token 时走匿名试用通道
- 配置 token 时自动附带 `Authorization: Bearer ...`
- 遇到短期限流 (`429`) 时会按 `Retry-After` 自动重试
- 只负责请求云端 API，不在本地执行 Rakuten 抓取逻辑

面向终端用户的推荐说法：

- `分析这个乐天店铺：https://www.rakuten.co.jp/vacchetta-topkapi/`
- `帮我分析这个乐天店铺：vacchetta-topkapi`
- `帮我出一份这个乐天店铺的分析报告：https://www.rakuten.co.jp/vacchetta-topkapi/`

不要先要求用户输入环境变量，除非对方明确在做高级配置或自定义后端地址。
