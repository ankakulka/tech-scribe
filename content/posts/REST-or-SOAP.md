---
title: "REST or SOAP"
date: 2022-02-02T12:01:28+01:00
draft: false
show_reading_time: true
featured_image: "/images/comfy.png"
tags: ['REST', 'SOAP', 'API']
toc: true
---

First of all, let us consider whether we can compare those web services. 
**SOAP** (Simple Object Access Protocol), as the full name suggests, is a protocol. 
On the other hand, **REST** is an architectural style. It allows more flexibility and is considered easier to implement. 
RESTful applications have become ubiquitous in recent years, with SOAP web services
lagging behind. There is no simple answer to whether one is ‘better’ than the other -
it depends on the use case. As SOAP is much stricter, it is a preferable choice for applications where **security** is crucial. 
This would be a preferred choice when web services concerning regulated industries are considered.

Both SOAP and REST are language-agnostic (language independent) allowing engineers
to connect to a web service developed in a different language. 
However, the implementation in some cases might be cumbersome, and if there are no clear advantages of one
over the other, it is also worthwhile to consider what the available resources are. 
SOAP, in spite of trying to pass for a ‘simple’ service, might not be so simple after all, especially
when implementing it with JavaScript. Using Java with REST was until
recently unwieldy. Java 11 offers fully asynchronous HTTP/1.1 implementation.

## About SOAP

Some use cases where SOAP would be a preferred choice include large-scale enterprise
projects where reliability and formal contract are of paramount importance and for
ACID-compliant transactions. As SOAP works in a synchronous way, it is a better choice for
scenarios where the client requires to know the status of the web service in a very short
time.

### Web protocols

By implementing SOAP, it is possible to use a different protocol for messaging than HTTP, including:
- SMTP,
- TCP,
- JMS protocols. 

### Web Service Description Language

A SOAP web service includes a WSDL (Web Service Description Language), an XML-based document defining the way a web service is consumed. WSDL is either generated automatically or coded manually. 
In either case, it ensures the clarity and predictability of the service.

## About REST

REST stands for **RE**presantational State Transfer. Web services conforming to the REST
style are known as RESTful. 
These APIs are **stateless** so each request is independent of
another. This feature makes REST scalable and easy to cache. Other characteristics required to fulfill RESTful criteria are:
- uniform interface,
- client-server decoupling, 
- layered system architecture.

### Why is REST so popular?

The rise of RESTful APIs is tied to cloud computing and microservices. REST is faster and
more efficient than SOAP, multiple response formats are also possible — JSON, HTML,
XML, plain text. This has also contributed to the popularity of REST in recent years.

## Summary

To sum up, there is no clear winner and the best choice depends on the scenario. 
As REST has become the most popular choice in recent years, it is important to consider other factors such as security, which programming language is going to be used and whether 
a synchronous way might be required to provide a more stable service.

## References

References

- [Roy Fielding, Architectural Styles and the Design of Network-based Software Architectures](https://www.ics.uci.edu/~fielding/pubs/dissertation/top.htm)
- [Simple Object Access Protocol (SOAP) 1.1 specification](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)