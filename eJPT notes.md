eLearnSecurity Junior Penetration Tester/eJPT | INE = eLearnSecurity lol
<br> eJPT Training OFC - https://my.ine.com/
<br> This guy's notes - https://github.com/saran-gintoki/eJPT-Notes/
<br> https://www.kali.org/get-kali/#kali-installer-images

# 1 - Assessment Methodologies - Information Gathering
## Passive Information Gathering
### Website Recon & Footprinting
Identifying the scope of your test can be done via passive/active reconnaissance  
<br> whatis [Command] | gives a short description of a command
<br> host website.com | Does a DNS Lookup 

**robots.txt and sitemap.xml**
<br> A robots.txt file contains a list of directories that AREN'T indexed by search engines
<br> Example: https://hackersploit.org/robots.txt
<br> A sitemap.xml file contains a list of directories that ARE indexed by search engines
<br> Example: https://hackersploit.org/sitemap.xml 
<br> Alts: author-sitemap, post-sitemap, page-sitemap, category-sitemap (some may have more info)

**Tools / web technology identifiers**
<br> Wappalyzer | Firefox add-on cloud-based tool that identifies the technologies used to build websites. 
<br> Builtwith | Firefox add-on that does the same thing
<br> whatweb | Kali Tool/Command that does same thing
<br> Httrack | Firefox Add-on Website copier that downloads websites to a local directory

### Whois enumeration
<br> whois website.com | Does enumeration on website and finds overall info
<br> The who.is website also exists
<br> zonetransfer.me -- teaches about domain

### Website Footprinting With Netcraft
<br> netcraft | used to find out what technologies are used by a website https://sitereport.netcraft.com/

### DNS Recon or DNS footprinting
<br> dnsrecon is a Kali tool for dns footprinting
<br> dnsrecon -d website.com | specifies domain name and shows info like records 
<br> The dnsdumpster.com website gives better visual output when typing domains  
<br> dnsenum is a Kali tool that performs zonetransfers as well.
<br> sudo dnsenum —enum -f “/usr/share/dnsenum/dns.txt” salesforce.com

### wafw00f
<br> wafw00f is a Web Application Firewall Fingerprinting Toolkit
<br> wafw00f website.com | Checks the WAF protection on a website
<br> wafw00f -l | Shows a list of WAFs that can be detected by wafw00f (enable security - github)

### Sublist3r
<br> Install: sudo apt install sublist3r
<br> Sublist3r is used to perform a subdomain brute force or enumeration. | https://github.com/aboul3la/Sublist3r
<br> sublist3r -d website.com | Runs a search on all search engines
<br> sublist3r -d website.com -e google,yahoo | Does only google and yahoo (can also do netcraft and dnsdumper)

dig website.com | Kali tool that's same as host but more raw/detailed and can perform zone transfer
fierce | Kail tool that's a DNS scanner to help locate non-contiguous IP space and hostnames against specified domains.
nslookup website.com | same as host (maybe)

/etc/hosts file consists of the ip and domain names  
usr/share/dnsenum/dns.txt has a list of dns names to bruteforce

Google dorking or Google hacking is a technique using sophisticated search queries to uncover information on the internet not easily accessible through typical search queries  
waybackmachine  
google hacking database  
theHarvester  
spyse - search engine  
haveibeenpwned.com 

# SUB-OBJECTIIVES
## Locate endpoints on a network 
## Identify open ports and services on a target 
## Identify operating system of a target 
## Extract company information from public sources 
## Gather email addresses from public sources 
## Gather technical information from public sources 
## Identify vulnerabilities in services 
## Evaluate information and criticality or impact of vulnerabilities

The Whois lookup utility can be used to identify the nameservers of a particular domain.

## Footprinting and Scanning
watch network traffic  
ARP resolves ip to mac  
<br> arp-scan -I interface -g  
<br> ICMP is for ping and traceroute 
<br> fping -I interface -f file.txt -a

netdiscover -i interface -r ippaddrrange

tftp [IP Address] port - tftp (udp) based file transfer protocol

