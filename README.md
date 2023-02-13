Quick start
-----------

![example](https://en.wikipedia.org/wiki/Digital_signature#/media/File:Private_key_signing.svg)

1. Generate RSA key pair. Run the below in files directory.
   ```
   openssl genrsa -out privatekey.pem 2048
   openssl rsa -in privatekey.pem -outform PEM -pubout -out publickey.pem
   ```