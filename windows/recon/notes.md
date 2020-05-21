### finding DFS shares

```
AD
Get-ADObject -filter * -SearchBase "CN=Dfs-Configuration,CN=System,DC=a,DC=b" | select name

ADSI
$s=[adsisearcher]'(name=*)'; $s.SearchRoot = [adsi]"LDAP://CN=Dfs-Configuration,CN=System,dc=a,dc=b"; $s.FindAll() | % {$_.properties.name}
```
