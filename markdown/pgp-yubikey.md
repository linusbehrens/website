---
title: PGP with 2fa usb sticks
author: "Linus Behrens"
date: 2025-07-05T16:00:00+02:00
tags: ['tech', 'security']
header: "/header/linux.jpg"
draft: true
---

```sh
gpg --expert --full-gen-key
```

- Enter `RSA`
- Enter `4096`
- Enter expiration date
- Enter user information and email
- Enter random input (mouse, keyboard) to gain entropy

Output:
```
gpg: key <keyID> marked as ultimately trusted
```

## Add authentication key (if not default)

```sh
gpg --expert --edit-key <keyID>
```

```sh
addkey
```

- Enter the `passphrase`
- Enter `8` for RSA
- Enter `S` for disabling "sign"
- Enter `E` for disabling "encrypt"
- Enter `A` for enabling "authentication"
- Enter `Q` for leaving dialoge
- Enter key size
- Enter same expiration date as before
- Enter `Y` to safe the changes

## Back pgp-Key up

```sh
gpg --export-secret-key --armor <KeyID>
```

- Store output safe

## Add pgp-keys to the YubiKey

- Insert YubiKey into a USB port

```sh
gpg --edit-key <KeyID>
```

```sh
keytocard
```

- Signature subkey:
    - Enter `keytocard`
    - Enter `Y` to continue
    - Enter `1` to move the signature subkey to a slot in the yubikey
    - Enter `key 1`
- Encryption subkey:
    - Enter `keytocard`
    - Enter `Y` to continue
    - Enter `2` to move the encryption subkey to a slot in the yubikey
    - Enter `key 1`
    - Enter `key 2`
- Authentication subkey
    - Enter `keytocard`
    - Enter `3` to move the authentication subkey to a slot in the yubikey
- Enter `quit` to leave

When asked **do not safe** your changes enabling you to copy the key to another Yubikey.

---

[article by yubikey](https://support.yubico.com/hc/en-us/articles/360013790259-Using-Your-YubiKey-with-OpenPGP)
