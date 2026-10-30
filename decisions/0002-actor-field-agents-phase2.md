# 0002 — `actor` field & agents phase 2

## Context

合同草案需要区分消息/操作发起方：人、agent、系统。客户端不可伪造身份。

## Decision

- 字段：`actor` ∈ `human | agent | system`，可选 `actor_id`。
- **仅服务端按凭证写入**；客户端传入的 `actor` / `actor_id` 一律丢弃（见合同 §7b.1）。
- Agent 经 BFF token：可读、可回复。
- Agent **不可**：付款、退款、改价。

## Consequences

- Webhook / 开放 API 实现必须剥离客户端 actor。
- SDK 不暴露可写的 actor 字段。
- 支付与退款仍走 Woo 真源 + 既有内部 webhook。

## Affected repos

marketplace-chat, cyberforums-bff-core, cyberforums-sdk-js, cyberforums-sdk-python.
