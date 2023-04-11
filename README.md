# `(import (letloop argon2))`

> Argon2 is award winning password hasher.

It is useful backend side to implement user accounts, and verify that
as user claiming to be someone can provide an input that is same as
the one we already know about, that input is the password. The trick
is that, the backend does not store the password as it is provided, it
rely on cryptography to make it hard to guess what is the actual
password, while still being possible to make sure that it is the
correct password when it is.

For stronger scheme, look into
[letloop/htgp](https://github.com/letloop/htgp).

## `(argon2id salt password)` `bytevector?` `bytevector?` → `bytevector?`

As of available hardware in 2023, given the bytevectors `SALT` and
`PASSWORD` generate a strong key derivation bytevector output.

## `(argon2id-encode salt password)` `bytevector?` `bytevector?` → `bytevector?`

Same as above `argon2id` but include the parameters required to verify
the password with `argon2id-verify`.

## `(argon2id-verify password-encoded password)` `bytevector?` `bytevector?` → `boolean?`

Verifiy the bytevector `PASSWORD-ENCODED` produced by
`argon2id-encode` against the bytevector `PASSWORD`.


