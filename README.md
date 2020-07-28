#Example: password from command line with "pass:"
```openssl req -new -passout pass:"Pomegranate" -subj "/CN=sample.myhost.com" -out newcsr.csr -sha512 -newkey rsa:2048
openssl rsa -in privkey.pem -passin pass:'Pomegranate' | head -n2```
