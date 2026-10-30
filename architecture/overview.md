# Architecture overview

## Boundaries

| Layer | Role | Not responsible for |
|---|---|---|
| WooCommerce | Products, orders, payments (source of truth) | Forum UX, chat UI |
| Discourse | Discussion, trust groups, shop PM | Order/payment state |
| BFF (`marketplace-chat` / `cyberforums-bff-core`) | Open API, webhooks, attest, commerce-context | Dual write of orders |

Agents, SDKs, and future tools (e.g. Chatwoot) **must** go through BFF open APIs — never Discourse or Woo internals.

## Current repos (Cyberforums org)

| Repo | URL |
|---|---|
| discourse-cyberforums-marketplace | https://feicode.com/Cyberforums/discourse-cyberforums-marketplace |
| marketplace-chat | https://feicode.com/Cyberforums/marketplace-chat |
| cyberforums-bff-core | https://feicode.com/Cyberforums/cyberforums-bff-core |
| wenpai-marketplace-forum-sync | https://feicode.com/Cyberforums/wenpai-marketplace-forum-sync |
| forum-embed | https://feicode.com/Cyberforums/forum-embed |
| cyberforums-docs | https://feicode.com/Cyberforums/cyberforums-docs |
| cyberforums-sdk-js | https://feicode.com/Cyberforums/cyberforums-sdk-js |
| cyberforums-sdk-python | https://feicode.com/Cyberforums/cyberforums-sdk-python |
| cyberforums-integration-template | https://feicode.com/Cyberforums/cyberforums-integration-template |

See [repos.md](../repos.md) for roles and types.
