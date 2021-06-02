# Quantitative Comparison of P2P with Client-Server

Let’s calculate how long it will take to transmit a file from one server to a number of clients based on both the P2P and server-client architectures. The calculations will be performed based on the following givens.

- A **server** that can upload at a rate of _up<sub>​s</sub>_ where _up<sub>​s</sub>_ is the upload speed in bits/second.

- There are _N_ **clients** all wanting to download the same file from the server. Client _i_ can upload at a rate of _up<sub>​i</sub>_ bits/second and download at a rate of _dwn<sub>​i</sub>_ bits/second.

- The size of the file that all the peers want is _S_.

# Client-Server

Let’s start with the client-server architecture. The following can be observed.

- Since _N_ clients each want a file of size _S_, the server will have to upload _NS_ bits. The upload rate of the server is _up<sub>​s</sub>_ so the server will take at least <img src="https://latex.codecogs.com/gif.latex?\frac{NS}{up_{s}}" title="\frac{NS}{up_{s}}" /> time to transmit the file to all NN clients.

- The client with the lowest download rate (_dwn<sub>min</sub> = min(dwn<sub>i</sub>)_) will take at least <img src="https://latex.codecogs.com/gif.latex?\frac{S}{dwn_{min}}" title="\frac{S}{dwn_{min}}" /> time to download the full file.

So, in total the time taken to transmit the file will be the maximum of both of the times above, i.e.:
<img src="https://latex.codecogs.com/gif.latex?max\{\frac{NS}{up_{s}},&space;\frac{S}{dwn_{min}}\}" title="max\{\frac{NS}{up_{s}}, \frac{S}{dwn_{min}}\}" />

# P2P

We can make the following observations:

- Initially, only the server has the file. It has to throw the file out into the network and to do that, it will take at least <img src="https://latex.codecogs.com/gif.latex?\frac{S}{up_{s}}" title="\frac{S}{up_{s}}" /> time. While the file is being sent out into the network of peers, they start to distribute it amongst themselves.

- The peer with the lowest download rate (_dwn<sub>min</sub>_) will take at least <img src="https://latex.codecogs.com/gif.latex?\frac{S}{dwn_{min}}" title="\frac{S}{dwn_{min}}" /> time to download the full file.

- The file cannot be transmitted faster than the total upload speed of the entire network: (_up<sub>sum</sub> = {up<sub>1</sub>+up<sub>2</sub>+up<sub>3</sub>+...+up<sub>N</sub>}_). Since the file has to be distributed to all _N_ peers, NSNS bits have to be transmitted, that will take <img src="https://latex.codecogs.com/gif.latex?\frac{NS}{up_{sum}}" title="\frac{NS}{up_{sum}}" /> time.

Therefore, the time taken in total to distribute a file of size _S_ to _N_ peers is:
<img src="https://latex.codecogs.com/gif.latex?max\{\frac{S}{up_{s}},&space;\frac{S}{dwn_{min}},&space;\frac{NS}{up_{sum}}\}" title="max\{\frac{S}{up_{s}}, \frac{S}{dwn_{min}}, \frac{NS}{up_{sum}}\}" />

Note that as the number of clients/peers, _N_, grows, the time taken by the client-server architecture also grows. Here is a graph of how the distribution time grows for each architecture as the number of clients/peers grow:
![Graph of How p2p Scales vs Client-Server attributed to:https://pdfs.semanticscholar.org/3de3/1a9b45a3d071c638574117af8e046b578004.pdf](3.png)

**P2P networks are extremely mathematically scalable.** The resources of a P2P system grows with the number of peers in the system. Thus, applications with P2P architecture are self-scaling.
