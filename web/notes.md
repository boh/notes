### Burp Suite extensions

* [SQLi-Query-Tampering](https://github.com/xer0days/SQLi-Query-Tampering)
* [Quoted-printable-Parser](https://github.com/Hxzeroone/quoted-printable-Parser)

### E-mail
* [user@abc123.burpcollaborator.net](https://medium.com/@d0nut/piercing-the-veal-short-stories-to-read-with-friends-4aa86d606fc5)
* [Bypassing Email Filter which leads to SQL Injection](https://medium.com/@dimazarno/bypassing-email-filter-which-leads-to-sql-injection-e57bcbfc6b17)

### Recon/Hunting

* [How to hunt for bugs](https://github.com/KathanP19/HowToHunt)

### Little hacks
* [tomnomnom - webpaste](https://github.com/tomnomnom/hacks/tree/master/webpaste/extension) - see tomnomnom's nahamsec conf talk on creating wordlists 

### Finding links

Find api links in subdomains, or how to find a simple SSRF in five minutes in a big company

```
assetfinder --subs-only http://target.com | waybackurls | grep "?url="
```

### Bounty Tips
```
grep "="  .txt| qsreplace "' OR '1" | httpx -silent -store-response-dir output -threads 100 | grep -q -rn "syntax\|mysql" output 2>/dev/null && \printf "TARGET \033[0;32mCould Be Exploitable\e[m\n" || printf "TARGET \033[0;31mNot Vulnerable\e[m\n"
```

```
subfinder -d http://tesla.com -silent | httpx -timeout 3 -threads 300 --follow-redirects -silent | xargs -I% -P10 sh -c 'hakrawler -plain -linkfinder -depth 5 -url %' | grep "tesla"
```

![dns](https://pbs.twimg.com/media/EgM0dUOXoAMeoi1?format=png&name=900x900)

```
./github-subdomains.py -t APIKEY -d http://att.com | httpx -silent | xargs -I@ -P20 sh -c 'gospider -a -s "@" -d 2' | grep -Eo "(http|https)://[^/\"].*.js+" | sed "s#\] \- #\n#g" | anew | grep "http://att.com"
```

https://github.com/gwen001/github-search

![dns](https://pbs.twimg.com/media/EgRzmv8X0AMkSja?format=png&name=small)

```
assetfinder -subs-only http://tesla.com -silent | httpx -timeout 3 -threads 300 --follow-redirects -silent | xargs -I% -P10 sh -c 'hakrawler -plain -linkfinder -depth 5 -url %' | grep "tesla"
```

```
Sometimes it returns more domains that common curl
psql -A -F , -f querycrt -h http://crt.sh -p 5432 -U guest certwatch 2>/dev/null | tr ', ' '\n' | grep twitch | anew
```

![dns](https://pbs.twimg.com/media/EgJFL0nXYAAA9WT?format=jpg&name=small)

```
chaos -d http://att.com | httpx -silent | xargs -I@ -P20 sh -c 'gospider -a -s "@" -d 2' | grep -Eo "(http|https)://[^/\"].*.js+" | sed "s#\] \- #\n#g" | anew | grep "http://att.com"
```

![dns](https://pbs.twimg.com/media/EgCFTDiXgAAM3rF?format=png&name=small)

```
New trick, using gospider and Chaos:
chaos -d http://paypal.com -bbq -filter-wildcard -http-url | xargs -I@ -P5 sh -c 'gospider -a -s "@" -d 3'
```

![dns](https://pbs.twimg.com/media/Ef9jVsxWAAA6Q2v?format=png&name=small)

```
xargs -P 500 -a pay.txt -I@ sh -c 'nc -w1 -z -v @ 443 2>/dev/null && echo @' | xargs -I@ -P10 sh -c 'gospider -a -s "https://@" -d 2 | grep -Eo "(http|https)://[^/\"].*.js+" | sed "s#\] \- #\n#g" | anew'
```

```
curl "https://recon.dev/api/search?key=apiKEY&domain=paypal.com" |jq -r '.[].rawDomains[]' | sed 's/ //g' | anew |httpx -silent | xargs -I@ gospider -d 0 -s @ -c 5 -t 100 -d 5 --blacklist jpg,jpeg,gif,css,tif,tiff,png,ttf,woff,woff2,ico,pdf,svg,txt | grep -Eo '(http|https)://[^/"]+' | anew
```

![urls](https://pbs.twimg.com/media/Ef6pfHJWkAAaAnq?format=png&name=small)

```
subfinder -d http://att.com >> domains ; assetfinder -subs-only http://att.com >> domains ; amass enum -norecursive -noalts -d http://att.com >> domains ; subjack -w domains -t 100 -timeout 30 -ssl -c /fingerprints.json -v 3 >> takeover ;
```
