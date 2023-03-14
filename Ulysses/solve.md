# CyberDefenders - Ulysses

## Scenario:
A Linux server was possibly compromised and a forensic analysis is required in order to understand what really happened. Hard disk dumps and memory snapshots of the machine are provided in order to solve the challenge.

## Prepa:
#### We're given a zip file which contains a LinuxDebian profile to use in volatility 
#### $ cp Debian5_26.zip /volatility/volatility/plugins/overlays/linux

#### We're also given a sda.img file to investigate, to extract it i used
#### $ mkdir sda_mount
#### $ mount victoria-v8.sda1.img sda_mount/ 
<br />
<br />

## Questions:

### Q1/. The attacker was performing a Brute Force attack. What account triggered the alert?
#### $ sudo cat /sda_mount/var/log/auth.log
<br />
<br />

### Q2/. How many were failed attempts there?
#### $ sudo cat /sda_mount/var/log/auth.log | grep -i "failed" | wc
#### (wc gives us an extra field for the root so the answer was 32 not 33)
<br />
<br />

### Q3/. What kind of system runs on the targeted server?
#### $ cat /sda_mount/etc/issue.net
<br />
<br />

### Q4/. What is the victim's IP address?
#### $ python2 vol.py -f victoria-v8.memdump.img --profile=LinuxDebian5_26x86 linux_netstat > linux_netstat.txt
<br />
<br />

### Q5/. What are the attacker's two IP addresses? Format: comma-separated in ascending order
#### $ cat linux_netstat.txt
<br />
<br />

### Q6/. What is the "nc" service PID number that was running on the server?
#### $ python2 vol.py -f victoria-v8.memdump.img --profile=LinuxDebian5_26x86 linux_pslist > linux_pslist.txt
<br />
<br />

### Q7/. What service was exploited to gain access to the system? (one word)
#### $ python2 vol.py -f victoria-v8.memdump.img --profile=LinuxDebian5_26x86 linux_psaux > linux_psaux.txt
<br />
<br />

### Q8/. What is the CVE number of exploited vulnerability? 
#### CVE-2010-4344
<br />
<br />

### Q9/. During this attack, the attacker downloaded two files to the server. Provide the name of the compressed file.
#### $ cd /sda_mount/tmp && ls
<br />
<br />

### Q10/. Two ports were involved in the process of data exfiltration. Provide the port number of the highest one.
#### $ cat linux_netstat.txt
<br />
<br />

### Q11/. Which port did the attacker try to block on the firewall?
#### $ cd /sda_mount/tmp
#### $ sudo tar -xvf rk.tar && cd rk
#### $ cat vars.sh
<br />
<br />
