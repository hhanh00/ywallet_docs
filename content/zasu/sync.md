---
title: Synchronization
weight: 40
---

{{% notice warning %}}
This wallet will **not** automatically start synchronization 
{{% /notice %}}

![Synch](/zasu-04.png)

1. Activate/Deactivate the Spam Filter which skips over transactions
with large number of outputs and actions (50+)
2. Synchronization button bar, see below for explanations
3. Update the latest block height from the server

## Synchronization Actions

### Sync

Start synchronization. The wallet uses WARP 2, a custom built algorithm.

### Reset

Set the wallet birth height. Transactions that happened before that height
are not scanned.

### Rewind

Return the synchronization point to an earlier height. 

### Rescan

Rescan all the transactions from this wallet. 

See [Rescan]({{< relref "rescan" >}})
