## ETERNAL SCANNER 2.1

Eternal scanner is an network scanner for Eternal Blue exploit CVE-2017-0144 .

# Screenshots
<img src="https://s1.postimg.org/7b7lfgw95r/image.jpg" width="55%"></img>

<img src="https://s21.postimg.org/45d8z2fmv/image.png" width="25%"></img><img src="https://s11.postimg.org/5rmdqf0jn/image.png" width="25%"></img><img src="https://s1.postimg.org/20bbkhijrz/image.jpg" width="25%"></img><img src="https://s13.postimg.org/hsjofgyzr/image.png" width="25%"></img>

## 2.1 Version (New Implementations)
* Search in database reviewed (escan -l)
* <img src="https://s1.postimg.org/6qtbx2agnj/image.jpg" width="50%"></img>

* Source Code Reviewed from 1272 to 774 lines

# Video
* Eternal Scanner 2.0 : https://www.youtube.com/watch?v=8heVXfcywq0

* Eternal Scanner 2.2 (Quick Peak) https://www.youtube.com/watch?v=Tbh94jnd5aw

# Requirements
- masscan
- metasploit-framework
- wget

# How to Install
- git clone https://github.com/peterpt/eternal_scanner.git
- cd eternal_scanner && ./escan
- OR ./escan -h (to change scanner speed)

# Install Requirements
- apt-get install masscan metasploit-framework

# Notes
- Starting from version 2.0 , eternal scanner will auto install itself on your system on 1st run .
- Vulnerable scanned Ip data (vuln.txt) will be placed from now on in /usr/local/share/eternal_scanner
