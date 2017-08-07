## ETERNAL SCANNER (How To Use)

* Disclaimer
- Eternal Scanner does not exploit any IP , Eternal Scanner only checks if IP or IP Range is exploitable with CVE-2017-0144
- CVE-2017-0144 Exploit Information : https://www.cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-0144
- Scanning an IP or an IP Range that is not under your maintenance is forbidden in many countries and it goes against the law .
- Eternal Scanner was build for network System administrators in order to check if any station is vulnerable to this exploit .


## How to use

* Switches

-Running in current eternal_scanner directory over terminal :
- "./escan -h"  will popup the available switches
- "./escan -s 1000" will setup the scanner rate speed to 1000pk/s 
- Rate speed :
Eternal Scanner allows the -s switch to accept values from 100pk/s to 100000000pk/s where "100" should be used for low internet
bandwith , and "10000000" for special internet connections with network cards up to 10Gb/s .
Using the "-s" switch with an higher value on a slow internet connection may kill your internet connection or give scanner
unreliable outputs .
For Normal 100Mbit internet connection users it is not advised to go further than "10000" over the -s switch .

- "./escan -c" will recheck if current vulnerable ip list in eternal_scanner is still vulnerable (In case exists).
Latest changes in code , allows when this switch is activated , as it is , to not only recheck the vuln.txt file automatically
created by eternal_scanner on 1st running (in case positive results are achieved) , but also create another detailed file
called "vuln_OS.txt" that contains not only the vulnerable ips from (vuln.txt) but also their respective Operating System .
vuln_OS.txt is only created when this switch is activated and in not any other circunstance or switch .

- "./escan -c /root/someiplist.txt" , will check manual ip list that user provide to escan , and will add the vulnerable ip
list to vuln.txt file in the end .
In case user iplist path is wrong then escan will set the default "vuln.txt" file , in case exists .

* Note : User manual ip list example should be strucutred with one ip per line

- "./escan" normal launching method for eternal_scanner
On a normal launching method , eternal scanner will autosetup the scanner speed to "500pk/s" (packets per second) .
Eternal Scanner will scan user ip or ip range input for vulnerable hosts and will create a vulnerable file (vuln.txt)in 
its directory with the current vulnerable hosts detected . In case Vulnerable file already exists then eternal scanner will
add the new detected hosts to that file .


# Switches not available or not allowed :

- ./escan -s 3000 -c   - this command will not work
- ./escan -s 3000 192.68.1.1/24  - adding an ip ahead scanner speed was NOT inplemented yet in Eternal Scanner


## Installing dependencies for Eternal Scanner

- Eternal Scanner does a quick search on every start for masscan and metasploit-framework files , in case any of those 
tools does not exist on a system PATH variable , then eternal scanner will not run .
On debian pentest based distributions (Kali,Parrot,etc..) , installing masscan should be easy as writing apt-get install masscan
, but by default on pentest distros , these tools are already installed (masscan & metasploit framework).
On non pentest distributions and in case your debian distribution does not have in their repository these tools , then 
these tools can be compiled from their source code on your Linux OS just by following author instructions .

For manual install of masscan github :
https://github.com/robertdavidgraham/masscan

For Metasploit-Framework github :
https://github.com/rapid7/metasploit-framework

Installing metasploit on a specific directory that is not on a system path variable  , it is advised to create a symlink on
a system path (like : /usr/bin  , or /usr/sbin) pointing to your specific metasploit directory .

- Eternal Scanner asks to your Linux OS if msfconsole (part of metasploit-framework) exists before running .

## Some Bugs that may appear using Eternal Scanner

- I notice that eternal scanner output an error is metasploit have to check more than 700 ips in one single instance .
- On next update of eternal scanner , the script will detect if the ip list is bigger than 500 ips , and if that is the case then it will divide the list and batch multiple sessions for metasploit to scan .
Example : if an ip list to be checked have 3000 ips , then the script will divide that lit to other 6 smaller lists and will batch metasploit in multiple jobs , this means that the script will divide the 3000 ips to 6 lists with 500 ips and will check
one by one .



