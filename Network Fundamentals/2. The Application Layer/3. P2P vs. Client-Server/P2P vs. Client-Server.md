# Quantitative Comparison of P2P with Client-Server

Let’s calculate how long it will take to transmit a file from one server to a number of clients based on both the P2P and server-client architectures. The calculations will be performed based on the following givens.

- A **server** that can upload at a rate of _up<sub>​s</sub>_ where _up<sub>​s</sub>_ is the upload speed in bits/second.

- There are _N_ **clients** all wanting to download the same file from the server. Client _i_ can upload at a rate of _up<sub>​i</sub>_ bits/second and download at a rate of _dwn<sub>​i</sub>_ bits/second.

- The size of the file that all the peers want is _S_.

# Client-Server

Let’s start with the client-server architecture. The following can be observed.
