# 0x09. Web infrastructure design
## Learning Objectives
### General
+ You must be able to draw a diagram covering the web stack you built with the sysadmin/devops track projects
+ You must be able to explain what each component is doing
+ You must be able to explain system redundancy
+ Know all the mentioned acronyms: LAMP, SPOF, QPS
# Notes
## DNS
### What is DNS?
The Domain Name System (DNS) is the phonebook of the Internet. Humans access information online through domain names, like nytimes.com or espn.com. Web browsers interact through Internet Protocol (IP) addresses. DNS translates domain names to IP addresses so browsers can load Internet resources.

Each device connected to the Internet has a unique IP address which other machines use to find the device. DNS servers eliminate the need for humans to memorize IP addresses such as 192.168.1.1 (in IPv4), or more complex newer alphanumeric IP addresses such as 2400:cb00:2048:1::c629:d7a2 (in IPv6).

There are 4 DNS servers involved in loading a webpage:  
+ **DNS recursor(resolver)** - The recursor can be thought of as a librarian who is asked to go find a particular book somewhere in a library. The DNS recursor is a server designed to receive queries from client machines through applications such as web browsers. Typically the recursor is then responsible for making additional requests in order to satisfy the client’s DNS query.
+ **Root nameserver** - The root server is the first step in translating (resolving) human readable host names into IP addresses. It can be thought of like an index in a library that points to different racks of books - typically it serves as a reference to other more specific locations.
+ **TLD nameserver** - The top level domain server (TLD) can be thought of as a specific rack of books in a library. This nameserver is the next step in the search for a specific IP address, and it hosts the last portion of a hostname (In example.com, the TLD server is “com”).
+ **Authoritative nameserver** - This final nameserver can be thought of as a dictionary on a rack of books, in which a specific name can be translated into its definition. The authoritative nameserver is the last stop in the nameserver query. If the authoritative name server has access to the requested record, it will return the IP address for the requested hostname back to the DNS Recursor (the librarian) that made the initial request.

### The 8 steps in a DNS lookup:

1. A user types ‘example.com’ into a web browser and the query travels into the Internet and is received by a DNS recursive resolver.
2. The resolver then queries a DNS root nameserver (.).
3. The root server then responds to the resolver with the address of a Top Level Domain (TLD) DNS server (such as .com or .net), which stores the information for its domains. When searching for example.com, our request is pointed toward the .com TLD.
4. The resolver then makes a request to the .com TLD nameserver.
5. The TLD server then responds with the IP address of the domain’s nameserver, example.com.
6. Lastly, the recursive resolver sends a query to the domain’s nameserver.
7. The IP address for example.com is then returned to the resolver from the nameserver.
8. The DNS resolver then responds to the web browser with the IP address of the domain requested initially.
Once the 8 steps of the DNS lookup have returned the IP address for example.com, the browser is able to make the request for the web page:

9. The browser makes a HTTP request to the IP address.
10. The server at that IP returns the webpage to be rendered in the browser (step 10).

### What’s an A record?

An A record maps a domain name to the IP address (Version 4) of the computer hosting the domain. An A record uses a domain name to find the IP address of a computer connected to the internet

The A in A record stands for Address. Whenever you visit a web site, send an email, connect to Twitter or Facebook, or do almost anything on the Internet, the address you enter is a series of words connected with dots.

For example, to access the DNSimple website you enter www.dnsimple.com. At our name server, there’s an A record that points to the IP address 208.93.64.253. This means that a request from your browser to www.dnsimple.com is directed to the server with IP address 208.93.64.253.

### CNAME Record  
A Canonical Name (CNAME) record is a type of resource record in the Domain Name System (DNS) that maps one domain name (an alias) to another (the canonical name). 

This can prove convenient when running multiple services (like an FTP server and a web server, each running on different ports) from a single IP address. One can, for example, use CNAME records to point ftp.example.com and www.example.com to the DNS entry for example.com, which in turn has an A record which points to the IP address. Then, if the IP address ever changes, one only has to record the change in one place within the network: in the DNS A record for example.com.

When a DNS resolver encounters a CNAME record while looking for a regular resource record, it will restart the query using the canonical name instead of the original name. (If the resolver is specifically told to look for CNAME records, the canonical name (right-hand side) is returned, rather than restarting the query.)

        NAME                    TYPE   VALUE
    --------------------------------------------------
    bar.example.com.        CNAME  foo.example.com.
    foo.example.com.        A      192.0.2.23

### MX record
A mail exchanger record (MX record) specifies the mail server responsible for accepting email messages on behalf of a domain name. It is a resource record in the Domain Name System (DNS). It is possible to configure several MX records, typically pointing to an array of mail servers for load balancing and redundancy.  

Resource records are the basic information element of the Domain Name System (DNS). An MX record is one of these, and a domain may have one or more of these set up, as below:

    Domain			TTL   Class    Type  Priority      Host
    example.com.		1936	IN	MX	10         onemail.example.com.
    example.com.		1936	IN	MX	10         twomail.example.com.

The characteristic payload information of an MX record[1] is a preference value (above labelled "Priority"), and the domain name of a mailserver ("Host" above).

The priority field identifies which mailserver should be preferred - in this case the values are both 10, so mail would be expected to flow evenly to both onemail.example.com and twomail.example.com - a common configuration. The host name must map directly to one or more address records (A, or AAAA) in the DNS, and must not point to any CNAME records.[2]

When an e-mail message is sent through the Internet, the sending mail transfer agent (MTA) queries the Domain Name System for the MX records of each recipient's domain name. This query returns a list of host names of mail exchange servers accepting incoming mail for that domain and their preferences. The sending agent then attempts to establish an SMTP connection, trying the host with the lowest "Priority" value first. The system allows high-availability clusters of mail gateways to be built for one domain if necessary.[3]

The MX mechanism does not grant the ability to provide mail service on alternative port numbers, nor does it provide the ability to distribute mail delivery across a set of unequal-priority mail servers by assigning a weighting value to each one

## Links
### Concepts
+ [DNS](https://intranet.alxswe.com/concepts/12)
    + [Learn everything about DNS in cartoon](https://howdns.works/)
    + [A](https://support.dnsimple.com/articles/a-record/)
    + [CNAME](https://en.wikipedia.org/wiki/CNAME_record)
    + [MX Record](https://en.wikipedia.org/wiki/MX_record)
    + [TXT Record](https://en.wikipedia.org/wiki/TXT_record)  
    Advanced:
    + [Use DNS to scale with round-robin DNS](https://www.dnsknowledge.com/whatis/round-robin-dns/)
    + [What’s an NS Record?](https://support.dnsimple.com/articles/ns-record/)
    + [What’s an SOA Record?](https://support.dnsimple.com/articles/soa-record/)
+ [Monitoring](https://intranet.alxswe.com/concepts/13)
+ [Web Server](https://en.wikipedia.org/wiki/Web_server)
+ [Web server - MDN](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Web_mechanics/What_is_a_web_server)
+ [Network basics]()  
+ [Load balancer]()
+ [Server]()