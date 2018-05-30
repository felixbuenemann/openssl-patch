# openssl-patch

## OpenSSL Equal Preference Patch

[Test Page - (TLS 1.3 draft 23, 28)](https://ssl.hakase.io/)

**If you link site to a browser that supports draft 23 or 28, you'll see a TLS 1.3 message.**

**Latest patch : openssl-equal-pre8.patch, openssl-equal-pre8_ciphers.patch**

[View Tree (OpenSSL)](https://github.com/openssl/openssl/tree/f3a246c63eefc1e5da434df5dc7f48795a12c38b)

[Original source](https://boringssl.googlesource.com/boringssl/+/858a88daf27975f67d9f63e18f95645be2886bfb%5E%21) by [BoringSSL](https://github.com/google/boringssl) & [CentminMod](https://centminmod.com/)

OpenSSL 1.1.0h patch is [here](https://gitlab.com/buik/openssl/blob/openssl-patch/openssl-1.1/OpenSSL1.1h-equal-preference-cipher-groups.patch)

## pre8 File

openssl-equal-pre8.patch : TLS 1.3 cipher settings can not be changed on nginx.

openssl-equal-pre8_ciphers.patch : TLS 1.3 cipher settings can be changed on nginx. (ex. TLS13+AESGCM+AES128:TLS13+AESGCM+AES256)

The _ciphers patch file is a temporary change to the TLS 1.3 configuration.

## nginx Configuration (ssl_ciphers)

### OpenSSL-1.1.1-pre2 ciphers (draft 23)
`[TLS13-AES-128-GCM-SHA256|TLS13-CHACHA20-POLY1305-SHA256]:TLS13-AES-256-GCM-SHA384:[EECDH+ECDSA+AESGCM+AES128|EECDH+ECDSA+CHACHA20]:EECDH+ECDSA+AESGCM+AES256:EECDH+ECDSA+AES128+SHA:EECDH+ECDSA+AES256+SHA:[EECDH+aRSA+AESGCM+AES128|EECDH+aRSA+CHACHA20]:EECDH+aRSA+AESGCM+AES256:EECDH+aRSA+AES128+SHA:EECDH+aRSA+AES256+SHA:RSA+AES128+SHA:RSA+AES256+SHA:RSA+3DES`

### OpenSSL-1.1.1-pre6~pre7 ciphers (draft 26 ~ 28)
`[EECDH+ECDSA+AESGCM+AES128|EECDH+ECDSA+CHACHA20]:EECDH+ECDSA+AESGCM+AES256:EECDH+ECDSA+AES128+SHA:EECDH+ECDSA+AES256+SHA:[EECDH+aRSA+AESGCM+AES128|EECDH+aRSA+CHACHA20]:EECDH+aRSA+AESGCM+AES256:EECDH+aRSA+AES128+SHA:EECDH+aRSA+AES256+SHA:RSA+AES128+SHA:RSA+AES256+SHA:RSA+3DES`

### OpenSSL-1.1.1-pre7-draft23_28, pre8 ciphers (draft 23, 28)
`[EECDH+ECDSA+AESGCM+AES128|EECDH+ECDSA+CHACHA20]:EECDH+ECDSA+AESGCM+AES256:EECDH+ECDSA+AES128+SHA:EECDH+ECDSA+AES256+SHA:[EECDH+aRSA+AESGCM+AES128|EECDH+aRSA+CHACHA20]:EECDH+aRSA+AESGCM+AES256:EECDH+aRSA+AES128+SHA:EECDH+aRSA+AES256+SHA`

### OpenSSL-1.1.1-pre8_ciphers ciphers (draft 23, 28)
`[TLS13+AESGCM+AES128|TLS13+AESGCM+AES256|TLS13+CHACHA20]:[EECDH+ECDSA+AESGCM+AES128|EECDH+ECDSA+CHACHA20]:EECDH+ECDSA+AESGCM+AES256:EECDH+ECDSA+AES128+SHA:EECDH+ECDSA+AES256+SHA:[EECDH+aRSA+AESGCM+AES128|EECDH+aRSA+CHACHA20]:EECDH+aRSA+AESGCM+AES256:EECDH+aRSA+AES128+SHA:EECDH+aRSA+AES256+SHA`
