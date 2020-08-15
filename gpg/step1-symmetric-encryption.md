We start by using GPG to encrypt a file with a symmetric cipher.

As a first step we create a file named `document.txt` and add some text (*the plaintext*) to it.
This can be done in a variety of ways.

`echo "Here is the plaintext." > document.txt`{{execute}}

Alternatively you can use and editor to create or edit the files: vi, nano, ... are possible alternatives:
`vi document.txt`{{execute}}


## Symmetric Encryption

Symmetric encryption can be carried out by using the `--symmetric` flag:

`gpg --output document.gpg --symmetric document.txt`{{execute}}

The passphrase you provide is used to generate the cryptographic key used for the encryption.

Note: PGP does note delete the original file (`document.txt`) which must be explicitly deleted if you wish so.

`rm document.txt`{{execute}}

## Symmetric Decryption

The file can be decrypted by using `--decrypt` flag:

`gpg --output decrypted-document.txt --decrypt document.gpg`{{execute}}

The passphrase you provide is used to generate the cryptographic key used for the encryption.

The same passphrase you provided for encryption must be used here.

You can now check that the newly generated file (`decrypted-document.txt`) contains the same plaintext as the original one (`document.txt`).

`cat decrypted-document.txt`{{execute}}




