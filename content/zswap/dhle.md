---
title: Discrete Log Equality Accross Groups
weight: 70
---

When Bob extracted the secret key A from Alice's signature,
we assumed that he would be able to use it to redeem the ZEC.

However, without enforcing that the secret key used in BTC Lock
is also used in ZEC Lock, the ZSwap falls apart.

In fact, Bob only see public points P on secp256k1 and ak on Jubjub or Pallas.
There is no guarantee that they were generated from the same secret key
by Alice.

Therefore, Alice must present a ZK-proof that establishes that:

```math
There is a hidden value s such as $P = s.G_B$ and $ak = s.G_Z$
```

We create this proof using the Halo 2 proving system.

Likewise, Alice also checks that the public keys given by Bob are also
generated from a single secret key.

