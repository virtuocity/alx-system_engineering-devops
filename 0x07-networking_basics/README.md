# 0x07. Networking basics #0
## Notes
### OSI Model
The Open Systems Interconnection model (OSI model) is a conceptual model that 'provides a common basis for the coordination of [ISO] standards development for the purpose of systems interconnection'. In the OSI reference model, the communications between a computing system are split into seven different abstraction layers: Physical, Data Link, Network, Transport, Session, Presentation, and Application.  
### TCP And UDP
*TCP/IP* is a suite of protocols used by devices to communicate over the Internet and most local networks. It is named after two of it’s original protocols—the Transmission Control Protocol (TCP) and the Internet Protocol (IP). TCP provides apps a way to deliver (and receive) an ordered and error-checked stream of information packets over the network.   
*The User Datagram Protocol (UDP)* is used by apps to deliver a faster stream of information by doing away with error-checking   
**What they have in common**
Both TCP and UDP are protocols used for sending bits of data—known as packets—over the Internet.
### How TCP Works 
TCP is the most commonly used protocol on the Internet.   

When you request a web page in your browser, your computer sends TCP packets to the web server’s address, asking it to send the web page back to you. The web server responds by sending a stream of TCP packets, which your web browser stitches together to form the web page. When you click a link, sign in, post a comment, or do anything else, your web browser sends TCP packets to the server and the server sends TCP packets back.   

*Note that a specific IP + port = socket.*   

### Check Listening Ports with netstat
*netstat* is a command-line tool that can provide information about network connections.  

To list all TCP or UDP ports that are being listened on, including the services using the ports and the socket status use the following command:   

    $sudo netstat -tunlp  
    

## Tasks
## Links 
+ OSI Model   
https://en.wikipedia.org/wiki/OSI_model   
+ Different kinds of networks   
https://www.lifewire.com/lans-wans-and-other-area-networks-817376   
+ LAN Network    
https://en.wikipedia.org/wiki/Local_area_network   
+ WAN Network   
https://en.wikipedia.org/wiki/Wide_area_network   
+ What is the internet?   
https://roadmap.sh/guides/what-is-internet   
+ MAC Address   
https://whatismyipaddress.com/mac-address   
+ What is an IP address?   
https://www.bleepingcomputer.com/tutorials/ip-addresses-explained/   
+ Private and public IP addresses 
https://www.iplocation.net/public-vs-private-ip-address   
+ IPv4 and IPv6   
https://www.webopedia.com/insights/ipv6-ipv4-difference/   
+ Localhost   
https://en.wikipedia.org/wiki/Localhost  
+ TCP and UDP  
https://www.howtogeek.com/190014/htg-explains-what-is-the-difference-between-tcp-and-udp/  
+ TCP/UDP ports List   
https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers   
+ What is ping /ICMP   
https://en.wikipedia.org/wiki/Ping_%28networking_utility%29   
+ Positional parameters   
https://wiki.bash-hackers.org/scripting/posparams   