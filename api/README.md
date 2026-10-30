# Open API

## Source of truth (current)

在独立 OpenAPI 落地前，以 **marketplace-chat** 仓库内的合同草案为准（§2–§7b，含 actor 规则）。

- Repo: https://feicode.com/Cyberforums/marketplace-chat  
- 实现变更须同步更新该合同；本目录只做索引与版本说明。

## Versioning

- URL 前缀：`/v1/...`  
- 破坏性变更升主版本；兼容字段可加，不可默默改语义。  
- Agent / 第三方只使用 BFF **开放**端点，不调 Discourse/Woo 内部 API。
