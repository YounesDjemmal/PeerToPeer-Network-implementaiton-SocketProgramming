# PeerToPeer-Network-implementaiton-SocketProgramming
Each data object to be shared is identified by a 32 hex-character key that is the MD5 hash
of the data object’s content. We will give you the keys; you will not need to compute them.
For our purposes, we will assume that these hash value keys are unique. You will also not
need to keep actual files, since the point of this assignment is to model the tracking and
finding of data objects, but not really transmit data files.
Each P2PClient keeps two data structures, a Content List (CL), which is simply a list of the
keys for the data objects the client currently holds, and a Content Originator List (COL)
which is a list of the keys for data objects that this Client has received from other Clients.
For each key in the COL, the IP address and port number of the sending client is kept.


Clients may delete data objects from their content list at any time. When they do so, the
corresponding key is immediately removed from the CL (but not from COL). News of the
deletion is not propagated any further; other clients are not told that an object has been
deleted. As a result, the COL list at other peers may be out of date, i.e., a COL list may
indicate that a particular peer has a data object when, in fact, that peer has already deleted
the content. This leads to a searching and routing problem, checking to see if a peer has a
data object, and if not, discovering other peers to ask.
The P2PTracker is the mechanism that allows a P2PClient to find out about currently
registered peers in the system. The P2PTracker keeps a list of all currently registered peers
(via a Client ID and the IP address and port number for the client) and provides that list
upon request. The P2PTracker also sends a start command to all peers who are registered,
in order to trigger the start of peer action, and to enforce some command ordering across
peers, which makes it easier to test.

Full System Description in pdf file.
