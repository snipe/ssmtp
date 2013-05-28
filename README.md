SSMTP - Secure Simple Mail Transport Protocol *
=====

Summary
-------
Email as we know it just doesn't work anymore. Fighting spam has become a losing game for email administrators and passwords are insecure and easily stolen. 

We're working on gathering requirements for a new email protocol, one that is easy to implement, easy to use (as an end-user), and is more secure. We don't have all the answers yet, but we're trying to work some of that out here. Feel free to contribute if you have any ideas! 

Whil we definitely aim to look to the research and brilliance of others (such as DJB with Internet Mail 2000), we want to approach this with fresh eyes, taking into consideration the current state of spam, hacking, phishing and spoofing, and where trends indicate it will go from here. We're starting from the business requirements first, and seeing where this takes us. 


Rough Requirements
--------
- Web of Trust
- Key exchange
- Possible multiple tiers of trust/keys: 
    - Well Trusted: good friends/colleagues, always gets through
    - Known: Newsletters, people you've just met and want to hear from, but you don't know well
    - Unknown: probably spam, but might not always be

Use Cases to Consider
--------
- Slow-adopting enterprise - need sane fallbacks, but not so sane that they discourage adoption
- User gets hacked - they need to revoke their own keys, people with their public key need to be able to invalidate it (and possibly notify the user)
- People will try to hack this, of course. How, and how can we mitigate? 
- Like spam filters of today, how do I let a legit stranger contact me and not get caught in spam traps?
- DDoS mitigation

Disorganized thoughts
--------
- Backwards Compatibility with SMTP?
- Distributed By Nature?
- Mobile/Multi-device friendly?
- Consider ammending/usurping/replacing IMAP as well? 
- Can it just be a SpamAssassin plugin with a distributed friend-network component?
- Is it just SMTP with some new headers?

Useful Articles
--------
- http://en.wikipedia.org/wiki/Internet_Mail_2000
- http://en.wikipedia.org/wiki/Proof-of-work_system (+ certs?)


**THIS NAME WILL PROBABLY CHANGE.** We know Debian ships with an SSMTP :P One problem at a time. "There are only two hard things in programming: naming things, cache invalidation and off-by-one errors."