zenmap is a tool (GUI) for host discovery
nmap -sn [ipaddressrange] allows host discovery  too
nmap -p 21 --script vuln [IP Address] runs a basic vuln scan
nmap -sV --script=banner [IP Address] grabs banners of the services  
nmap -T4 -PA -sC -sV -p 1-1000 [IP Address] -oX outputfile
nmap scripts can be found in - **/usr/share/nmap/scripts/**  
Learn more about nmap here - nmap.org/book/

Locate endpoints on a network
Identify open ports and services on a target
Identify operating system of a target
Extract company information from public sources
Gather email addresses from public sources
Gather technical information from public sources
Identify vulnerabilities in services
Evaluate information and criticality or impact of vulnerabilities
## Servers and Services
SMB and NetBIOS | https://docs.google.com/document/d/1gglw7abLVa7j5hQU57yIGvac4BcUm54d9P3MwrSSpKg/edit?tab=t.0#heading=h.x90mu8vztl7s

IPC - null sessions

net use - command in windows, Connects a computer to or disconnects a computer from a shared resource, or displays information about computer connections.  
example --> net use * /delete - to delete the network share we have connected  
net use z: \ipaddr\C$ passwd /user:username - here z: denotes the name of drive you want

**nmap scripts for SMB --**  {smb-security-mode, smb-enum-sessions,smb-enum-shares,smb-enum-users,smb-server-stats,smb-enum-domains,smb-enum-groups,smb-enum-services,(smb-enum-shares,smb-ls), smb-protocols, smb-os-discovery}

nmap -p445 --script {scriptname} ipaddr  
nmap -p445 --script smb-enum-sessions --script-args smbusername=usesrname,smbpassword=password ipaddr

smbmap tool
smbmap -u username -p 'password' -d . -H [ipaddress] lists the shares
smbmap -u username -p 'password' -H [ipaddress] -x 'ipconfig' executes a command
smbmap -u username -p 'password' -H [ipaddress] -L lists the contents/drive
smbmap -u username -p 'password' -H [ipaddress] -r 'C$' reads the content of C drive
smbmap -u username -p 'password' -H [ipaddress] --upload '/path/file' 'C$\file' uploads file
smbmap -u username -p 'password' -H [ipaddress] --download 'C$\file' downloads file

**other tools for enumeration --**

- metasploit - scanner/smb/smb_version, scanner/smb/smb2, scanner/smb/smb_enumshares, scanner/smb/smb_enumusers, scanner/smb/smb_login, scanner/smb/pipe_auditor
- nmblookup -A ipaddr (in the output if there is a 20 that means theres a server we can connect to)
- smbclient -L ippaddr -N
- smbclient -L 1 \\ipaddr\ -U admin
- smbclient \\ipaddr\sharename -U admin
- smbclient //ipaddr/sharename -N -- to connect
- rpcclient -U ''"" -N ipaddr -- to see if guest login is enabled
- enum4linux {args} ipaddr - args {-o,-U}
- enum4linux -u username -p password -U ipaddr

scanner/smb/smb_enumusers - to enumerate smb users (metasploit)

login bruteforcing  
metasploit - scanner/smb/smb_login  
hydra - hydra -l username -P file.txt ipaddr smb

### FTP
- ftp [IP]
- hydra -L usernamelist -P passwordlist ipaddr ftp
- nmap ipaddr --script ftp-brute --script-args userdb=file -p 21

 *to check for anonymous login* -
        nmap ipaddr -p 21 --script ftp-anon
- metasploit - auxiliaryscanner/ftp/ftp-version, auxiliary/scanner/ftp/ftp_login, auxiliary/scanner/ftp/anonymous

### SSH Commands
- ssh root@ipaddr
- nc ipaddr 22
- nmap ipaddr -p 22 --script ssh2-enum-algos
- nmap ipaddr -p 22 --script ssh-hostkey --script-args ssh-hostkey=full
- nmap ipaddr -p 22 --script ssh-auth-methods --script-args="ssh.user=student" --- or try ssh.user=admin
- hydra -l username -P passwordlist ipaddr ssh
- nmap ipaddr -p 22 --script ssh-brute --script-args userdb=usernamefile
- metasploit -- auxiliary/scanner/ssh/ssh_login, auxiliary/scanner/ssh/ssh_version, auxiliary/scanner/ssh/ssh_enumusers

### HTTP
- whatweb ippaddr
- http ipaddr
- dirb http://ipaddr
- nmap ippaddr -p 80 --script {http-enum, http-headers,http-methods}
- nmap --script http-methods --script-args http-methods.url-path=/webdav/ ipaddr
- nmap --script http-webdav-scan --script-args http-methods.url-path=/webdav/ ipaddr
- nmap ipaddr -p 80 -sV -script banner
- metasploit -- scanner/http/http_version, scanner/http/brute_dirs, scanner/http/http_header, scanner/http/robots_txt, scanner/http/dir_scanner, scanner/http/files_dir, scanner/http/http_login, scanner/http/apache_userdir_enum,
- curl ippaddr,
- wget 'http://ipaddr/index'
- browsh, lynx - to view the website (old tools)
- robots.txt

### SQL 3306

- mysql -h ipaddr -u username
- select load_file("/etc/shadow"); -- in mysql

- nmap scripts -- mysql-empty-password, mysql-info, mysql-users, mysql-databases, mysql-variables, mysql-audit, mysql-dump-hashes,
example -
  nmap --script=mysql-variables --script-args="mysqluser='root',mysqlpass=''" -p 3306 ipaddr

- **bruteforce login using hydra** - hydra -l root -P passwordfile ipaddr mysql

mysql commands - show databases; use dbname; UPDATE wp_users SET user_pass = MD5('password123') WHERE user_login = 'admin';

**MS-SQL**
- *nmap scripts* -- ms-sql-info, ms-sql-ntlm-info, ms-sql-brute, ms-sql-empty-password, ms-sql-query -- *to run a query*, ms-sql-dump-hashes, ms-sql-xp-cmdshell,

nmap -p 1433 --script ms-sql-brute --script-args userdb=/root/Desktop/wordlist/common_users.txt,passdb=/root/Desktop/wordlist/100-common-passwords.txt ipaddr
nmap -p 1433 --script ms-sql-query --script-args  mssql.username=admin,mssql.password=anamaria,ms-sql-query.query="SELECT * FROM master..syslogins" ipaddr -oN output.txt --Extracting sysusers from MSSQL and storing the output in a file

*metasploit* -- 
**mysql** -- scanner/mysql/mysql_version, scanner/mysql/mysql_writable_dirs, scanner/mysql/mysql_hashdump, mysql-query, auxiliary/scanner/mysql/mysql_file_enum, scanner/mysql/mysql_login, admin/mysql/mysql_enum, {admin/mysql/mysql_sql - used to run sql queries}, {scanner/mysql/mysql_schemadump - can tell what tables are there under the databases}
**mssql** -- auxilary/scanner/mssql/mssql_login, auxilary/admin/mssql/mssql_enum, auxilary/admin/mssql/mssql_enum_sql_logins, auxilary/admin/mssql/mssql_exec, auxilary/admin/mssql/mssql_enum_domain_accounts

### SMTP
metasploit - auxiliary/scanner/smtp/smtp_version, auxiliary/scanner/smtp/smtp_enum
nmap -sV -script banner 192.80.153.3

# 2 - Host and Networking Auditing

# SUB-OBJECTIIVES
## Compile information from files on target
## Enumerate network information from files on target
## Enumerate system information on target
## Gather user account information on target
## Transfer files to and from target
## Gather hash/password information from target

# 3 - Host and Network Penetration Testing

# SUB-OBJECTIIVES
## Identify and modify exploits
## Conduct exploitation with metasploit
## Demonstrate pivoting by adding a route and by port forwarding
## Conduct brute-force password attacks and hash cracking

# 4 - Web Application Penetration Testing

# SUB-OBJECTIIVES
## Identify vulnerabilities in web applications
## Locate hidden file and directories
## Conduct brute-force login attack
## Conduct web application reconnaissance
## Gobuster -u [url] -w log.txt dir
