### Burp Suite extensions

* [SQLi-Query-Tampering](https://github.com/xer0days/SQLi-Query-Tampering)
* [Quoted-printable-Parser](https://github.com/Hxzeroone/quoted-printable-Parser)

### Finding links

Find api links in subdomains, or how to find a simple SSRF in five minutes in a big company

assetfinder --subs-only http://target.com | waybackurls | grep "?url="
