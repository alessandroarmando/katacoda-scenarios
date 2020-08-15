We start by using GPG to encrypt a file with a symmetric cipher.

As a first step we create a file named `document.txt` and add some text (*the plaintext*) to it.
This can be done in a variety of ways.

`echo "Here is the plaintext." > document.txt`{{execute}}

Alternatively you can use and editor to create or edit the files: vi, nano, ... are possible alternatives:
`vi document.txt`{{execute}}


## Symmetric Encryption

Symmetric encryption can be carried out by specifying the `--symmetric` flag:

`gpg --output document.gpg --symmetric document.txt`{{execute}}

