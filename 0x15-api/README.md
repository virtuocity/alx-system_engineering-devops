# 0x15. API
## Notes
### Background Context

Old-school system administrators usually only know Bash and that is what they use to build their scripts. While Bash is perfectly fine for a lot of things, it can quickly get messy and not efficient compared to other programming languages. The new generation of system administrators, usually called SREs, are pretty much regular software engineers but instead of building products, they are managing systems. And one of the big differences with their predecessors is that they know more than just Bash scripting.

One popular way to expose an application and dataset is to use an API. Often, they are the public facing part of websites and micro-services so that allow outsiders to interact with them – access and modify their data. In this project, you will access employee data via an API to organize and export them to different data structures.

This is a perfect example of a task that is not suited for Bash scripting, so let’s build Python scripts.

### What is an API?
An application program interface (API) is a set of routines, protocols, and tools for building software applications. Basically, an API specifies how software components should interact. Additionally, APIs are used when programming graphical user interface (GUI) components. A good API makes it easier to develop a program by providing all the building blocks. A programmer then puts the blocks together.

There are many different types of APIs for operating systems, applications or websites. Windows, for example, has many API sets that are used by system hardware and applications — when you copy and paste text from one application to another, it is the API that allows that to work.

Most operating environments, such as MS-Windows and android, provide APIs, allowing programmers to write applications consistent with the operating environment. 

### What is a REST API? 
REST is an acronym for *Representational State Transfer* — an almost meaningless description of the most-used web service technology! A REST API is **a way for two computer systems to communicate using the HTTP technologies found in web browsers and servers.**

REST is simply a widely adopted style of API that we use to communicate with internal and external parties in a consistent and predictable way. It can be compared with how we used to send a letter with a postage stamp, address, and envelope in a certain way to ensure it gets delivered and read.

REST is commonly used by people on the web systems to interact with each other. For example, retrieving and updating account information in a social media application.

REST was defined in 2000 by Roy Fielding and is considerably simpler than the others. It’s not a standard but a set of recommendations and constraints for RESTful web services. These include:

+ **Client-Server:** SystemA makes an HTTP request to a URL hosted by SystemB, which returns a response.It’s identical to how a browser works. A browser makes a request for a specific URL. The request is routed to a web server which typically returns an HTML page. That page may contain references to images, style sheets, and JavaScript, which incur further requests and responses.

+ **Stateless:** REST is stateless: the client request should contain all the information necessary to respond.In other words, it should be possible to make two or more HTTP requests in any order, and the same responses will be received (… unless the API was designed to return random responses such as the quiz example above).
+ **Cacheable:** A response should be defined as cacheable or not.Caching improves performance because it’s not necessary to regenerate a response for the same URL. Private data specific to a certain user at a certain time would not normally be cached.
+ **Layered:** The requesting client need not know whether it’s communicating with the actual server, a proxy, or any other intermediary.
* The servers that perform helper functions for the main application server are commonly referred to as *microservices*.

## Resources
### Read or watch:

+ [Friends don’t let friends program in shell script](https://www.turnkeylinux.org/blog/friends-dont-let-friends-program-shell-script)
+ [What is an API?](https://www.webopedia.com/definitions/api/)
+ [What is an API? In English, please](freecodecamp.org/news/what-is-an-api-in-english-please-b880a3214a82/)
+ [What is a REST API](https://www.sitepoint.com/rest-api/)
+ [What are microservices?](https://smartbear.com/learn/api-design/microservices/)
+ [PEP8 Python style - having a clean code respecting style guide is really appreciated in the industry](https://peps.python.org/pep-0008/)