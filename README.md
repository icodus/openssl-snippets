password from command line with "pass:"

$ openssl req -new -passout pass:"Pomegranate" -subj "/CN=sample.myhost.com" -out newcsr.csr -sha512 -newkey rsa:2048
$ openssl rsa -in privkey.pem -passin pass:'Pomegranate' | head -n2

password from variable with "env:"

$ export MYPASS='Elderberry'
$ openssl req -new -passout env:MYPASS -subj "/CN=sample.myhost.com" -out newcsr.csr -sha512 -newkey rsa:2048
$ openssl rsa -in privkey.pem -passin pass:'Elderberry' | head -n2

password from file with "file:"

$ echo "Farkleberry" > password.txt
$ openssl req -new -passout file:password.txt -subj "/CN=sample.myhost.com" -out newcsr.csr -sha512 -newkey rsa:2048

