# Introduction

There are two types of HTTP messages as discussed previously:

- HTTP **request messages**

- HTTP **response messages**

We’ll study request messages in this one.

# HTTP Request Messages

Let’s look at request messages first. Here is an example of a typical HTTP message:

```
GET /path/to/file/index.html HTTP/1.1
Host: www.educative.io
Connection: close
User-agent: Mozilla/5.0
Accept-language: fr
Accept: text/html
```

It should be noted that,

- HTTP messages are in **plain ASCII text**

- **Each line** of the message **ends with** two control characters: a **carriage return and a line feed:** \r\n.

  - The last line of the message also ends with a carriage return an d a line feed!

- This particular message has 6 lines, but HTTP messages can have **one or as many lines as needed.**

- The first line is called the **request line** while the rest are called **header lines.**

# The Anatomy of an HTTP Request Line

The HTTP request line is followed by an HTTP header. We’ll look at the request line first. The request line consists of three parts:

- **Method**

- **URL**

- **Version**

## HTTP Methods

HTTP methods tell the server what to do. There are a lot of HTTP methods but we’ll study the most common ones: <code>GET</code>, <code>POST</code>, <code>HEAD</code>, <code>PUT</code>, or <code>DELETE</code>.

- <code>GET</code> is the most common and **requests data.**

- <code>POST</code> **puts an object on the server.**

  - This method is generally used when the client is not sure where the new data would reside. The server responds with the location of the object.

  - The data posted can be a message for a bulletin board, newsgroup, mailing list, a command, a web form, or an item to add to a database.

  - The POST method technically requests a page but that depends on what was entered.

- <code>HEAD</code> is similar to the <code>GET</code> method except that **the resource requested does not get sent in response. Only the HTTP headers are sent** instead.

  - This is useful for quickly retrieving meta-information written in response headers, without having to transport the entire content. In other words, it’s useful to check with minimal traffic if a certain object still exists. This includes its meta-data, like the last modified date. The latter can be useful for caching.

  - This is also useful for testing and debugging.

- <code>PUT</code> **uploads an enclosed entity under a supplied URI.** In other words, it **puts** data at a specific location. If the URI refers to an already existing resource, it’s replaced with the new one. If the URI does not point to an existing resource, then the server creates the resource with that URI.

- <code>DELETE</code> **deletes an object** at a given URL.

Note that while most forms are sent from the POST method, the GET method is also used sometimes with the entries of the form appended to the URL, as in arguments like this:

However, sending forms with a POST request is generally better because:

1. The amount of data that can be sent via a post request is unlimited.

2. The form’s fields are not shown in the URL.

> **Note: URIs & URLs**
>
> - **Uniform Resource Locators (URLs)** URLs are used to identify an object over the web. RFC 2396. A URL has the following format: <code>protocol://hostname:port/path-and-file-name</code>
>
> - **Uniform Resource Identifiers (URIs)** can be more specific than URLs in such a way that they can locate fragments within objects too RFC 3986. A URI has the following format: <code>http://host:port/path?request-parameters#nameAnchor</code>. For instance, <code>https://www.educative.io/collection/page/10370001/6105520698032128/6460983855808512/#http-methods</code> is a URI.

## URL

This is the location that any HTTP method is referring to.

## Version

The HTTP version is also specified in the request line. The latest version of HTTP is HTTP/2.

## The Anatomy of HTTP Header Lines

The HTTP request line is followed by an HTTP header. A lot of HTTP headers exist! We’ll be covering the most important ones in this lesson. However, if you’re interested, you can read further about all of them.

- The first header line specifies the <code>Host</code> that the request is for.

- The second one defines the type of HTTP <code>Connection</code>. It’s Non-persistent in the case of the following drawing as the connection is specified to be closed.

- The <code>user-agent</code> line specifies the client. This is useful when the server has different web pages that exist for different devices and browsers.

- The <code>Accept-language</code> header specifies the language that is preferred. The server checks if a web page in that language exists and sends it if it does, otherwise the server sends the default page.

- The <code>Accept</code> header defines the sort of response to accept. It can be anything like HTML files, images, and audio/video.

