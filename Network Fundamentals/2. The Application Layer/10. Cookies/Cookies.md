# Introduction

You might have heard of the term ‘cookie’ used a lot in the context of computer networks and privacy. Let’s have a closer look at what they are.

HTTP is a stateless protocol, but we often see websites where session state is needed. For instance, imagine you are browsing for products on an e-commerce website. How does the server know if you are logged in or not, or if the protocol is stateless? How does the server know what’s in your shopping cart when checking out if the protocol is stateless? Cookies allow the server to keep track of this sort of information.

# How Cookies Work

- Cookies are **unique string identifiers** that can be stored on the client’s browser.

- These identifiers are **set by the server through HTTP headers** when the client first navigates to the website.

- After the cookie is set, it’s sent along with subsequent HTTP requests to the same server. This **allows the server to know who is contacting it** and hence serve content accordingly.

So the HTTP request, the HTTP response, the cookie file on the client’s browser, and a database of cookie-user values on the server’s end are all involved in the process of setting and using cookies.

# **<code>Set-cookie</code>** Header

Let’s look at how cookies work in a bit more detail. When a server wants to set a cookie on the client-side, it includes the header Set-cookie: value in the HTTP response. This value is then appended to a special cookie file stored on your browser. The cookie file contains:

The website’s domain
The string value of the cookie
The date that the cookie expires (yes, much like actual cookies, they do expire)
Have a look at the following slides to see how cookies work in practice.
