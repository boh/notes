### Burp Suite extensions

* [list of awesome burp extensions](https://github.com/snoopysecurity/awesome-burp-extensions)
* [AutoRepeater](https://github.com/nccgroup/AutoRepeater)
  * [Burp Suite Pro real-life tips & tricks: Authorization testing](https://mzet-.github.io/2019/07/21/burp-suite-pro-rltandt-authorization-testing.html) 
* [SQLi-Query-Tampering](https://github.com/xer0days/SQLi-Query-Tampering)
* [Quoted-printable-Parser](https://github.com/Hxzeroone/quoted-printable-Parser)
* [BurpBounty](https://github.com/wagiro/BurpBounty)
* [BurpSuite_403Bypasser](https://github.com/sting8k/BurpSuite_403Bypasser)
* [burpBridge](https://github.com/merlinxcy/burpBridge)
* [Python2Intruder](https://github.com/Leoid/Python2Intruder)
* [BurpSuiteAutoCompletion](https://github.com/Static-Flow/BurpSuiteAutoCompletion)
* [AuthMatrix](https://github.com/SecurityInnovation/AuthMatrix)
* [ProgressBurp - Track vulnerability assessment](https://github.com/dariusztytko/progress-burp)

### Burp Suite Collaborator

* [Custom Burp Collaborator server](https://portswigger.net/burp/documentation/collaborator/deploying#add-custom-http-content)

### parsing html from commandline
* [pup](https://github.com/ericchiang/pup)

## cheatsheets, checklists

* [Web-Application-Pentest-Checklist mindmap](https://github.com/iamthefrogy/)
* [OWASP Web Security Guide](https://github.com/OWASP/wstg)
* [BountyTips](https://github.com/r0eXpeR/BountyTips)
* [WAF IDS evasion techniques](https://blog.0xffff.info/2021/07/24/a-guide-to-non-conventional-waf-ids-evasion-techniques/)
* [OWASP www-project-automated-threats-to-web-applications](https://owasp.org/www-project-automated-threats-to-web-applications/)
* [List of SourceCodeReview links](https://github.com/rahulbhichher/SourceCodeReview)
* [Great web checklist for different types of pentests](https://pentestbook.six2dez.com/others/web-checklist)
* [Advanced-SQL-Injection-Cheatsheet](https://github.com/kleiton0x00/Advanced-SQL-Injection-Cheatsheet)

## Proxies

* [weird proxies attack scenarios](https://github.com/GrrrDog/weird_proxies)
* [h2csmuggler](https://github.com/BishopFox/h2csmuggler)

### JWT
* [jwt_tool](https://github.com/ticarpi/jwt_tool)

### SSL
* [SSL testing with openssl](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)
* [jwtXploiter](https://github.com/DontPanicO/jwtXploiter)

### IDOR
* [finding-more-idors-tips-and-tricks](https://www.aon.com/cyber-solutions/aon_cyber_labs/finding-more-idors-tips-and-tricks/)

### REQUEST SMUGGLING
* [request_smuggler in rust](https://github.com/Sh1Yo/request_smuggler)

### E-mail
* [user@abc123.burpcollaborator.net](https://medium.com/@d0nut/piercing-the-veal-short-stories-to-read-with-friends-4aa86d606fc5)
* [Bypassing Email Filter which leads to SQL Injection](https://medium.com/@dimazarno/bypassing-email-filter-which-leads-to-sql-injection-e57bcbfc6b17)

### Recon/Hunting

* [Dynamic Infrastracture](https://github.com/pry0cc/axiom)
* [DNS recon](https://github.com/Findomain/Findomain)
* [https://recon.dev](https://recon.dev)
* [http://securitytrails.com/](http://securitytrails.com/)
* [reconftw](https://github.com/six2dez/reconftw)
* [webstor](https://github.com/RossGeerlings/webstor)

* [How to hunt for bugs](https://github.com/KathanP19/HowToHunt)
* [Recon via bash scripts](https://github.com/harsh-bothra/Bheem)
* [Recon framework](https://github.com/j3ssie/Osmedeus)
* [Recon automation](https://github.com/hackerspider1/EchoPwn)
* [Hunting shortened URL](https://github.com/utkusen/urlhunter)
* [OSINT tools for domain recon](https://medium.com/@dalvikbytecode/top-10-osint-tools-to-help-you-do-recon-a-domain-53d3af8b1ad2)
* [OSINT geo ip](https://medium.com/@ipdata_co/what-is-the-best-commercial-ip-geolocation-api-d8195cda7027#9854)
* [IP behind Cloudflare](https://github.com/christophetd/CloudFlair)

![urlhunter](https://camo.githubusercontent.com/bf01c1974b093eb78cc23cc49c0439579c42f3dd1d829dbef10aa4856f8864ff/68747470733a2f2f692e696d6775722e636f6d2f4a32437276664d2e706e67)

### Little hacks
* [tomnomnom - webpaste](https://github.com/tomnomnom/hacks/tree/master/webpaste/extension) - see tomnomnom's nahamsec conf talk on creating wordlists 

### Finding links

Find api links in subdomains, or how to find a simple SSRF in five minutes in a big company

```
assetfinder --subs-only http://target.com | waybackurls | grep "?url="
```

### Bounty Tips

* ssrf + don't forget to add additional headers like X-Remote-IP, X-Forwarded-For, X-Real-IP etc to 127.0.0.1

```
for i in $(cat list); do curl "https://$i" --request-target http://burpcollaborator/ -v -k --path-as-is --max-time 2 ; done
```

```
Account takeover with JSON

{"password":"1234",token="123"} -> 200 OK

{"password":"1234","email":"victm@gm.com","token="123"} -> 200 OK

Hidden email add
```

[KingOfBugBountyTips](https://github.com/KingOfBugbounty/KingOfBugBountyTips)

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

### URL redirection

thanks `https://github.com/ptswarm/ptswarm-twitter/blob/main/2020-11-30-open-redirect-params.txt`

```
/[redirect]
?targetOrigin=[redirect]
?fallback=[redirect]
?query=[redirect]
?redirection_url=[redirect]
?next=[redirect]
?ref_url=[redirect]
?state=[redirect]
?l=[redirect]
?redirect_uri=[redirect]
?forum_reg=[redirect]
?return_to=[redirect]
?redirect_url=[redirect]
?return_url=[redirect]
?host=[redirect]
?url=[redirect]
?redirectto=[redirect]
?return=[redirect]
?prejoin_data=[redirect]
?callback_url=[redirect]
?path=[redirect]
?authorize_callback=[redirect]
?email=[redirect]
?origin=[redirect]
?continue=[redirect]
?domain_name=[redirect]
?redir=[redirect]
?wp_http_referer=[redirect]
?endpoint=[redirect]
?shop=[redirect]
?qpt_question_url=[redirect]
?checkout_url=[redirect]
?ref_url=[redirect]
?redirect_to=[redirect]
?succUrl=[redirect]
?file=[redirect]
?link=[redirect]
?referrer=[redirect]
?recipient=[redirect]
?redirect=[redirect]
?u=[redirect]
?hostname=[redirect]
?returnTo=[redirect]
?return_path=[redirect]
?image=[redirect]
?requestTokenAndRedirect=[redirect]
?retURL=[redirect]
?next_url=[redirect]
```

### FUZZ

* [fuzz wordlist](https://github.com/Bo0oM/fuzz.txt)

### JAVASCRIPT

* [JavaSecurity checklist](https://github.com/dschadow/JavaSecurity)

### tuts

* [Microsoft Web-Dev-For-Beginners](https://github.com/microsoft/Web-Dev-For-Beginners)
* [token manipulation](https://twelvesec.com/2017/05/05/authorization-token-manipulation/)

### scan
* [jaeles The Swiss Army knife for automated Web Application Testing](https://github.com/jaeles-project/jaeles)
* [jaeles-signatures](https://github.com/jaeles-project/jaeles-signatures)
* [parameter pollution scanner - plution](https://github.com/raverrr/plution)
* [jspanda - parameter pollution scanner](https://github.com/RedSection/jspanda)
* [RMI scanning](https://github.com/qtc-de/remote-method-guesser)

### api
* [graphql explorer](https://github.com/dolevf/graphw00f)
* (API pentest mindmap)[https://dsopas.github.io/MindAPI/play/]

### ctfs and reports
* [[H1-2006 2020] I made the CEO's bounty payment!](https://hackerone.com/reports/887816)
* [[H1-2006 2020] H1-2006 CTF Writeup](https://hackerone.com/reports/887611)
* [H1 How hackers saved christmas](https://hackerone.com/reports/1069335)
