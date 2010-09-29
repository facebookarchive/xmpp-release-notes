==================
XMPP Release Notes
==================

These release notes document
the latest updates to and the newest features
of the XMPP Service.
All updates to the beta tier and production tier will be listed here. 


.. contents::


Update Notifications
====================

An email will be sent to this mailing list
<http://publists.facebook.com/mailman/listinfo/xmpp-updates>
when updates are made to this page.


Accessing the Beta Tier
=======================

Configure your chat client to connect to port 5221
to access the beta tier,
which will have new features that have not been pushed to production yet.

If the beta tier is down for more than one hour
and the latest update is a beta update,
please file a bug in bugzilla.


Update Process
==============

Unless otherwise noted, all changes will
only be applied to new connections.
There will be a transition period where
a new connection can be assigned to
either the new or old version of the code.
During the transition period,
existing clients might be forced offline
with a "<system-shutdown/>" stream error
or simply closing the TCP connection.
In either case, clients should attempt to reconnect.


Update Details
==============

(beta) September 29, 2009
--------------------

  - Miscellaneous stability improvements.
  - Add support for some upcoming features that will be enabled after
    corresponding changes are pushed to other Facebook systems.

(meta) September 18, 2010
-------------------------

  - The release notes have been moved from the Developer Wiki to GitHub.

(prod) July 19, 2010
--------------------

  - We're pushing the latest build once again after resolving some system
    issues. 

(prod) July 16, 2010
--------------------

  - We've reverted back to the previous build due to some stability
    issues. 

(prod) July 14, 2010
--------------------

  - The build from the latest beta is gradually being pushed to the
    production tier. 

(beta) June 30, 2010
--------------------

  - More miscellaneous stability improvements. 

(beta) June 24, 2010
--------------------

  - Miscellaneous stability improvements.
  - IQs sent to full JIDs (node@host/resource) are now processed a bit
    differently. However, there are no valid uses for this type of stanza
    (in Facebook Chat) before or after the change, so correct applications
    should not be affected.
  - Clients will receive IQs notifying them of the messages they send.
    This is an experimental feature. Until further notice, assume that it
    might be disabled or changed at any time, even if it gets pushed to
    production. When interface is finalized, a full description will be
    posted. The purpose of this extension is to allow clients to display
    both sides of a conversation that happens through web chat or another
    client. 

(prod) June 16, 2010
--------------------

  - The latest build is now serving all new connections. Existing
    connections to the previous build will be severed in a few days. 

(prod) June 15, 2010
--------------------

  - The build from the latest beta is gradually being pushed to the
    production tier. 

(beta) June 9, 2010
-------------------

  - Roster remove stanzas for old-style "u123" contacts are no longer
    sent.
  - Old-style "u123" JIDs are no longer accepted for message sends and
    vCard fetches.
  - Roster and vCard requests are parsed a bit more leniently. Roster
    requests containing the XEP-0237 "ver" attribute will be accepted.
  - Clients may request profile pic urls rather than pic content in vCard
    fetches by including a "<want-extval
    xmlns='http://www.facebook.com/xmpp/vcard/photo'/>" element as a
    direct child of the "<vCard xmlns='vcard-temp'/>" element.
  - An Adobe cross-domain policy will be served on the service ports to
    allow Flash clients to connect to the server.
  - Miscellaneous improvements to stability and error handling. 

(prod) May 12, 2010
-------------------

  - The update is complete. All new sessions should be using the new IP
    address with the new software. The old IP will be taken down in a few
    days, and all remaining sessions on it will be closed. 

(prod) April 22, 2010
---------------------

  - The build from the latest beta will be pushed to the production tier
    tomorrow morning.
  - This will be a DNS-based change because we are changing our load
    balancer simultaneously.
  - The old version of the service will remain available at the current IP
    address (69.63.181.104) for a few days. 

(beta) April 5, 2010
--------------------

  - UID-based JIDs are now of the form "-12345@chat.facebook.com" due to
    concerns about the use of the "%" character.
  - Message sends and vCard fetches should continue to work with
    "u12345"-style JIDs, but this support will be removed in the next
    release.
  - Clients that use the DIGEST-MD5 authentication mechanism will receive
    a number of "roster subscription remove" pushes to remove the
    "u12345"-style JIDs. This is to work around a Pidgin behavior: leaving
    old contacts in the buddy list even though they no longer appear in
    the roster. This will be removed in the next release. 

(beta) March 23, 2010
---------------------

  - UID-based JIDs will be of the form "%12345@chat.facebook.com" instead
    of "u12345@chat.facebook.com". This applies to both JIDs in the
    contact list and JIDs assigned to users who use platform
    authentication. Old-style "u12345" JIDs will not be recognized.
  - Connections will be accepted on port 443 in addition to port 5222.
    5222 is still the preferred port. This feature will not be visible
    until the production push.
  - Various minor stability improvements. 

(meta) March 15, 2010
---------------------

  - Stub entry. Preparing release notes page. 
