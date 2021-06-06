# cURL

cURL (pronounced ‘curl’) is a command-line tool that transfers data to or from a server. The transfer can be based on a vast set of protocols, so we’ll be seeing cURL a lot. It’s perfect for our purposes because it doesn’t require live user interaction. cURL stands for “Client URL.” You can read more about cURL on its [manpage](https://curl.haxx.se/docs/manpage.html).

# Explanation

Let’s learn about all of its components.

- <code>curl</code> is the name of the command that tells the terminal that this is a curl command.

- The --head flag or -I in short, tells cURL to send an HTTP request with the head method. In other words, the entity-body of the HTTP message is not fetched.

- The -silent flag tells cURL to not display the progress meter. The progress meter is interpreted as an error on our platform, which is why we decided to remove it. The command is perfectly fine without this flag otherwise.

We encourage you to explore the cURL command. You can find a list of all the flags under the ‘options’ heading on cURL’s [manpage](https://curl.haxx.se/docs/manpage.html). Try different websites and different flags and see what you get!
