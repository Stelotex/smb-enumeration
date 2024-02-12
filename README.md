# smb-enumeration
Enumerating SMB protocol

# USING NMAP
nmap --script smb-os-discovery $IP \n
nmap --script nbstat.nse $IP \n
nmap --script smb-enum-shares -p139,445 $IP \n

# USING NMBLOOKUP
nmblookup -A $IP \n

# using NBSTAT
nbstat -A $IP \n

# Finally SMBMAP
smbmap -H 192.168.1.40 \n
smbmap -H 192.168.1.17 -u raj -p 123 \n

# USING MSFCONSOLE
use auxiliary/scanner/smb/smb_enumshares \n
set rhosts $IP \n
smbuser raj \n
smbuser pass 123 \n
exploit \n

# USING SMBCLIENT
smbclient -L $IP -U raj%123 \n
smbclient //$IP/share -U raj%123 \n
get raj.txt \n

smbclient -L $IP \n
smbclient //$IP/guest \n
get file.txt \n

# OTHERS
rpcclient -U "" -N $IP \n
netshareenum \n
netshareenumall \n
net view \\$IP /All \n
crackmapexec smb $IP -u 'raj' -p '123' --shares \n
