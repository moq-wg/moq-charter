# Name: Media over QUIC
## Description

Media over QUIC (moq) will work on solution for a simple low-latency 
media delivery protocol for ingest and distribution. 
This work may address use cases including live streaming, gaming, and 
media conferencing and allows efficient scaling. The solution supports 
both web browsers and simple devices that don’t contain embedded browsers. 
 
The work focuses on building protocol mechanisms for publication of media 
and ways to identify and receive the media.

The media publication protocol will be a push protocol for sending 
media including audio, video, and timed metadata.
The common protocol for publishing media over ingest and distribution 
will support:

* one or more media formats, 
* an interoperable way to request media and encodings,
* rate adaption strategies based on changing codec rates, changing chosen media encoding/qualities,  
* a cache friendly media mechanisms. 

The mechanism to name and receive media will enable:

* Requesting server start sending media related to given point in the stream
* Cue points
* Integration with captions
* Selection of desire encoding ( choosing language, bit rate , etc ) 

Media will be mapped onto underlying QUIC mechanisms (QUIC Streams and/or
QUIC datagrams) and can be used over raw QUIC or WebTransport.

The proposed solution provides extensibility for supporting different 
media formats and shall specify a mandatory to implement media format to ensure interoperability. Support for multiple media types, media encodings shall be proposed, in addition to a simple method of authentication to access media as well as carrying information for additional decryption of media payloads where required.
  
The MOQ architecture allows for the use of optional relays as first 
class elements of the design. The media publication protocol can 
leverage on-path relays/caches wherever applicable to improve the 
media quality. Media is encrypted, possibly end-to-end encrypted 
for certain usecases. The keying mechanisms for media confidentiality
is however outside the scope of this working group. Even when media is 
end-to-end encrypted, the relays can access metadata needed for caching
such as timestamp, making media forwarding decisions (such as drop or 
delay under congestion) and so on.
 
This working group will not propose changes to underlying QUIC 
transport, but may propose requirements for QUIC extensions to the QUIC WG. This working group will not define signaling mechanisms for discovery of relay or media producers or consumers. 
 
This working group will coordinate with the QUIC and WebTransport working 
groups as needed. It will liaise with MPEG-DASH, and W3C WebTransport 
as appropriate. 

## Required Details
- Status: WG Forming
- Responsible AD: TBD ART AD
- BOF proponents: TBD
- BOF chairs: TBD
- Number of people expected to attend: 70
- Length of session (1 or 2 hours): 2 hours
- Conflicts (whole Areas and/or WGs)
   - Chair Conflicts: TBD
   - Technology Overlap: TBD
   - Key Participant Conflict: TBD

## Information for IAB/IESG

At IETF 113 a non WG forming BOF was held to discuss the idea of delivering media over QUIC which had participations from 58 pariticipants across realtime conferencing and streaming industries. Since then 
we have had 2 follow up meetings to work on the charter, each bringing in contributions from around 30 participants. There has been consistent interest and participation in this work from developers associated with widely deployed applications including Twitch, Facebook, Webex, Haivison.


## Agenda
   - TBD

## Links to the mailing list, draft charter if any, relevant Internet-Drafts, etc.
   - Mailing List: https://www.ietf.org/mailman/listinfo/moq
   - Draft charter: https://github.com/moq-wg/moq-charter
   - Relevant drafts: Following drafts were submitted as part of Non WG forming BOF at IETF113
      - https://datatracker.ietf.org/doc/draft-gruessing-moq-requirements/
      - https://datatracker.ietf.org/doc/draft-jennings-moq-quicr-proto/
      - https://www.ietf.org/archive/id/draft-lcurley-warp-00.html
      - https://www.ietf.org/archive/id/draft-kpugin-rush-01.html
      - https://www.ietf.org/archive/id/draft-jennings-moq-quicr-arch-00.html