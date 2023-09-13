---
title: Rescan
weight: 45
---

Zasu performs an incremental backup of your wallet
in the memo of your change outputs.

When you restore your seed phrase and rescan
the blockchain, use the Rescan method and enter
the snapshot height.

Since Zasu makes an automatic backup whenever you
make a payment, you will notice
that the latest snapshot height changes.

The latest value is shown when you open the Rescan menu.

The rescan will restore the wallet to the given height.
You need to use normal synchronization to catch up with
the latest blockchain height.

![Rescan](/zasu-05b.png)

{{% notice info %}}
Rescan is equivalent to a full import but can run thousands of times faster
than a normal sync even with a birth height.
{{% /notice %}}

## Demo

{{< youtube VYoAWAxA2E0 >}}
