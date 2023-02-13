Quick start
-----------

![example](https://upload.wikimedia.org/wikipedia/commons/7/78/Private_key_signing.svg)

1. Generate RSA key pair. Run the below in files directory.
   ```
   openssl genrsa -out privatekey.pem 2048
   openssl rsa -in privatekey.pem -outform PEM -pubout -out publickey.pem
   ```