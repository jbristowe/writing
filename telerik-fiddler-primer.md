# A Primer on Telerik Fiddler

Given the ubiquitous nature of the Internet, many applications are built to assume network connectivity. That's because a connection to the web can greatly expand the capabilities of an application through the integration of remote data and services. However, this integration is often error-prone; services can become unavailable and data can take a long time to transfer over slow networks. In fact, many bugs can be attributed to conditions relating to underlying network. In these situations, it's useful to have a utility that's able to help you debug the problem; a utility to monitor the network traffic  (HTTP or HTTPS) that occurs between your application and the services it relies upon.

Enter [Telerik Fiddler](https://www.telerik.com/fiddler).

## What is Telerik Fiddler?

Telerik Fiddler (or Fiddler) is special-purpose proxy server for Windows. Locally-running programs like web browsers, Office applications, and other clients send their HTTP and HTTPS requests to Fiddler, which then typically forwards the traffic to a web server. The server's responses are then returned to Fiddler, which passes the traffic back to the client.

![](https://i.imgur.com/SF40wep.png)

Nearly all programs that use web protocols support proxy servers. As a result, Fiddler can be used with most applications without need for further configuration. When Fiddler starts to capture traffic, it registers itself with the [Windows Internet (WinINet)](https://docs.microsoft.com/windows/desktop/wininet/about-wininet) networking component and requests that all applications begin directing their requests to Fiddler.

![](https://i.imgur.com/c3eBDsD.png)

A small set of applications do not automatically respect the Windows networking configuration and may require manual configuration in order for Fiddler to capture their traffic. Fiddler can be configured to work in these scenarios, including server-to-server (e.g. web services) and device-to-server traffic (e.g. mobile device clients). By default, Fiddler is designed to automatically chain to any upstream proxy server that was configured before it began capturing - this allows Fiddler to work in network environments where a proxy server is already in use.

Because Fiddler captures traffic from all locally-running processes, it supports a wide range of filters. These enable hiding of traffic which is not of interest to you, as well as highlighting (using colors or font choice) of traffic deemed interesting. Filters can be applied based on the source of the traffic (e.g. the specific client process) or based on some characteristic of the traffic itself (e.g. what hostname the traffic is bound for, or what type of content the server returned).

Fiddler supports a rich extensibility model which ranges from simple [FiddlerScript](https://www.telerik.com/blogs/understanding-fiddlerscript) (C# or JScript 10.0) to powerful [extensions which can be developed using any .NET language](http://docs.telerik.com/fiddler/Extend-Fiddler/ExtendWithDotNet). Fiddler also supports several special-purpose extension types, the most popular of which is called an **Inspector**, so named because it enables you to inspect a single request or response. Inspectors can be built to display all response types (e.g. the HexView Inspector) or tailored to support a type-specific format (e.g. the JSON Inspector). If you're a developer, you can build Fiddler's core proxy engine into your applications using a class library named [FiddlerCore](https://www.telerik.com/fiddler/fiddlercore).

Fiddler can decrypt HTTPS traffic and display and modify the requests that would otherwise be inscrutable to observers on the network using a man-in-the-middle decryption technique. To permit seamless debugging without security warnings, Fiddler's root certificate may be installed in the Trusted Certificates store of the system or web browser.

![](https://i.imgur.com/iM6rALt.png)

A web session represents a single transaction between a client and a server. Each session appears as a single entry in the **Web Sessions List** in the Fiddler interface. Each session object has a request and a response, representing what the client sent to the server and what the server returned to the client. The session object also maintains a set of flags that record metadata about the session, and a timers object that stores timestamps logged in the course of processing the session.

![](https://i.imgur.com/7miJVqT.png)

Proxy servers are not limited to simply viewing network traffic; Fiddler got its name from its ability to "fiddle" with outbound requests and inbound responses. Manual tampering of traffic may be performed by [setting a request or response breakpoint](https://www.telerik.com/blogs/breakpoints-in-fiddler). When a breakpoint is set, Fiddler will pause the processing of the session and permit manual alteration of the request and the response.

![](https://i.imgur.com/4mBUiNz.png)

Traffic rewriting may also be performed automatically by script or extensions running inside of Fiddler. By default, Fiddler operates in buffering mode, whereby the server's response is completely collected before any part of it is sent to the client. If the streaming mode is instead enabled, the server's response will be immediately returned to the client as it is downloaded. In streaming mode, response tampering is not possible.

Captured sessions can be saved in a Session Archive Zip (SAZ) file for later viewing. This compressed file format contains the full request and response, as well as flags, timers, and other metadata. A lightweight capture-only tool known as [FiddlerCap](https://www.telerik.com/fiddler/fiddlercap) may be used by non-technical users to collect a SAZ file for analysis by experts. Fiddler supports Exporter extensions that allow storing captured sessions in myriad other formats for interoperability with other tools. Similarly, Fiddler supports Importer extensions that enable Fiddler to load traffic stored in other formats, including the [HTTP Archive (HAR) format](https://en.wikipedia.org/wiki/.har) used by many browsers' developer tools.

## Usage Scenarios

Some of the most common questions are of the form: *"Can I use Fiddler to accomplish [x]?"* While there are a huge number of scenarios for which Fiddler is useful, and a number of scenarios for which Fiddler isn't suitable, the most common tasks fall into a few buckets. Here's a rough guide to what you can and cannot do with Fiddler:

### An Incomplete List of Things Fiddler Can Do

* View web traffic from nearly any browser, client application, or service.
* Modify any request or response, either manually or automatically.
* Decrypt HTTPS traffic to enable viewing and modification.
* Store captured traffic to an archive and reload it later, even from a different computer.
* Playback previously-captured responses to a client application, even if the server is offline.
* Debug web traffic from most PCs and devices, including macOS/Linux systems and mobile devices.
* Chain to upstream proxy servers, including the Tor network.
* Run as a reverse proxy on a server to capture traffic without reconfiguring the client computer or device.
* Grow more powerful with new features added by FiddlerScript or the .NET-based extensibility model.

### An Incomplete List of Things Fiddler Cannot Do

While Fiddler is a very flexible tool, there are some things it cannot presently do. That list includes:

* Debug non-web protocol traffic.
	* Fiddler works with HTTP, HTTPS, and FTP traffic and related protocols like HTML5 WebSockets and ICY streams.
	* Fiddler cannot "see" or alter traffic that runs on other protocols like SMTP, POP3, Telnet, IRC, etc.
	* Handle huge requests or responses.
* Fiddler cannot handle requests larger than 2 GB in size.
	* Fiddler has limited ability to handle responses larger than 2 GB.
	* Fiddler uses system memory and the pagefile to hold session data. Storing large numbers of sessions or huge requests or responses can result in slow performance.
* "Magically" remove bugs in a website for you.
	* While Fiddler will identify networking problems on your behalf, it generally cannot fix them without your help. I can't tell you how many times I've gotten emails asking: "What gives? I installed Fiddler but my website still has bugs!"

*The above text is a modified excerpt from the book, "Debugging with Fiddler, Second Edition" by [Eric Lawrence](https://twitter.com/ericlaw). Options for purchasing this book can be found at [fiddlerbook.com](https://fiddlerbook.com/book/).*
