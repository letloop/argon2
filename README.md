# `(import (letloop argon2))`

## `(argon2id salt password)` `bytevector?` `bytevector?` → `bytevector?`

As of available hardware in 2023, given the bytevectors `SALT` and
`PASSWORD` generate a strong key derivation bytevector output.

## `(argon2id-encode salt password)` `bytevector?` `bytevector?` → `bytevector?`

Same as above `argon2id` but include the parameters required to verify
the password with `argon2id-verify`.

## `(argon2id-verify password-encoded password)` `bytevector?` `bytevector?` → `boolean?`

Verifiy the bytevector `PASSWORD-ENCODED` produced by
`argon2id-encode` against the bytevector `PASSWORD`.


