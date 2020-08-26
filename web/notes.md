### Burp Suite extensions

* [SQLi-Query-Tampering](https://github.com/xer0days/SQLi-Query-Tampering)
* [Quoted-printable-Parser](https://github.com/Hxzeroone/quoted-printable-Parser)

### Finding links

Find api links in subdomains, or how to find a simple SSRF in five minutes in a big company

assetfinder --subs-only http://target.com | waybackurls | grep "?url="

### Bounty Tips
```
grep "="  .txt| qsreplace "' OR '1" | httpx -silent -store-response-dir output -threads 100 | grep -q -rn "syntax\|mysql" output 2>/dev/null && \printf "TARGET \033[0;32mCould Be Exploitable\e[m\n" || printf "TARGET \033[0;31mNot Vulnerable\e[m\n"
```
