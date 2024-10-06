# **Domain Name System**

- Directory service that provides a mapping b/w the name of a host on the network & its numerical address.
- Required for the functioning of the internet (OR Imagine typing **2607:f8b0:4007:819::2004** every time you wanted to visit google.com)
- Each node in a tree has a domain name
- A full domain name is a sequence of symbols specified by dots
- Translates the domain name into IP address (for eg **2607:f8b0:4007:819::2004** to **https://www.google.com** in this case)

# Generic Domains

- Defines the Registered hosts according to their generic behavior


| **Label** | **Description**                        |
| --------- | -------------------------------------- |
| aero      | Airlines & aerospace companies         |
| biz       | Businesses or firms                    |
| com       | Commercial Organizations               |
| edu       | Educational Institutions               |
| gov       | Government Institutions                |
| info      | Information service providers          |
| mil       | Military groups                        |
| museum    | Museum & other nonprofit organizations |
| name      | Personal names                         |
| net       | Network Support Centres                |
| org       | Nonprofit Organizations                |
| pro       | Professional individual Organizations  |
| int       | International Organizations            |

# Country Domain

- Format is same.
- But uses two character country codes. (eg - .in India, .us USA)

# Inverse Domain

- Used for mapping an address to a name.

# Working

## User Input
	You type www.example.com into your web browser.

## DNS Query

	 The browser needs to find the IP address of www.example.com because computers communicate over the internet using IP addresses, not domain names.
	 
    The browser checks its cache first to see if the IP address is already known. If not, it sends a DNS query to the nearest DNS resolver (typically provided by your ISP).
    

## DNS Resolver

	The resolver will look up the domain name in its own cache. If the information is not cached, it will query other DNS servers.
	
     The request first goes to a root DNS server, which tells the resolver where to find the Top-Level Domain (TLD) DNS server for .com.
     
     The resolver then queries the TLD DNS server, which knows which Authoritative DNS server is responsible for example.com.

## IP Address Retrieval

	The authoritative DNS server for example.com responds with the IP address associated with www.example.com, e.g., 192.0.2.1.

## Request to Web Server

	Once the browser has the IP address, it can send an HTTP request directly to that IP. For example, the browser sends an HTTP request like:
	
	GET /index.html HTTP/1.1
	Host: www.example.com

## Document Retrieval

	The web server at 192.0.2.1 processes the request, retrieves the document index.html from its storage, and sends it back to the browser as an HTTP response.

## Display

	The browser processes the HTML document and renders the website's content on your screen.