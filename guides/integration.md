# Integration guide

## 1. Get a token

向平台负责人申请 BFF API token。按用途分档（示例）：

| Tier | Can | Cannot |
|---|---|---|
| read | 读会话 / commerce-context | 写消息、支付 |
| reply | 读 + 发消息（agent/human） | 付款 / 退款 / 改价 |
| internal | 服务端 webhook（如 paid） | 暴露给浏览器 |

Token 勿进 git、勿进聊天。

## 2. Base URL

生产 / 测试 BFF 地址由负责人下发。SDK：`baseUrl` + `Authorization: Bearer <token>`。

## 3. Rate limits

以 BFF 返回的限流头 / 错误为准；客户端需退避重试。具体配额见合同或运维说明。

## 4. Webhooks

- 付款等内部事件：服务端 → BFF（幂等）。  
- 出站 webhook（可选）：订阅会话/订单事件时按合同验签。

## 5. Handoff

新系统接入：fork `cyberforums-integration-template` → 填 DECISIONS → 对接 BFF → 跑 contract-tests 占位用例 → 在 `cyberforums-docs` 登记仓库。
