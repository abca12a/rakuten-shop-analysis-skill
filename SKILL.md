---
name: rakuten-shop-analysis
description: 用于分析 Rakuten 乐天店铺。用户提供店铺链接或 shopCode 时使用，适合竞品研究、店铺结构分析和快速出报告。
metadata:
  openclaw:
    requires:
      bins: ["node"]
---

# Rakuten Shop Analysis

分析 Rakuten 乐天店铺，并返回结构化结果。

适合用于：

- 店铺分析
- 竞品研究
- 爆款样本查看
- 快速出分析报告

支持输入：

- 乐天店铺链接
- 乐天 `shopCode`

## 如何使用

安装后，直接对 OpenClaw 说：

```text
分析这个乐天店铺：https://www.rakuten.co.jp/vacchetta-topkapi/
```

或者：

```text
帮我出一份这个乐天店铺的分析报告：https://www.rakuten.co.jp/vacchetta-topkapi/
```

也可以直接输入 `shopCode`：

```text
分析这个乐天店铺：vacchetta-topkapi
```

## 当前说明

- 安装后可直接匿名试用
- 当前匿名限额：每个 IP 每 60 秒最多 30 次 API 请求
- 如果限流，等待约 1 分钟后再试即可
- 当前版本不需要配置 token，也不需要配置后端地址
