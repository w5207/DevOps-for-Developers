# Finding The Authoritative Name Server Using **<code>host</code>**

```
host -t ns google.com
```

**<code>host</code>** is a DNS lookup utility. It is normally used to map hostnames to IP addresses. However, with a combination of flags, it can be programmed to perform a myriad of DNS-related tasks.

The syntax of the command above, for instance, is

```
host -t ns hostname.com
```

- **<code>host<code>** invokes the host command

- **-t** is the **type** flag. It is used to specify the type of the command. Check out [host’s manpage](https://linux.die.net/man/1/host) for a list of all the types available.

- **<code>ns</code>** specifies the type. It stands for the name server in this case.

- **<code>hostname.com</code>** can be any website of your choice.

# Checking What Your Local DNS Server Is

To check the IP address of your local DNS server, run the following command on UNIX based machines. If you’re on a mobile machine, try [www.whatsmydnsserver.com](http://www.whatsmydnsserver.com/). There are a lot of instructions available for Windows machines online.

```
cat /etc/resolv.conf
```

## Output

Here is what the output may look like

```
## Dynamic resolv.conf(5) file for glibc resolver(3) generated by resolvconf(8)
## DO NOT EDIT THIS FILE BY HAND -- YOUR CHANGES WILL BE OVERWRITTEN
nameserver 169.254.169.254
search c.educative-exec-env.internal google.internal
```

You can safely ignore the first two lines since they are comments. On the third line, **<code>nameserver</code>** shows the IP address of the local DNS server. On the last line, **<code>search</code>** represents the default search domain that is used to resolve a query for a domain with no suffix (for example, www.facebook).

> **Note:** Educative’s code widgets run on a remote server. The code runs there, the output is then sent back to your machine and displayed. So, the DNS server shown here is local to the server that runs Educative’s code.
