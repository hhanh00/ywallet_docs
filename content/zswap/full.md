---
title: Full Picture
weight: 65
---

```mermaid
flowchart LR
    subgraph Bob [Bob's Wallet]
    BTCLockIn[Bob's Funds]
    end
    subgraph BTC [BTC Lock]
    BTCLockIn[Bob's Funds] -- B --> BTCLock[BTC]
    end
    subgraph BTCRedeem [BTC Redeem]
    BTCLock -- A+B --> BTCRedeemA[Alice]
    end
    subgraph BTCCancel [Cancellation]
    BTCLock -- A+B --> Cancel[BTC Cancel]
    end
    subgraph BTCRefund [Refund]
    Cancel -- A+B --> BTCRefundB[Bob]
    end
    subgraph BTCPunish [Punish]
    Cancel -- A+B --> BTCPunishA[Alice]
    end
    style BTCRedeem fill:MediumSeaGreen,color:white
    style BTCRefund fill:MediumSeaGreen,color:white
    style BTCCancel fill:Pink
    style BTCPunish fill:Pink
```

- Transactions in Pink are time locked, the signatures were provided off-chain before any on-chain transaction. **This is possible because transaction ID are non-malleable and deterministic.**
- Transactions in Green reveal the secret key through the signature adaptor

```mermaid
flowchart LR
    subgraph Alice [Alice's Wallet]
    ZECLockIn[Alice's Funds]
    end
    subgraph ZEC [ZEC Lock]
    ZECLockIn[Alice's Funds] -- A --> ZECLock[ZEC]
    end
    subgraph ZECRedeem [ZEC Redeem]
    ZECLock -- A+B --> ZECRedeemB[Bob]
    end
    style ZECRedeem fill:LightBlue
```

- Transactions in Blue can be signed once the second secret key is revealed by the signature from the corresponding green transaction.
