zuora_ssl_python
================

## How To Use

1. Encrypt Message

```python
from ZuoraSSL import ZuoraSSL

zuoraSSL = ZuoraSSL(
    "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAt7k14Yxu1pmXqMr67Yu0QcPFbY3R+S/AKjFpoyQJtMo2oTJAoDrcKKijN/40w9KCMxYqxCNrgez996zPIl7QRPGtuqv7F6Y0hi4pSrRtm+C2spf9T5PVrpcAf0tr0vglkW+cttMmQQ1/dwNDT7zRxTlSReQvkQ1aieEGiitBkkmnI0ThhUubJCTI90u4NO5fIkWJodbxsZ0w9eEJ3IpPCGEwjOkrTQtoa0IfacdMW7nxOQEvWiUQ2Pq154sNTfVRjCZsjugl8zkCLcp8IPqJ4rkNQu8WyylPb5Rp74I6nKSuNJkLGV8DoHHOTMuT4521oksrzrYs2NOtDlC0R+Ba0wIDAQAB")
encrypted = zuoraSSL.encrypt_message("Hello I'm Your Boss")
print(encrypted)
```

2. Decrypt Signatrue

```python
from ZuoraSSL import ZuoraSSL

zuoraSSL = ZuoraSSL(
    "MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAt7k14Yxu1pmXqMr67Yu0QcPFbY3R+S/AKjFpoyQJtMo2oTJAoDrcKKijN/40w9KCMxYqxCNrgez996zPIl7QRPGtuqv7F6Y0hi4pSrRtm+C2spf9T5PVrpcAf0tr0vglkW+cttMmQQ1/dwNDT7zRxTlSReQvkQ1aieEGiitBkkmnI0ThhUubJCTI90u4NO5fIkWJodbxsZ0w9eEJ3IpPCGEwjOkrTQtoa0IfacdMW7nxOQEvWiUQ2Pq154sNTfVRjCZsjugl8zkCLcp8IPqJ4rkNQu8WyylPb5Rp74I6nKSuNJkLGV8DoHHOTMuT4521oksrzrYs2NOtDlC0R+Ba0wIDAQAB")

decrypted = zuoraSSL.decrypt_signature(
    "rxJ8Dv2G0L+5h9Z7y1f+p6DR2+SGL9ixF/qzRfzEAJ3OtLEd6POxfLgtG+0J8YDY3FuO3FpAGZotdOcQarnYMkbjkWOBNgMA9kmEZaZnEeXUuYJn5eSb0wtO3Vqh65xK6vFAeuFH/ONaeuRvN34a3mUn1p/9jw+PF1dpMBdTHFo94ezPQL0q6yP/TTKSQLEk9E+f9yRcBTW4ZbqhvwFSD8Xzi1URrr6cpkVNP+tatYFzHnBFNDzIl2ZuKU97L2Ao/DChy/mJ2hhHNtx7XzXGmXVRQnUEeXSvguwi+s9Ktb6cxmh05g5P/SEsYJymHDsdDumx0cXJD+SkkntuK1omgg==")
print(decrypted)

```

The result should be like this:
```
/hpm2samplecodejsp/callback.jsp#9#5ZUbvhzsquXKrnd0qkjdT6XkMXpTVYh2#1418192059150#4028904a49eff36e0149f43e62cb000e
```

If you want a dictionary decrypted from the signature instead of a string with '#' connected,  you can use `decrypt_signature_to_dict` method, and you will get a dictionary like below:

```
{'pageId': '4028904a49eff36e0149f43e62cb000e', 'token_signature': '5ZUbvhzsquXKrnd0qkjdT6XkMXpTVYh2', 'timestamp_signature': '1418192059150', 'url_signature': '/hpm2samplecodejsp/callback.jsp', 'tenantId': '9'}
```
