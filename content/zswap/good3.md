---
title: Zwap Successful - Summary
weight: 50
---

```mermaid
sequenceDiagram
    Bob->>BTCLock: 1 BTC
    Alice->>ZECLock: 1000 ZEC
    Bob-->>Alice: Signature Adaptor for Alice Secret (off-chain)
    Alice-->>BTCLock: Alice decrypts the Signature (off-chain)
    BTCLock->>Alice: reveals her Secret, redeems 1 BTC
    ZECLock->>Bob: Bob uses his Secret and Alice Secret, redeems 1000 ZEC
```

