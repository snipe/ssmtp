[![Stories in Ready](http://badge.waffle.io/snipe/ssmtp.png)](http://waffle.io/snipe/ssmtp)  
SSMTP - Secure Simple Mail Transport Protocol *
=====

Summary
-------
Email as we know it just doesn't work anymore. Fighting spam has become a losing game for email administrators and passwords are insecure and easily stolen. 

We're working on gathering requirements for a new email protocol, one that is easy to implement, easy to use (as an end-user), and is more secure. We don't have all the answers yet, but we're trying to work some of that out here. Feel free to contribute if you have any ideas! 

While we definitely aim to look to the research and brilliance of others (such as DJB with Internet Mail 2000), we want to approach this with fresh eyes, taking into consideration the current state of spam, hacking, phishing and spoofing, and where trends indicate it will go from here. We're starting from the business requirements first, and seeing where this takes us. 

In discussing this with colleagues (over beer and brunch - very technical stuff), we realized that several of the social networks have gotten it pretty close: 

On Facebook, if someone you're friends with sends you a Facebook Message, it goes into your FB Inbox and you are alerted that you have a new message. If someone you're not Facebook friends with sends you a message, it gets filed in Facebook's version of a pseudo-SPAM box, labeled "Other". Messages from Facebook fan pages you "liked" also appear here and bypass your Inbox altogether.

On Twitter, messaging is much simpler. If you are following someone on Twitter, they can send you a direct (private) message. If you do not follow them, they cannot privately message you. If you have blocked them, you will not see @replies to you, and they will be prevented from sending you direct messages.

So the challenge here is partly how to handle those layers of relationships and trust. We certainly don't want a corporation holding the keys to those relationships, so we need something federated. 


Rough Requirements
--------
- Web of Trust
- Key exchange
- Possible multiple tiers of trust/keys: 
    - Well Trusted: good friends/colleagues, always gets through
    - Known: Newsletters, people you've just met and want to hear from, but you don't know well
    - Unknown: probably spam, but might not always be

Use-Cases to Consider
--------
- Slow-adopting enterprise - need sane fallbacks, but not so sane that they discourage adoption
- User gets hacked - they need to revoke their own keys, people with their public key need to be able to invalidate it (and possibly notify the user)
- People will try to hack this, of course. How, and how can we mitigate? 
- Like spam filters of today, how do I let a legit stranger contact me and not get caught in spam traps?
- DDoS mitigation
- Chain of Custody (losing BCC headers in IMAP Sent items, etc)

Disorganized thoughts
--------
- Backwards Compatibility with SMTP?
- Distributed By Nature?
- Mobile/Multi-device friendly?
- Consider amending/usurping/replacing IMAP as well? 
- Can it just be a SpamAssassin plugin with a distributed friend-network component?
- Is it just SMTP with some new headers?

Useful Articles
--------
- http://en.wikipedia.org/wiki/Internet_Mail_2000
- http://en.wikipedia.org/wiki/Proof-of-work_system (+ certs?)
- http://en.wikipedia.org/wiki/Thawte#Web_of_trust


**THIS NAME WILL PROBABLY CHANGE.** We know Debian ships with an SSMTP :P One problem at a time. "There are only two hard things in programming: naming things, cache invalidation and off-by-one errors."