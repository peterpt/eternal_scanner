## ETERNAL SCANNER (How To Use)

* Disclaimer
- Eternal Scanner does not exploit any IP , Eternal Scanner only checks if IP or IP Range is exploitable with CVE-2017-0144/0145
- CVE-2017-0144 Exploit Information : https://www.cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0144
- CVE-2017-0145 Exploit Information : https://www.cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0145
- Scanning an IP or an IP Range that is not under your maintenance is forbidden in many countries and it goes against the law .
- Eternal Scanner was build for network System administrators in order to check if any station is vulnerable to this exploit .


## How to use

* Switches

-Running in current eternal_scanner directory over terminal :
- "escan -h"  will popup the available switches
- "escan -s 1000" will setup the scanner rate speed to 1000pk/s 
- Rate speed :
Eternal Scanner allows the -s switch to accept values from 100pk/s to 100000000pk/s where "100" should be used for low internet
bandwith , and "10000000" for special internet connections with network cards up to 10Gb/s .
Using the "-s" switch with an higher value on a slow internet connection may kill your internet connection or give scanner
unreliable outputs .
For Normal 100Mbit internet connection users it is not advised to go further than "10000" over the -s switch .

- "escan -c" will recheck if current vulnerable ip list in eternal_scanner is still vulnerable (In case exists).

- "escan -ck /root/someiplist.txt" , will check manual ip list that user provide to escan , 
and will add the vulnerable ips to vuln.txt file in the end .

* Note : User manual ip list example should be structured with one ip per line

- "escan -i 192.168.1.1/24" , using this command directly from terminal will avoid eternal scanner
prompt for ip value , and will proceed automatically to ip/ip range scan .

- "escan -i 192.168.1.1/24 -s 3000" , same as (escan -i switch before) , but with scan speed at 3000 packets/s .

- "escan -v" , will display current vulnerable ip list (vuln.txt) on screen (in case exists)

- "escan -vo" , will display current Operating System vulnerable ip list (vuln_OS.txt) on screen (in case exists).

- "escan -u" , will update your current eternal scanner binaries . This switch will check if EternalScanner is installed
on a system path or not , in case it is on a system path then will update the binaries directly from github in that path .
In case Eternal scanner is not installed on a system path then it will update your binaries only in your eternal scannel local folder .

- "escan -l" , in case detailed vulnerability ip list file exists , it will provide user a search input field to
look in Eternal scanner database . 

- "escan -er" , Will check current vulnerability ip list (case exists) for Eternal Romance vulnerabilty , and will
create an output file in /usr/local/share/Eternal_Scanner/vulner.txt .

Some outputs from Eternal Romance Checks :
* Vulnerable = The Ip is Vulnerable to Eternal Romance Exploitation (SMB V1) or that Windows OS was not yet patched to this vulnerability
* Not Vulnerable = The Ip is not Vulnerable to Eternal Romance Exploitation (SMB V1) or that Windows OS was already patched to this exploitation .
* Time Out / Offline = It means that current ip is not online at the time of scan , or that current ip did not reply in maximum timeout .

Should be considered that many ISPS apply dhcp ips to their clients , this will mean that the current first scan of some ip could be
in another dhcp ip lease and will not return to to the original ip when eternal scanner got it for the first time .


- "./escan" normal launching method for eternal_scanner
On a normal launching method , eternal scanner will autosetup the scanner speed to "500pk/s" (packets per second) .
Eternal Scanner will scan user ip or ip range input for vulnerable hosts and will create a vulnerable file (vuln.txt)in 
its directory with the current vulnerable hosts detected . In case Vulnerable file already exists then eternal scanner will
add the new detected hosts to that file .


# Switches not available or not allowed :

- ./escan -s 3000 -c   - this command will not work
./escan -s 3000 -i 192.168.1.1   - this command will not work


## Installing dependencies for Eternal Scanner

- Eternal Scanner does a quick search on every start for masscan , metasploit-framework files , wget and python-pip ,
in case any of those tools does not exist on a system PATH variable , then eternal scanner will not run .
On debian pentest based distributions (Kali,Parrot,etc..) , installing masscan should be easy as writing 
(apt-get install masscan), but by default on pentest distros , these tools are already installed 
(masscan & metasploit framework).
On non pentest distributions and in case your debian distribution does not have in their repository these tools , then 
these tools can be compiled from their source code on your Linux OS just by following author instructions .
From version 2.0 and up , eternal scanner will require wget to be installed , wget is required to update eternal scanner
binaries directly from github with the switch (escan -u) , wget instalation can be done by (apt-get install wget) .
Python-pip (pip) is required for user to install Eternal romance python modules case his linux repository does not have 
thosemodules over apt-get .

For manual install of masscan github :
https://github.com/robertdavidgraham/masscan

For Metasploit-Framework github :
https://github.com/rapid7/metasploit-framework

Installing metasploit on a specific directory that is not on a system path variable  , it is advised to create a symlink on
a system path (like : /usr/bin  , or /usr/sbin) pointing to your specific metasploit directory .

- Eternal Scanner asks to your Linux OS if msfconsole (part of metasploit-framework) exists before running .

Python modules for eternal romance check :

The required python modules to run this check are : python-crypto python-impacket python-pyasn1-modules
all these modules can be install by apt-get .
In case your linux OS does not have these libraries and if you are using a debian based linux OS like :
Kali
Ubuntu
Devuan
Debian
etc....

Consider adding to your /etc/apt/sources.list file these repositories :
deb  http://deb.debian.org/debian sid main contrib non-free
deb-src  http://deb.debian.org/debian sid main contrib non-free

Then execute : "apt-get update && apt-get install python-crypto python-impacket python-pyasn1-modules"

atfer installing these modules you can remove these repositories from your : /etc/apt/sources.list  file , and
execute : "apt-get update"

an alternative installation for these modules is using pip , by writing in your terminal :
"pip install crypto"
"pip install impacket"
"pip install pyasn1-modules"

## Some Bugs that may appear using Eternal Scanner

"cat: msflog not found" - for this error to appear it means that your metasploit instalation is not working correctly .
Make sure you can run metasploit everywhere in your linux . To check this just write msfconsole outside metasploit directory .



