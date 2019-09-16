# SNI-modifier

This proxy modifies SNI header via MITM to bypass SNI-based HTTPS firewalls.  
It uses a method suggested by this paper 10.1109/INM.2015.7140423:  
Upon receiving a connection, the proxy first tries to connect to the target domain with SNI disabled. If that didn't work (e.g. for some cloudflare protected doamins), it will then try to connect with SNI enabled.

To use this you should first generate a CA cert/privkey pair and place them under `/etc/sni-modifier/`. Then compile the program and run it.  
You should be able to get a running socks5 server at localhost:8080.
