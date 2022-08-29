#Charter for Media over QUIC

Media over QUIC (moq) will develop a simple low-latency media delivery solution
for ingest and distribution of media.  This solution addresses use cases including live
streaming, gaming, and media conferencing and will scale efficiently. The
solution will be implementable in both browser and non-browser endpoints.

The work focuses on building protocol mechanisms for publication of media
and means to identify and receive the media.

The media publication protocol will enable sending
media including audio, video, and timed metadata, such as closed captions and
cue points.
The common protocol for publishing media for ingest and distribution
will support:

* one or more media formats,
* an interoperable way to indicate the media and the media format being sent,
* rate adaptation strategies based on changing codec rates, changing chosen media
encoding/qualities, or other mechanisms
* cache friendly media mechanisms

The mechanism to name and receive media will enable:

* Requesting the server start sending media related to given point in the stream
* Selection of desired encoding (choosing language, bit rate, etc)

Media will be mapped onto underlying QUIC mechanisms (QUIC streams and/or
QUIC datagrams) and can be used over raw QUIC or WebTransport.

The proposed solution will provide extensibility for supporting different media
formats and will support multiple media types and media encodings.


The working group will define MoQ so that the media publication protocol 
can leverage coordinating relays, caches, or replication points wherever applicable 
to improve the delivery performance.

The solution will specify a simple method for clients to authenticate
to the relay or server to transmit or receive media.
Media will be encrypted at the transport layer using the standard QUIC
mechanisms.  Media content may be end-to-end encrypted in certain use cases,
where the "end-to-end" keys are available to media sources and consumers, but
not relays.  Even when media is content end-to-end encrypted, the relays can access
metadata needed for caching (such as timestamp), making media forwarding
decisions (such as drop or delay under congestion), and so on.  Such media
metadata will be authenticated and integrity-protected end-to-end.  Mechanisms
for establishing keys for these end-to-end protections are outside the scope of
this group.

This working group will not propose changes to the underlying QUIC transport, but
may propose requirements for QUIC extensions to the QUIC WG. This working group
will not define signaling mechanisms for discovery of relay or media producers
or consumers.

This working group will coordinate with the QUIC, WebTransport, and MOPS working
groups as needed. It will liaise with MPEG Systems WG, DASH Industry Forum, and 
W3C WebTransport as appropriate.

## Milestones

* WG adoption of Protocol Specification for Common Media Publication Protocol
over QUIC
* WG adoption of Protocol Specification for the use of the Datagram Extension for Media
Publication Protocol over QUIC
* WG adoption of Protocol Specification for Media Subscription Protocol over
QUIC
* WG adoption of Architecture Specification for a Common Media Delivery
Protocol over QUIC
* WG adoption of Usecases and Requirements document for Media Delivery over QUIC
- decision about whether to forward to IESG for publication to be made later, by
WG consensus
* Forward Protocol Specification for Common Media Publication Protocol over QUIC
draft to IESG
* Forward Protocol Specification for the use of the Datagram Extension for Media Publication
Protocol over QUIC draft to IESG
* Forward Protocol Specification for Media Subscription Protocol over QUIC draft
to IESG
* Forward Architecture Specification for a Common Media Delivery Protocol over
QUIC draft to IESG
