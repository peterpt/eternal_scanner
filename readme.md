## ETERNAL SCANNER 2.0

Eternal scanner is an network scanner for Eternal Blue exploit CVE-2017-0144 .

# Screenshots
<img src="https://s24.postimg.org/guwhjz9rp/image.png" width="55%"></img>

<img src="https://s21.postimg.org/45d8z2fmv/image.png" width="25%"></img><img src="https://s11.postimg.org/5rmdqf0jn/image.png" width="25%"></img><img src="https://s4.postimg.org/jc6tbsxx9/image.png" width="25%"></img><img src="https://s13.postimg.org/hsjofgyzr/image.png" width="25%"></img>

## 2.0 Version (New Implementations)
* Autoinstalation on 1st run
<img src="https://s29.postimg.org/55f4m5653/20c.png" width="25%"></img>

* (-i Switch to scan ips directly from terminal without prompt)
<img src="https://s29.postimg.org/7k706kmdz/20a.png" width="25%"></img>

* (-i and -s switches implemented together to scan directly from terminal at some rate speed)
<img src="https://s29.postimg.org/h60kmvdjr/20b.png" width="25%"></img>

* (-c Switch to recheck current vulnerable ip list)
<img src="https://s1.postimg.org/3rywvvc0f/image.png" width="25%"></img>

* (Using the -c switch eternal scanner will create a detailed file from vulnerable ips)
<img src="https://s21.postimg.org/4xrv3vbyv/image.png" width="25%"></img>

# Requirements
- masscan
- metasploit-framework

# How to Install
- git clone https://github.com/peterpt/eternal_scanner.git
- cd eternal_scanner && ./escan
- OR ./escan -h (to change scanner speed)

# Install Requirements
- apt-get install masscan metasploit-framework

# Notes
- Starting from version 2.0 , eternal scanner will auto install itself on your system on 1st run .
- Vulnerable scanned Ip data (vuln.txt) will be placed from now on in /usr/local/share/eternal_scanner