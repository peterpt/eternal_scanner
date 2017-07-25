## ETERNAL SCANNER (How To Use)

* Disclaimer
- Eternal Scanner does not exploit any IP , Eternal Scanner only checks if IP or IP Range is exploitable with CVE-2017-0144
- Scanning an IP or Range of IP that is not under your maintenance if forbidden in many countries and it goes against the law .
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
unreliale outputs .
For Normal 100Mbit internet connection users it is not advised to go further than "10000" over the -s switch .

- "./escan -c" will recheck if current vulnerable ip list in eternal_scanner is still vulnerable (In case exists).
Latest changes in code , allows when this switch is activated as it is to not only recheck the vuln.txt file automatically
created by eternal_scanner on 1st running (in case positive results are achieved) , but also create another detailed file
called "vuln_OS.txt" that contains not only the still vulnerable ips but also their respective Operating System .
vuln_OS.txt is only created when this switch is activated and in not any other circunstance or switch .

- "./escan" normal launching method for eternal_scanner
On a normal launching method , eternal scanner will autosetup the scanner speed to "500pk/s" (packets per second) .
Eternal Scanner will scan user ip or ip range input for vulnerable hosts and will create a vulnerable file (vuln.txt)in 
its directory with the current vulnerable hosts detected . In case Vulnerable file already exists then eternal scanner will
add the new detected targets to that file .


# Switches not available or not allowed :

- ./escan -s 3000 -c   - this command will not work
- ./escan -s 3000 192.68.1.1/24  - adding an ip ahead scanner speed was NOT yet inplemented in eternal scanner
- ./escan -c ~/ipfile.txt - Scanning an indenpendent ip list is not yet available but will be soon .

