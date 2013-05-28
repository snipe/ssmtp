SSMTP - Secure Simple Mail Transport Protocol
=====

Summary
-------
Email as we know it just doesn't work anymore. Fighting spam has become a losing game for email administrators and passwords are insecure and easily stolen. 

We're working on gathering requirements for a new email protocol, one that is easy to implement, easy to use (as an end-user), and is more secure. We don't have all the answers yet, but we're trying to work some of that out here. Feel free to contribute if you have any ideas! 

Rough Requirements
--------
- Web of Trust
- Key exchange
- Possible multiple tiers of trust/keys: 
-- Well Trusted: good friends/colleagues, always gets through
-- Known: Newsletters, people you've just met and want to hear from, but you don't know well
-- Unknown: probably spam, but might not always be

Use Cases to Consider
--------
- Slow-adopting enterprise - need sane fallbacks, but not so sane that they discourage adoption
- User gets hacked - they need to revoke their own keys, people with their public key need to be able to invalidate it (and possibly notify the user)
- People will try to hack this, of course. How, and how can we mitigate? 
- Like spam filters of today, how do I let a legit stranger contact me and not get caught in spam traps?

Disorganized thoughts
--------
- Backwards Compatibility with SMTP?
- Distributed By Nature?
- Mobile/Multi-device friendly?
- Consider ammending/usurping/replacing IMAP as well? 
- Can it just be a SpamAssassin plugin with a distributed friend-network component?
- Is it just SMTP with some new headers?
