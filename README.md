### NAME
   makecsr
### SYNOPSIS
  Generating CSR (Certificate Signing Requsts) from live sites.
### USAGE
  makecsr -u url
  makecsr -h
### EXAMPLE
  makesr -u example.com
  makecsr -u https://example.com:44321
  makecsr -u https://example.com
### FUNCTION
: It will examine a current live certificate, and construct openssl comamnds
and generate a key, csr, and cnf file if required.

### Environment
   python3 -m venv ~/.venv/makecsr/bin/activate
   pip -r requirements.txt

### tidy
   sh tidy.sh 
   - will remove *.csr *.cnf *.key files so be careful


