# Create a Self-signed Certificate

As described in
[PSD2 Gateway Operational Guidelines for AISs and PISs](https://docs.fabrick.com/psd2/manuals/OperationalGuidelinesForTPP.pdf),
in order to make successful calls to _TEST environment_, the caller must pass an X.509 certificate in every request.

To create the X.509 certificate, you can use `openssl` as shown herein.

```bash
$ openssl req \
    -x509 -sha256 -nodes -newkey rsa:4096 -days 365 \
    -subj '/CN=localhost' \
    -keyout test-psd2gateway.fabrick.com.key \
    -out test-psd2gateway.fabrick.com.crt
```
