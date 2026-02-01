# Certificates Directory

This directory contains SSL/TLS certificates for Caddy.

## Security Notice

⚠️ **NEVER commit private keys (*.key) or certificates (*.crt) to version control!**

These files are excluded via `.gitignore` for security reasons.

## Files

- `openssl.cnf` - OpenSSL configuration template (tracked in git)
- `selfsigned.crt` - Self-signed certificate (NOT tracked, generate locally)
- `selfsigned.key` - Private key (NOT tracked, generate locally)

## Generate Self-Signed Certificate

```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
  -keyout selfsigned.key \
  -out selfsigned.crt \
  -config openssl.cnf
```

## For Production

Replace self-signed certificates with certificates from a trusted CA (Let's Encrypt, etc.)
