# Rakuten Shop Analysis Skill

独立分发用 OpenClaw skill 仓库。

## 安装

OpenClaw 里直接安装这个 GitHub 仓库：

```text
https://github.com/abca12a/rakuten-shop-analysis-skill
```

安装后可直接匿名试用；如果要更高额度，再配置 `RAKUTEN_SKILL_API_TOKEN`。

## 说明

这个仓库只包含 skill 本体，不包含后端抓取服务。skill 会调用已部署公网后端：

```bash
https://rakuten.845817074.xyz
```

## 文件结构

```bash
SKILL.md
agents/openai.yaml
scripts/run.mjs
scripts/format-output.mjs
tests/run.test.mjs
```

## 可选环境变量

```bash
RAKUTEN_SKILL_API_BASE_URL=https://rakuten.845817074.xyz
RAKUTEN_SKILL_API_TOKEN=your-token
```

- 不配置 `RAKUTEN_SKILL_API_TOKEN` 时走匿名试用
- 配置 token 后走认证额度

## 本地验证

```bash
npm test
node scripts/run.mjs vacchetta-topkapi
```

## 分发建议

- 对外直接给这个 GitHub 地址即可
- `Display name` 建议用 `Rakuten Shop Analysis`
