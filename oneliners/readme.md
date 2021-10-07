### masscan
https://captmeelo.com/pentest/2019/07/29/port-scanning.html
grep "Ports:" TARGETS.gnmap | cut -d " " -f4 | cut -d "/" -f1 | sort -n | uniq | paste -sd, > OPEN_PORTS
cat TARGETS.gnmap | grep Host | awk '{print $2,$5}' | sed 's@/.*@@' | sort -t' ' -n -k2 | awk -F' ' -v OFS=' ' '{x=$1;$1="";a[x]=a[x]","$0}END{for(x in a) print x,a[x]}' | sed 's/, /,/g' | sed 's/ ,/ /' | sort -V -k1 | cut -d " " -f1 > HOSTS
