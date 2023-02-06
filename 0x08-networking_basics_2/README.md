# 0x08. Networking basics #1
## Notes
### What is localhost? 
In computer networking, localhost is a hostname that refers to the *current device* used to access it. It is used to access the network services that are running on the host via the loopback network interface. Using the loopback interface bypasses any local network interface hardware.   
### Loopback  
The *local loopback mechanism* may be used to *run a network service on a host without requiring a physical network interface*, or without making the service accessible from the networks the computer may be connected to. For example, a locally installed website may be accessed from a Web browser by the URL *http://localhost* to display its home page.

The name localhost normally resolves to the IPv4 loopback address 127.0.0.1, and to the IPv6 loopback address ::1.  
### Name resolution
IPv4 network standards reserve the entire address block 127.0.0.0/8 (more than 16 million addresses) for loopback purposes.That means any packet sent to any of those addresses is looped back. The address 127.0.0.1 is the standard address for IPv4 loopback traffic; the rest are not supported by all operating systems. However, they can be used to set up multiple server applications on the host, all listening on the same port number. The IPv6 standard assigns only a single address for loopback: ::1.  

The resolution of the name localhost to one or more IP addresses is normally configured by the following lines in the operating system's hosts file:   

    127.0.0.1    localhost
    ::1          localhost
 
 ### 0.0.0.0
 This host on this network.It is a non routable address  
 ### The hosts file  
 The hosts file is a plain text file that all operating systems use to translate hostnames (also known as web addresses or URLs) into IP addresses. When you type in a hostname, such as wikipedia.org, your system will look into the hosts file to get the IP address needed to connect to the appropriate server.  


# Links
+ What is Localhost  
https://en.wikipedia.org/wiki/Localhost  
+ What is 0.0.0.0  
https://en.wikipedia.org/wiki/0.0.0.0  
+ Linux Hosts file  
https://www.makeuseof.com/tag/modify-manage-hosts-file-linux/  
+ Practical Linux Netcat NC command Examples  
https://www.thegeekstuff.com/2012/04/nc-command-examples/
+ man ifconfig  
https://man7.org/linux/man-pages/man8/ifconfig.8.html  
+ man telnet  
https://linux.die.net/man/1/telnet  
+ man nc  
https://linux.die.net/man/1/nc  
+ man cut  
https://man7.org/linux/man-pages/man1/cut.1.html  
+ OSI Model   
https://www.imperva.com/learn/application-security/osi-model/  
