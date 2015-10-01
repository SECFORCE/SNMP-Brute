# SNMP Brute
SNMP brute force, enumeration, CISCO config downloader and password cracking script.
Listens for any responses to the brute force community strings, effectively minimising wait time.

Requirements	
=======================
* metasploit
* snmpwalk
* snmpstat
* john the ripper

Usage	
=======================
  `python snmp-brute.py -t [IP]`

Options
=======
`--help, -h`              show this help message and exit

`--file=DICTIONARY, -f DICTIONARY`   Dictionary file

`--target=IP, -t IP`      Host IP

`--port=PORT, -p PORT`    SNMP port

Advanced
--------
`--rate=RATE, -r RATE`    Send rate

`--timeout=TIMEOUT`       Wait time for UDP response (in seconds)

`--delay=DELAY`           Wait time after all packets are send (in seconds)

`--iplist=LFILE`          IP list file

`--verbose, -v`           Verbose output

Automation
----------
`--bruteonly, -b`         Do not try to enumerate - only bruteforce

`--auto, -a`              Non Interactive Mode

`--no-colours`            No colour output

Operating Systems
-----------------
`--windows`               Enumerate Windows OIDs (snmpenum.pl)

`--linux`                 Enumerate Linux OIDs (snmpenum.pl)

`--cisco`                 Append extra Cisco OIDs (snmpenum.pl)

Alternative Options
-------------------
`--stdin, -s`             Read communities from stdin

`--community=COMMUNITY, -c COMMUNITY`    Single Community String to use

`--sploitego`             Sploitego's bruteforce method

Features	
=======================
* Brute forces both version 1 and version 2c SNMP community strings
* Enumerates information for CISCO devices or if specified for Linux and Windows operating systems.
* Identifies RW community strings
* Tries to download the router config (metasploit module).
* If the CISCO config file is downloaded, shows the plaintext passwords (metasploit module) and tries to crack hashed passords with John the Ripper

Credits	
=======================
* cisc0wn - github.com/nccgroup/cisco-SNMP-enumeration
* sploitego project - github.com/allfro/sploitego/blob/master/src/sploitego/scapytools/snmp.py
* snmpenum.pl script - by Filip Waeytens
* metasploit - www.metasploit.com
