Yealink file encryption: a case study in rolling your own crypto
================================================================

### Authors: Cal Leeming, Travis Cross
### Date: TBD

Summary
-------

[ Yealink tool is broken (bad key generation).  Yealink crypto design
is broken (ECB mode encryption, public symmetric keys).  Zero-touch
provisioning is a hard problem. ]

A detour: the conceit of zero-touch provisioning
------------------------------------------------

[ Describe what ZTP is and why people want it.  Describe why it's hard
and easy to do wrong. ]

A non-solution to the zero-touch provisioning problem
-----------------------------------------------------

[ Describe how Yealink responded and touch on why it would be
insufficient even in theory.  Describe what motivated Yealink to make
the mistakes that follow. ]

How Yealink's tool works
------------------------

[ add screen shots of the full process and a graphviz diagram of the
key relationships. ]

What's the worst way you could generate a password?
---------------------------------------------------

[ Design a broken system that just happens to match what Yealink
does. ]

What's the worst way to do a key exchange?
------------------------------------------

[ Design a broken system that just happens to match what Yealink
does. ]

Results from reverse engineering
--------------------------------

[ Describe the process of reversing their binary and what we found
that it does in detail.  Describe tools used for reverse
engineering. ]

A real solution to the zero-touch provisioning problem
------------------------------------------------------

[ Describe a TPM-based solution where the manufacturer acts as a CA
and signs the public cert of each phone.  The CN would contain the MAC
address.  A service provider knowing just the MAC to expect (and the
manufacturer's public key) could then verify that the phone is
authentic. ]

See also
--------

https://github.com/traviscross/yealink-keycrack

References
----------

* [ how to generate keys securely ]
* [ why ECB mode is not a good idea ]
* [ key wrapping encryption modes ]
* [ LFSR ]
