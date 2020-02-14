- [ ] Find ANS and Ip ranges
```
cat /root/Desktop/prober/files/GeoIPASNum2.zip |gunzip | cut -d"," -f3 | sed 's/"//g' | sort -u | grep -i COMPANY_NAME

whois -h whois.radb.net -- '-i origin  ' | grep -Eo "([0-9.]+){4}/[0-9]+"


if
$whois company.com | grep OrigenAS

else
$nslookup company.com 
Get ip= 192.168.69.58
$whois 192.168.69.58| grep OrigenAS
Now Go to http://bgp.he.net/AS13335

```


- [ ] Shodan
```
product: MongoDB
Boolean operators: + - | &
after:dd/mm/yyyy			filtes results by data
country:US				filters results by two letter country code
hostname:google.com or .eud		filters results by specified text in the hostname or domain
net: Subnet or Ip Subset		filter results by a specific IP range or subnet
os:linux,Windows			search for specific operating systems
port:80,443				narrow the search for specific services
ssl: 					SSl enabled [yes|no]


Examples:
apache Country:CH 				Finds all the apache server in Switzerland
apache 2.2.3 hostname:.gov.in			All the India Government Website Running on apache 2.2.3
iis-5.0 hostname:.edu
"default password" 				Search for header with text default password in it
"iis/4.0"
"iis/1.0"
```


- [ ] Github Dorks

```
using github
trufflehog http://www.github.com/invis/jshjsd.git
“badoo.com” API_key
“badoo.com” secret_key
“badoo.com” aws_key
“badoo.com” Password 
“badoo.com” FTP
“badoo.com” login 
“badoo.com” github_token 
"badoo.com" password
"badoo.com" dev
"api.badoo.com"

```

- [ ] HTTP method Testing

```
$perl davtest.pl -url http://mdsec.net/public -directory 1 -move -quite 
SpiderInBurp-->GetSomeFolders-->Options Http method --> Check Respose
```


- [ ] Google Dorks

```
site: site.com inurl:login,register,upload,logout,redirect,redir,goto,admin
site: site.com inurl:&
site: site.com ext:php,asp,aspx,jsp,jspa,txt,swf
site:paypal.com -www.paypal.com -www.sandbox
site:paypal.com filetype:txt
intitle:"index of /" Parent Directory site:yoursitehere.com
intitle:"Index of /admin" site:yoursitehere.com
intitle:"Index of /password" site:yoursitehere.com
intitle:"Index of /" passwd site:yoursitehere.com
intitle:"Index of /" .htaccess site:yoursitehere.com
Intitle: "login" "admin" site:yoursitehere.com
inurl:login site:yoursitehere.com
filetype:txt site:yoursitehere.com
filetype:xml site:yoursitehere.com
filetype:inf site:yoursitehere.com
filetype:ini site:yoursitehere.com
filetype:xls csv site:yoursitehere.com
```

- [ ] Subdomains Enumration

```
-Amass
-Massdns
-Online Endpoints
-GoBuster

Massdns
=====
./massdns/bin/massdns -r massdns/lists/resolvers.txt -t A -o S $PWD/massdns/subdomains.txt -w livehosts_temp.txt		---	Will save the Live Hosts in livehosts.txt
sed 's/A.*//' livehosts_temp.txt | sed 's/CN.*//' | sed 's/\..$//' >live_hosts.txt						---	Filter Live Hosts



```


- [ ] Masscaning

```
$nslookup website.com
>>Take Ip address
$masscan -p22-65534 125.256.214.2 --rate 1000
>>copy Open Ports {80,443,22,21,8080,3148,3124,4444,8443}
$nmap -sS -p80,443,22,21,8080,3148,3124,4444,8443 125.256.214.2 -Pn -n 
>>Visit every port to see any admin panels or logins

```

- [ ] Nmap

```

```


- [ ] Content Discovery

```

GitFinder
=========

cd /imxx/Gitools
python3 gitfinder.py -i subs.txt
```
