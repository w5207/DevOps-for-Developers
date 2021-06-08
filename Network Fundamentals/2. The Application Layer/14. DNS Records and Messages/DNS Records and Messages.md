# Resource Records

The DNS distributed database consists of entities called **RR**s, or **Resource Records.**

## Format

RRs contain some or all of the following values:

- **Name** of the domain.

- **Resource data (RDATA)** provides information appropriate for the type of resource record.

- **Type** of the resource record. We will discuss these shortly.

- **Time-to-live (TTL)** is how long the record should be cached by the client in seconds.

- **DNS Class.** There are many types of classes but we’re mainly concerned with **<code>IN</code>** which implies the ‘Internet’ class. That’s what all of our upcoming examples use so we won’t be discussing it again. Another common value for the DNS Class is **<code>CH</code>** for ‘CHAOS’. The CH class is mostly used for things like querying DNS server versions.

# Types of resource records

- **Address** type or **<code>A</code>** addresses contain IPv4 address to hostname mappings. They consist of:

  - The **<code>name</code>** is the hostname in question.

  - The **<code>TTL</code>** in seconds.

  - The **<code>type</code>** which is **<code>A</code>** in this case.

  - The **<code>RDATA</code>** which in this case is the IP address of the domain.

  - **Example:** **<code>educative.io. 299 IN A 104.20.7.183</code>** where **<code>educative.io</code>** is the name, 299 is the TTL in seconds, **<code>IN</code>** is the class, **<code>A</code>** is the type of the RR, and **<code>104.20.7.183</code>** is the **<code>RDATA</code>**.

- **Canonical name** or **<code>CNAME</code>** records are records of alias hostnames against actual hostnames. For example if, **<code>ibm.com</code>** is really **<code>servereast.backup2.com</code>**, then the latter is the canonical name of **<code>ibm.com</code>**.

  - The **<code>name</code>** is the alias name for the real or ‘canonical’ name of the server.

  - The **<code>RDATA</code>** is the canonical name of the server.

  - **Example:** **<code>bar.example.com. CNAME foo.example.com.</code>**

- **Mail Exchanger** or **<code>MX</code>** records are records of the server that accepts email on behalf of a certain domain. We have seen this one before!

  - The **<code>name</code>** is the name of the host.

  - The **<code>RDATA</code>** is the name of the mail server associated with the host.

  - Example: **<code>educative.io IN MX 10 aspmx2.googlemail.com.</code>**

These resource records are stored in text form in special files called **zone files.**

# DNS Messages

There are a few kinds of DNS messages, out of which the most common are **query** and **reply**, and both have the same format. Study the following slides for a detailed overview of a DNS message.

There are also **zone transfer request and response.** But, those are not used by common clients. Backup or secondary DNS servers use them for **zone transfers,** which are when zone files are copied from one server to another. This takes place over TCP.

