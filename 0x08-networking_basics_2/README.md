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

### ~ Home Directory
The tilde (~) is shorthand for your home directory. It means you don’t have to type the full path to your home directory in commands. Wherever you are in the filesystem, you can use this command to go to your home directory:  

### ifconfig
Ifconfig is used to configure the kernel-resident network interfaces.  It is used at boot time to set up interfaces as necessary.  After that, it is usually only needed when debugging or when system tuning is needed.

If no arguments are given, ifconfig displays the status of the currently active interfaces.  If a single interface argument is given, it displays the status of the given interface only; if a single -a argument is given, it displays the status of all interfaces, even those that are down.  Otherwise, it configures an interface.  
### The telnet 
The telnetcommand is used to communicate with another host using the TELNET protocol. If telnet is invoked without the host argument, it enters command mode, indicated by its prompt (telnet>). In this mode, it accepts and executes the commands listed below. If it is invoked with arguments, it performs an open command with those arguments.e.g   

    telnet localhost 98

### Netcat in a Server-Client Architecture
The netcat utility can be run in the server mode on a specified port listening for incoming connections.

    $ nc -l 2389

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
+ 15 Special Characters You Need to Know for Bash  
https://www.howtogeek.com/439199/15-special-characters-you-need-to-know-for-bash/   
+ man sed  
