# cyberforums-docs

Cyberforums 平台总文档骨架（monodoc）。

组织：[Cyberforums on FeiCode](https://feicode.com/Cyberforums)

## Contents

| Path | Role |
|---|---|
| [architecture/overview.md](architecture/overview.md) | 架构总览与真源边界 |
| [repos.md](repos.md) | 仓库清单 |
| [decisions/](decisions/) | 决策记录（ADR） |
| [api/](api/) | 开放 API 合同索引 |
| [guides/integration.md](guides/integration.md) | 接入指南 |
| [DECISIONS.md](DECISIONS.md) | 决策索引 |

## Principles

1. **WooCommerce** = 商品 / 订单 / 支付唯一真源  
2. **Discourse** = 讨论与权益组  
3. **BFF** = 对外唯一开放入口（SDK / agent / 第三方只调 BFF）

修改与自定义决策请写入 `decisions/`，并在本仓 `DECISIONS.md` 留索引。
