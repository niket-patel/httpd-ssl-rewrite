https://kb.firedaemon.com/support/solutions/articles/4000121705-firedaemon-openssl-1-1-1k-binary-distribution-for-microsoft-windows
#step-1
PS C:\software\OpenSSL\bin> openssl req -new -key server.key -out server.csr -sha256
#step-2
PS C:\software\OpenSSL\bin> openssl req -new -key server.key -out server.csr -sha256 -config C:\software\OpenSSL\ssl\openssl.cnf
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:IN
State or Province Name (full name) [Some-State]:KA
Locality Name (eg, city) []:Bengaluru
Organization Name (eg, company) [Internet Widgits Pty Ltd]:test
Organizational Unit Name (eg, section) []:fcom
Common Name (e.g. server FQDN or YOUR name) []:dev1.test.com
Email Address []:test@test.com

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:changeit
An optional company name []:test

#step-3
openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt

#step-4
update cert location in apache2/extra/httpd-ssl.confs



