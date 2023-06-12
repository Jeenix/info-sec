# misc explaination of security things
*Mostly explainations I've done for various excercises*

Ping.exe - to map the network and identify potential targets and vulnerable systems 

whoami.exe - user information to determine user's privledges and the extent of access then can get so they can plan their attack accordingly 

taskkill.exe - able to disrupt system functionality by being able to terminate processes. The attacker can use this to disable antivirus software, for example.

netstat.exe - gather information about network connections to find potential entry points and active service and communication channels for lateral movement through the network 

ipconfig.exe - to understand the network configuration of the compromised system, including IP addresses, DNS config, default gateways. This helps the attacker identify potential targets and network environment 

#### Persistent malware 

The persistent malware file is designed with persistent mechanisms to ensure it survives reboots and remain on the infected host, 
so its likely to have been a recent registry change that allow its installers to run and process commands stored in the file WinInit.ini. 
This allows the malware to take action while the computer is still booting up to install a new copy of the malware software. 
To remove of it, disconnect from the network, terminate the malicious process, using the registry change log to identify what has been changed ie what the persistent mechanisms are being employed by the malware, then remove them. 
Possible other steps include malware scanning, software updates and patches to prevent in reoccuring. 
