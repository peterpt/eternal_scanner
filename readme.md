## ETERNAL SCANNER 2.3

Eternal scanner is an network scanner for Eternal Blue exploit CVE-2017-0144 & Eternal Romance (named pipe) CVE-2017-0145 .

# Screenshots
<img src="https://s2.postimg.cc/nxhszh0s9/eromance3.jpg" width="55%"></img>

<img src="https://s21.postimg.cc/45d8z2fmv/image.png" width="25%"></img><img src="https://s2.postimg.cc/6wywqvvhl/eromance2.jpg" width="25%"></img><img src="https://s13.postimg.cc/hsjofgyzr/image.png" width="25%"></img>

## 2.2 Version (New Implementations)
* Eternal Romance Vulnerability check (escan -er)
* <img src="https://s2.postimg.cc/iyualacih/eromance.jpg" width="50%"></img>
* Escan Database Splited Results (escan -l)
* <img src="https://s2.postimg.cc/5yijooi6h/eromance1.jpg" width="50%"></img>
# Video
* Eternal Scanner 2.0 : https://www.youtube.com/watch?v=8heVXfcywq0
* Eternal Scanner 2.2 (install & run) : https://www.youtube.com/watch?v=BS9kYs-Y64U

# Requirements
- netcat
- masscan
- metasploit-framework
- wget (To Update Eternal Scanner Directly from github)
- pip (for alternative install of python modules)
- python-crypto (Dependency for Eternal Romance check)
- python-impacket (Dependency for Eternal Romance check)
- python-pyasn1-modules (Dependency for Eternal Romance check)

# How to Install
- git clone https://github.com/peterpt/Eternal_Scanner.git
- cd eternal_scanner && ./escan
- OR ./escan -h (to change scanner speed)

# Install Requirements
- apt-get install masscan metasploit-framework wget python-pip python-crypto python-impacket python-pyasn1-modules netcat

For python modules as alernative it can be used pip to install the libraries :
- pip install crypto && pip install impacket && pip install pyasn1-modules

# Notes
- Starting from version 2.0 , eternal scanner will auto install itself on your system on 1st run .
- Vulnerable scanned Ip data (vuln.txt) will be placed from now on in /usr/local/share/eternal_scanner
- Multiples sessions of escan will break the script , however , user can be scanning or checking with escan in one terminal
and use another escan session terminal to search in database by writing ( escan -l)
- Escan will run normally as before if eternal Romance dependencies are not installed , 
  however (escan -er) will not work without them .

* From Version 2.2
- Eternal Romance Vulnerability check original source : https://github.com/worawit/MS17-010

