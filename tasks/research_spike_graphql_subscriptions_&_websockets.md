# 🌐 Research Spike: GraphQL Subscriptions & WebSocket Abuse

**Goal:**  
Explore GraphQL subscriptions (WebSockets) for over-permissive or unauthenticated real-time data streams, often used in chat, trading, dashboards, and collaborative apps.

**Why It Matters:**  
Many GraphQL implementations use WebSocket-based subscriptions to push data. These are often:
- Unauthenticated after handshake
- Mapped to insecure channel filters
- Prone to info leaks or privilege escalation

---

### ✅ Tasks

- [ ] Discover WebSocket endpoints (e.g., `/graphql`, `/subscriptions`)
- [ ] Use `wscat`, `Apollo client`, or browser devtools to observe subscriptions
- [ ] Try unauthorized subscription (e.g., subscribe to another user’s feed)
- [ ] Abuse filters or mutation side effects to push messages
- [ ] Test for lack of access control during reconnection

---

### 🎯 Deliverables

- Subscription traffic PCAPs
- Examples of:
  - Unauthorized channel access
  - Broadcast data leakage
- Detection logic:
  - WebSocket channel auditing
  - Rate limits, unusual patterns
- Recommendations:
  - Token re-verification on reconnect
  - Per-channel access enforcement

---

### 🏷️ Tags

`graphql` `subscriptions` `websockets` `real-time-data` `info-leak` `t1071` `pubsub-abuse`