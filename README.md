Quick start
-----------

![example](https://upload.wikimedia.org/wikipedia/commons/7/78/Private_key_signing.svg)

1. Generate RSA key pair. Run the below commands.
   ```
   openssl genrsa -out privatekey.pem 2048
   openssl rsa -in privatekey.pem -outform PEM -pubout -out publickey.pem
   ```

2. Encrypted the message "Hello Bob!" in the file message.
   ```
   openssl dgst -sha256 -sign privatekey.pem -out sign.sha256 message
   ```
   
3. The resulting binary signature file is sign.sha256, an arbitrary name. To get a readable (if base64) version of this file, the follow-up command is:
   ```
   openssl enc -base64 -in sign.sha256 -out sign.sha256.base64
   ```
   
4. The final step in this process is to verify the digital signature with the public key.
   ```
   openssl enc -base64 -d -in sign.sha256.base64 -out sign.sha256
   openssl dgst -sha256 -verify publickey.pem -signature sign.sha256 message
   ```
   The output result:
   ```
   $ openssl dgst -sha256 -verify publickey.pem -signature sign.sha256 message
   Verified OK
   ```