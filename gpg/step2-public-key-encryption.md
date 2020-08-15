##_Generating a new keypair

The command-line option `--gen-key` is used to create a new primary keypair.
`gpg --gen-key`{{execute}}

GnuPG is able to create several different types of keypairs, but a primary key must be capable of making signatures:

- Option 1 creates two RSA keypairs: a primary keypair used for making signatures and a subordinate keypair for encryption.
- Option 2 creates a DSA keypair: the primary keypair usable only for making signatures and an ElGamal subordinate keypair for encryption.
- Option 3 creates only a DSA keypair for making signatures only.
- Option 3 creates only a RSA keypair for making signatures only.

In all cases it is possible to later add additional subkeys for encryption and signing. For most users the default option is fine.

You must also choose a key size, the lifetime of the key (a key that does not expire is adequate for most users), a user ID (Real Name, Comment and Email Address).

Finally PGP needs a passphrase to protect the primary and subordinate private keys that you keep in your possession.

* There is no limit on the length of a passphrase, and it should be carefully chosen.
* From the perspective of security, the passphrase to unlock the private key is one of the weakest points in PGP.
* Ideally, the passphrase should not use words from a dictionary and should mix the case of alphabetic characters as well as use non-alphabetic characters.


## Exchanging keys

To communicate with others you must exchange public keys.

To list the keys on your public keyring use the command-line option `--list-keys`.
`gpg --list-keys`{{execute}}

##_Exporting a public key

* To send your public key to a correspondent you must first export it.
* The flag `--export` is used to do this.
* It takes an additional argument identifying the public key to export.
* Either the key ID or any part of the user ID may be used to identify the key to export.
```
`gpg --armor --export mario.rossi@gmail.com`
