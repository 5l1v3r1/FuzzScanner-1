# [中文介绍](https://github.com/Yuanlin-He/HYLScanner/blob/master/README-zh.md)

# FuzzScanner

## Introduction
[![PyPI version](https://img.shields.io/badge/python-3-blue.svg)](https://www.python.org/)  [![License](https://img.shields.io/badge/license-GPLv2-red.svg)](https://raw.githubusercontent.com/sqlmapproject/sqlmap/master/LICENSE) 

 If you find any program error,you can send email: MTM5ODk4MDUxNkBxcS5jb20=  to me. 

**Welcome star** 

## Function
- Subdomain scan
- Open port scan
- Alive detect
- Waf detect 
- Sql inject detect
- Information disclosure detect
## Usage
use `python FuzzScanner.py -h` to see help
```
usage: python FuzzScanner.py [-h] [-d] [-a] [-s] [-p] [-w] [-sd] [-i] [-t] [-o]

optional arguments:
  -h, --help        show this help message and exit
  -d , --domain     Select the domain or ip
  -a, --alive       Alive detection
  -s, --sql         Sql inject detection
  -p, --port        Open port detection
  -w, --waf         Waf name detection
  -sd, --subdomain  subdomain fuzz detection
  -i, --id          Information disclosure detection
  -t , --time       subdomains timeout setting
  -o , --out        subdomains result file
```
## Details&Nodes
#### Subdomain scan
```
python FuzzScanner.py -sd -d qq.com -o result.txt
```
If no output file is specified, the program will automatically generate subdomain.txt in this directory to store the subdomain name.

If no dictionary file is specified, this program will automatically search for domain.csv in this directory.

Note: Beware of excessive card dictionary

If no timeout is specified, the program automatically sets one second


#### Open port scan
```
python FuzzScanner.py -p -d www.qq.com
```
#### Alive detect
```
python FuzzScanner.py -a -d 202.202.43.125
```
Support ICMP / SYN / ACK scanning
#### Waf detect 
```
python FuzzScanner.py -w -d www.qq.com
```
poc.py is the waf fingerprint library

Comparing ordinary URL status codes with malicious request status codes to detect if their waf is anti-scanning
#### Sql inject detect 
```
python FuzzScanner.py -s -d http://43.247.91.228:84/Less-1/?id=1
```
Note: 
**Please find the injection point by yourself or scan the injection point with awvs**

#### Information disclosure detect
```
python FuzzScanner.py -i -d http://web.jarvisoj.com:32798/
```
Support detection of git / svn, bak, swp and other backup file leaks

If the php file name is not in php-name.csv, please manually add the php file name you found to php-name.csv

