# CyberDefenders - Seized

## Scenario:

### Using Volatility, utilize your memory analysis skills to Investigate the provided Linux memory snapshots and figure out attack details.

## Prepa:
#### We're given a zip file which contains a profile to use on volatility:
#### $ cp Centos7.3.10.1062.zip /volatility/volatility/plugins/overlays/linux

#### Check that profile has loaded correctly
#### $ python2 vol.py --info| grep -i "linux"| grep -i "profile"
<br />
<br />

## Questions:                                   

### Q1/. What is the CentOS version installed on the machine?
#### $ strings dump.mem| grep "CentOS Linux"
<br />
<br />

### Q2/. There is a command containing a strange message in the bash history. Will you be able to read it?  
#### $ python2 vol.py -f dump.mem --profile=LinuxCentos7_3_10_1062x64 linux_bash > linux_bash.txt
#### $ echo c2hrQ1RGe2wzdHNfc3Q0cnRfdGgzXzFudjNzdF83NWNjNTU0NzZmM2RmZTE2MjlhYzYwfQo | base64 -d
<br />
<br />

### Q3/. What is the PID of the suspicious process?
#### $ python2 vol.py -f dump.mem --profile=LinuxCentos7_3_10_1062x64 linux_psaux > linux_psaux.txt
check nc command
<br />
<br />

### Q4/. The attacker downloaded a backdoor to gain persistence. What is the hidden message in this backdoor?
#### $ cat linux_bash.txt
#### $ git clone https://github.com/tw0phi/PythonBackup
#### $ cat /app/snapshot.py < looks like this code download a script from pastebin and execute it
#### $ curl -i https://pastebin.com/raw/nQwMKjtZ
#### $ echo c2hrQ1RGe3RoNHRfdzRzXzRfZHVtYl9iNGNrZDAwcl84NjAzM2MxOWUzZjM5MzE1YzAwZGNhfQo= | base64 -d
<br />
<br />

### Q5/. What are the attacker's IP address and the local port on the targeted machine?
#### $ python2 vol.py -f dump.mem --profile=LinuxCentos7_3_10_1062x64 linux_ifconfig > linux_ifconfig.txt #victimIP 
#### $ python2 vol.py -f dump.mem --profile=LinuxCentos7_3_10_1062x64 linux_netstat > linux_netstat.txt #attackerIP
<br />
<br />

### Q6/. What is the first command that the attacker executed?
#### $ cat linux_psaux.txt
<br />
<br />

### Q7/. After changing the user password, we found that the attacker still has access. Can you find out how? 
#### $ cat linux_bash.txt < attacker used vim to edit rc.local file
#### $ strings dump.mem| grep -A9 -B9 "rc.local"
#### $ echo c2hrQ1RGe3JjLmwwYzRsXzFzX2Z1bm55X2JlMjQ3MmNmYWVlZDQ2N2VjOWNhYjVii | base64 -d
<br />
<br />

### Q8/. What is the name of the rootkit that the attacker used?
#### $ python2 vol.py -f dump.mem --profile=LinuxCentos7_3_10_1062x64 linux_lsmod > linux_lsmod.txt
<br />
<br />

### Q9/. The rootkit uses crc65 encryption. What is the key?
#### $ strings dump.mem| grep -i "crc65"
<br />
<br />
