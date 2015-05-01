# Introduction #

This document describes the technical architecture of Symbee.

# Details #

Overall Architecture



Symbee is based on Peer to Peer communication. The Symbee server keeps track of all the logged in clients and their public IP address. When users log in to their Symbee client, the client logs in their respective Gmail accounts using Smack libraries and then logs in to the Symbee server. When the client needs to connect to its peer, it requests the server to establish a secure peer to peer connection between the two peers, once established the peers can communicate to each other directly.

Symbee primarily consists of two components. The Symbee server and the Symbee client.

Symbee Server



The Symbee Server is a java socket acceptor program that tracks Symbee clients and their status. the Server accepts SSL socket connections requests from clients and authenticates them against their Google accounts. The server also keep tracks of a user's buddy list and its status. When a client requests a P2P connection initiation with a buddy, the server verifies that the user is indeed in the buddy list and instructs both the clients to initiate a direct connection with each other. The connection between the peers is established using one-time use only token provided  by the server. The server also keeps track of users that are online, offline etc.

Symbee Client




Symbee client is Java WebStart client. The client can be launched using the vd.jnlp descriptor file. The client user interface is built using Swing libraries compatible with JDK 1.6. The client allows users to log in to Symbee server using their Google account credentials. The client communicates with the symbee server over ssl requesting tokens to connect to peers. The client on receiving the token initiates a direct P2P connection with the peer over an encrypted datagram socket. Once the connection is established, the Peers communicate directly for file requests etc.