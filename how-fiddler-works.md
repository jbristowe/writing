
# Understanding How Telerik Fiddler Works

Given the ubiquitous nature of the Internet, many applications are built to assume network connectivity. That's because a connection to the web can greatly expand the capabilities of an application through the integration of remote data and services. However, this integration is often error-prone; services can become unavailable and data can take a long time to transfer over slow networks. In fact, many bugs can be attributed to conditions relating to the underlying network. In these situations, it's useful to have a utility that's able to help you debug the problem; a utility to monitor the network traffic  (HTTP or HTTPS) that occurs between your application and the services it relies upon.

Enter [Telerik Fiddler](https://www.telerik.com/fiddler).

## What is Telerik Fiddler?

Telerik Fiddler (or Fiddler) is a special-purpose proxy server for debugging web traffic from applications like browsers. It's used to capture and record this web traffic and then forward it onto a web server. The server's responses are then returned to Fiddler and then returned back to the client. The recorded web traffic is presented through a session list in the Fiddler UI:

![](https://i.imgur.com/SF40wep.png)

Nearly all programs that use web protocols support proxy servers. As a result, Fiddler can be used with most applications without need for further configuration. When Fiddler starts to capture traffic, it registers itself with the [Windows Internet (WinINet)](https://docs.microsoft.com/windows/desktop/wininet/about-wininet) networking component and requests that all applications begin directing their requests to Fiddler.

## "What is a proxy?"

If you had asked me this question back in the early 1990s, I would have likely replied, "It's that thing that kills your Internet connection, right?" Back in the day, if found myself with a proxy configured on my machine then I'd sometimes see broken images on webpages. This would be followed by some cursing and many presses of the <kbd>F5</kbd> key. Obviously, things have improved since then. However, the question remains a good one to ask, especially for developers writing applications that will support them.

The [section 2.3 of the HTTP specification](https://httpwg.org/specs/rfc7230.html#intermediaries) defines a proxy as:

> a message-forwarding agent that is selected by the client, usually via local configuration rules, to receive requests for some type(s) of absolute URI and attempt to satisfy those requests via translation through the HTTP interface

The phrase, "selected by the client" in the description (above) is a key characteristic; a proxy is designated by a [user agent](https://en.wikipedia.org/wiki/User_agent) (UA) to convey messages to "origin server" (i.e. google.com). It's also specialised because it may perform actions on messages that are received. (More on this later.)

![](https://i.imgur.com/ii1HgSSl.png)

Consider this classic (and very funny) scene from the American sitcom, [I Love Lucy](https://www.imdb.com/title/tt0043208/):

[![I Love Lucy](http://img.youtube.com/vi/NkQ58I53mjk/0.jpg)](https://www.youtube.com/watch?v=NkQ58I53mjk "I Love Lucy")

In this scene, when a chocolate travels down the conveyor belt, it's observed, picked up, wrapped, and then placed back. This is a good way of thinking how a proxy works. Here, the assembly workers (Lucy and Ethel) represents proxies, a chocolate represents a message, and the conveyor belt represents the network. It's a brilliant scene because the concepts of network latency and reliably are also personified.

This scene doesn't represent a network in all its aspects. For example, it only represents outbound traffic. Let's not forget that HTTP is a request-response protocol. What about inbound traffic? For this, we would have to imagine chocolates simultaneously travelling in the opposite direction. The assembly worker would modify and forward the chocolates in the same manner as before. When this occurs with a network, a proxy is defined as a "reverse proxy" or "gateway". In other words, an origin server for outbound messages; it translates requests and forwards them inbound.

## Telerik Fiddler as a Proxy

[Telerik Fiddler](https://www.telerik.com/fiddler) (or Fiddler) is a web debugging proxy. That means it's acts as an [intermediary](https://httpwg.org/http-core/draft-ietf-httpbis-semantics-latest.html#intermediaries) and can troubleshoot the traffic that's sent between a user agent (i.e. Google Chrome) and the network. Nearly all programs that use web protocols support integration with a proxy. As a result, Fiddler can be used with most applications without need for further configuration. When Fiddler starts to capture traffic, it registers itself with the [Windows Internet (WinINet)](https://docs.microsoft.com/windows/desktop/wininet/about-wininet) networking component and requests that all applications begin directing their requests to Fiddler.

![](https://i.imgur.com/fx6LavP.png)

In the most common scenario where Fiddler is the only proxy that's configured to operate on the network, the architecture becomes a little simplier:

![](https://i.imgur.com/D6JqD1fl.png)

Many web developers will use Fiddler in this manner; to record web traffic that's generated by a browser to see what was transmitted. Since Fiddler is a proxy, it may process this web traffic before forwarding it upstream. This includes responding to messages on behalf of the origin server. The HTTP specification enables proxies to do this. In fact, Fiddler can be configured to respond to messages that match criteria you define through the [AutoResponder](https://docs.telerik.com/fiddler/KnowledgeBase/AutoResponder). The feature may be configured to serve local files (acting as a cache) or perform actions for messages it receives:

![](https://i.imgur.com/O2AkO1jl.png)

The AutoResponder supports a useful development scenario when resources and/or services may be unavailable. It may be used to mock API responses from a service. The AutoResponder may also be configured with a latency setting to simulate a more realistic response time.

The HTTP specification enables proxies to transform messages and their payloads (see [section 5.7.2](https://httpwg.org/specs/rfc7230.html#message.transformations)). In the example I cited (above), this is represented by Lucy and Ethel wrapping the individual chocolates as they travel along the conveyor belt. Fiddler is capable of transforming messages as they are intercepted. For example, I can add/remove HTTP headers and modify message payloads.

The transformation of messages is made possible through custom rules written in FiddlerScript. FiddlerScript is one of the most powerful features in Fiddler; it can be used to enhance Fiddler's UI, add new features, and modify messages. It can even change various characteristics of the network or client as messages are transmitted. For example, I can write FiddlerScript to simulate conditions of the browser (i.e. no cookies) or reroute traffic.

![](https://i.imgur.com/sZODz3T.png)

Two events are available that can be used to modify messages in transit: `OnBeforeRequest` and `OnBeforeResponse`. `OnBeforeRequest` is called before each request and `OnBeforeResponse` is called before each response.

Eric Lawrence has written a great article entitled, [Understanding FiddlerScript](https://www.telerik.com/blogs/understanding-fiddlerscript) where he describes its available functions. He's also published a list of FiddlerScript "recipes": [Fiddler Web Debugger - Script Samples](https://www.fiddlerbook.com/fiddler/dev/scriptsamples.asp).

### Telerik Fiddler as a Reverse Proxy

Incidentally, it can be useful to have Fiddler operate as a [reverse proxy](https://en.wikipedia.org/wiki/Reverse_proxy); a server that can translates requests and forwards them inbound. This can be useful in a situation where you may wish to capture traffic with Fiddler, but you are unable to configure the client to use a proxy server. Steps to configure Fiddler to operate in this manner are outlined in the documentation: [Use Fiddler as a Reverse Proxy](https://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/UseFiddlerAsReverseProxy).

## The More You Know

Understanding how Fiddler operates as a web debugging proxy will enable you to target scenarios where you're interested in seeing what's transmitted on the network. Once you have Fiddler configured correctly, you'll be able to use its large set of features. To get started, why not download Fiddler and kick the tires for yourself? And if you're interested in seeing the future, check out [Fiddler Everywhere](https://www.telerik.com/fiddler-everywhere), which runs across Windows, macOS, and Linux.
