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
openssl pkcs12 -in <digital-signature.pfx> -out private_key.pem -nodes -legacy -clcerts
openssl pkcs12 -in <digital-signature.pfx> -out ca.pem -nodes -legacy -cacerts
```

## Bundle with New Password

```bash
openssl pkcs12 -in certificado_000001011426842.pfx  -out certificates.crt -nodes -legacy
``

File with new password:

```bash
openssl pkcs12 -export -in certificates.crt  -out certificate.pfx
```


## View file

```bash
openssl pkcs12 -info -in certificate.pfx -nodes -legacy
``` 
