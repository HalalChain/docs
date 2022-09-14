---
title: sign and verify
weight: 3
#pre: "<b>1. </b>"
# chapter: true
---

{{% notice warning %}}
Do not use the private key used in this column.
<br>
It is dangerous.
{{% /notice %}}

### msg-sign

create a message signature.

```bash
~ qx msg-sign --help
Usage: msg-sign [wif] [message]
    -d  show signature details
    -m string
        the msg signature mode (default "qx")
```

#### Example

```bsah
~ qx msg-sign KyLSXswbDdBfrJoN6nPc8kPZJHEF5cBYey7f77dfnTFwGVEw1XGQ 'hello word'

ILKbIq3qp9zI6fTD6U4PKWe/MGIywzuejFCyVpze29LPDSFSPeDiHqoJdYzfKPMVD62T49c0TfjamCRSpjHhoeg=
```

#### show signature details

```bash
~ qx msg-sign -d KyLSXswbDdBfrJoN6nPc8kPZJHEF5cBYey7f77dfnTFwGVEw1XGQ 'hello word'

mode: qx
hash: 1ec592f0228c98f7b9beedc73b8ea91e71b34f3c11cd1064d01b54b7f060beb4
signature: 3045022100b29b22adeaa7dcc8e9f4c3e94e0f2967bf306232c33b9e8c50b2569cdedbd2cf02200d21523de0e21eaa09758cdf28f3150fad93e3d7344df8da982452a631e1a1e8
(base64): MEUCIQCymyKt6qfcyOn0w+lODylnvzBiMsM7noxQslac3tvSzwIgDSFSPeDiHqoJdYzfKPMVD62T49c0TfjamCRSpjHhoeg=
R: b29b22adeaa7dcc8e9f4c3e94e0f2967bf306232c33b9e8c50b2569cdedbd2cf
S: d21523de0e21eaa09758cdf28f3150fad93e3d7344df8da982452a631e1a1e8
compactsign: 20b29b22adeaa7dcc8e9f4c3e94e0f2967bf306232c33b9e8c50b2569cdedbd2cf0d21523de0e21eaa09758cdf28f3150fad93e3d7344df8da982452a631e1a1e8
(base64): ILKbIq3qp9zI6fTD6U4PKWe/MGIywzuejFCyVpze29LPDSFSPeDiHqoJdYzfKPMVD62T49c0TfjamCRSpjHhoeg=
compressed: true
```

---

### msg-verify

validate a message signature.

```bash
~ qx msg-verify --help
Usage: msg-verify [addr] [signature] [message]
    -m string
        the msg signature mode (default "qx")
```

#### Example 1

{{% notice tip %}}
The TmPip5CkA4e3fBRp7eo9onDYfVnba547uts is generated by KyLSXswbDdBfrJoN6nPc8kPZJHEF5cBYey7f77dfnTFwGVEw1XGQ private key.
{{% /notice %}}

```bash
~ qx msg-verify TmPip5CkA4e3fBRp7eo9onDYfVnba547uts ILKbIq3qp9zI6fTD6U4PKWe/MGIywzuejFCyVpze29LPDSFSPeDiHqoJdYzfKPMVD62T49c0TfjamCRSpjHhoeg= 'hello word'

true
```