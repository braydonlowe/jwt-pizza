# Curiosity Report: HAR Files

## What it is:
Essentially, HAR files are a JSON-formatted file that is used to log the browser's interactions with a site.

### What determines an interaction?
#### Interactions:
- **HTTP Requests**
- **XHR/Fetch Requests** - API calls made by the webpage.
- **Redirects** - Information about them including the URL/site.
- **TLS/SSL Handshakes**
- **Caching Interactions**
- **Headers and Cookies**
- **Timing information** - Detailed timings for each request.

## Why HAR Files:
There are a few reasons why HAR files are a great choice for logging information from a website. Here are some of my favorites:
- HAR files provide comprehensive data. A lot of that data is described in the interactions section above.
- HAR is standardized so that it works with all major browsers and tools.
- HAR integrates seamlessly with various tools.
- The behavior is reproducible. It essentially is just a record of the exact thing that the website did.

## What existed before HAR files:
Something I've always been interested in is the history of the evolution of technology.

### What developers used before HAR files:
There were a few options:

- **Manual logging and analysis**:
  - Raw HTTP logs, or
  - Browser console logs.
 
  Both of these were pretty minimal in the amount of data they collected.

- **Packet sniffers**:
  Packet sniffers are software that monitor/capture network traffic.
  - **Tcpdump**: Command Line tool used for capturing network traffic.
  - **Wireshark**: Analyzes network packets.
 
- **Proxy Tools**:
  Proxies intercepted and recorded HTTP traffic between the browser and the server.
  - **Fiddler**
  - **Squid Logs**

There are a few more tools in different areas that were used before HAR files. However, this brings us to the creation of HAR files. Even with the tools that existed, there seemed to have been gaps in the testing formats that existed.

## Who created HAR files:
Google and W3C's Web Performance Working Group developed HAR files to standardize the file format to log HTTP interactions between browsers and servers. All of this data would then be captured in one place. The format was first introduced by Google Chrome's developer tools.

While there has been development on HAR files, the core of it stays the same.

## Standardization Format:
The HAR file is just a JSON object. The general format is as follows:

### Root Object:
- **log**
  - **version**
  - **creator**
  - **browser**
  - **entries**

The **Log** object contains the HAR version.

**Creator** describes the tool that created the HAR file.  
**Browser** contains details about the browser that generated the file.  
**Entries** is an array containing each HTTP request/response pair and their associated data.

## Sources:
- [Wikipedia](https://en.wikipedia.org/wiki/HAR_(file_format))
- [W3C Documentation](https://w3c.github.io/web-performance/specs/HAR/Overview.html)
