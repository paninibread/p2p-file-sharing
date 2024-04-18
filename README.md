# P2P File Sharing
Java based peer to peer file sharing software.

### Description
This project aims to develop a peer-to-peer (P2P) file sharing software in Java, similar to BitTorrent, enabling users to share and download files directly from other peers in the network. The software follows a structured protocol for communication between peers, facilitating efficient data exchange and file distribution. 

It provides a decentralized approach to file sharing, allowing users to exchange files directly with other peers without relying on a central server. By adhering to a standardized communication protocol and leveraging Java's networking capabilities, the software ensures reliable and efficient data transfer in a peer-to-peer environment.

### Features

1. **Handshake Protocol:**
   - The handshake message consists of three parts:
     - Handshake header: An 18-byte string 'P2PFILESHARINGPROJ'.
     - Zero bits: 10-byte zero bits.
     - Peer ID: 4-byte integer representation of the peer ID.
   - The length of the handshake message is fixed at 32 bytes.

2. **Actual Messages:**
   - After handshaking, peers can exchange actual messages.
   - Each actual message consists of:
     - 4-byte message length field.
     - 1-byte message type field.
     - Variable-sized message payload.

3. **Message Types:**
   - **Choke, Unchoke, Interested, Not Interested:**
     - Messages with no payload indicating peer's current state.
   - **Have:**
     - Contains a payload with a 4-byte piece index field indicating the piece the peer has.
   - **Bitfield:**
     - Sent as the first message after handshaking.
     - Contains a bitfield payload representing pieces the peer has.
   - **Request:**
     - Contains a payload with a 4-byte piece index field indicating the requested piece.
   - **Piece:**
     - Contains a payload with a 4-byte piece index field and the content of the piece being sent.

**Implementation:**
   
The software is implemented using Java sockets for establishing connections between peers and facilitating message exchange. A multithreaded architecture is adopted to handle concurrent connections and message processing efficiently. The protocol specification guides the development of message parsing and handling mechanisms.

## Authors

Prashast Sharma - [LinkedIn](https://www.linkedin.com/in/prashast-sharma-690778230/)
