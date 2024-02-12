# smb-enumeration
Enumerating SMB protocol

# USING NMAP
nmap --script smb-os-discovery $IP

nmap --script nbstat.nse $IP

nmap --script smb-enum-shares -p139,445 $IP 


# USING NMBLOOKUP
nmblookup -A $IP

# using NBSTAT
nbstat -A $IP

# Finally SMBMAP
smbmap -H 192.168.1.40

smbmap -H 192.168.1.17 -u raj -p 123

# USING MSFCONSOLE
use auxiliary/scanner/smb/smb_enumshares

set rhosts $IP

smbuser raj

smbuser pass 123

exploit

# USING SMBCLIENT
smbclient -L $IP -U raj%123

smbclient //$IP/share -U raj%123

get raj.txt

smbclient -L $IP

smbclient //$IP/guest

get file.txt

# OTHERS
rpcclient -U "" -N $IP

netshareenum

netshareenumall

net view \\$IP /All

crackmapexec smb $IP -u 'raj' -p '123' --shares 
