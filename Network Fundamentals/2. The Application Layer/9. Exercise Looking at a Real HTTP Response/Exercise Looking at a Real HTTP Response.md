# cURL

cURL (pronounced ‘curl’) is a command-line tool that transfers data to or from a server. The transfer can be based on a vast set of protocols, so we’ll be seeing cURL a lot. It’s perfect for our purposes because it doesn’t require live user interaction. cURL stands for “Client URL.” You can read more about cURL on its [manpage](https://curl.haxx.se/docs/manpage.html).

# Explanation

Let’s learn about all of its components.

- <code>curl</code> is the name of the command that tells the terminal that this is a curl command.

- The <code>--head</code> flag or <code>-I</code> in short, tells cURL to send an HTTP request with the <code>head</code> method. In other words, the entity-body of the HTTP message is not fetched.

- The <code>-silent</code> flag tells cURL to not display the progress meter. The progress meter is interpreted as an error on our platform, which is why we decided to remove it. The command is perfectly fine without this flag otherwise.

We encourage you to explore the cURL command. You can find a list of all the flags under the ‘options’ heading on cURL’s [manpage](https://curl.haxx.se/docs/manpage.html). Try different websites and different flags and see what you get!

# Sample Output

The output of this command is an HTTP response such as the following. Notice the HTTP response code and the headers.

```
HTTP/1.1 200 OK
Content-Encoding: gzip
Accept-Ranges: bytes
Cache-Control: max-age=604800
Content-Type: text/html; charset=UTF-8
Date: Mon, 23 Sep 2019 06:48:39 GMT
Etag: "1541025663"
Expires: Mon, 30 Sep 2019 06:48:39 GMT
Last-Modified: Fri, 09 Aug 2013 23:54:35 GMT
Server: ECS (ord/5726)
X-Cache: HIT
Content-Length: 606
```
