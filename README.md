### NAME
   makecsr

### SYNOPSIS
  Generating CSR (Certificate Signing Requsts) from live sites.

### USAGE
  makecsr [ -u url |  -h ]

### EXAMPLE
  makesr -u example.com

  makecsr -u https://example.com:44321

  makecsr -u https://example.com
### FUNCTION

  It will examine a current live certificate, and construct openssl comamnds
  and generate a key, csr, and cnf file if required.

### Environment

   python3 -m venv ~/.venv/makecsr/bin/activate
   pip -r requirements.txt


### tidy
   sh tidy.sh 
   - will remove *.csr *.cnf *.key files so be careful

### Sample Output:
   `./makecsr -u google.com`

```
[-] You have requested to look at the  current certificate https://aardvark.herts.ac.uk:443
	The existing certificate has Altnames
[-] You can generate the certificate request (CSR) and a new key to replace this like this:
		openssl req -new -nodes -newkey rsa:4096 -keyout aardvark.key -out aardvark.csr -config aardvark.cnf  -subj "/C=GB/L=Hatfield/O=University of Hertfordshire/CN=www.aardvark.herts.ac.uk"
[-] Generating locally:
		aardvark.key  and aardvark.csr
[-] The openssl.cnf file: (generated aardvark.cnf)

#----cut-and-paste-to-a-file openssl.cnf
[req]
default_bits = 4096
prompt = no
default_md = sha256
req_extensions = req_ext
distinguished_name = dn

[dn]

[ req_ext ]
subjectAltName = @alt_names

[alt_names]

DNS.1 = www.aardvark.herts.ac.uk
DNS.2 = aardvark.herts.ac.uk 
```

