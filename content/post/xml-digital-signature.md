---
title: "Xml Digital Signature in .NET"
date: 2022-10-22T07:29:27-03:00
Description: ""
Summary: "Extract keys from digital signature file"
Tags: [xmldsig]
Categories: [cryptography]
DisableComments: false
draft: true
---

## Extract **Private Key** and **CA Certificate** from `.psx` file

```bash
openssl pkcs12 -in <digital-signature.pfx> -out private_key.pem -node -legacy -clcerts
openssl pkcs12 -in <digital-signature.pfx> -out ca.pem -node -legacy -cacerts
```