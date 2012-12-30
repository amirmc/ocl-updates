Imrunsil is a Distributed Idempotent Provenance-aware database (DIPA). Planning to use this with XCP and Xen Cloud.

Discussions and design work of the consistency model have taken place. Dave,
Anil and Raphael are working on understanding the best way to name end-
points and bind to them. Reading Plan9 again, but coming to the conclusion
that it should be possible to merge the XAPI (high-level) database with low-
level Xenstore. Raphael suggests that if the leaves of the db are Mirage
nodes, that the unikernel state could also be stored as part of the tree.

Refactoring `xenstore` to not depend on Xen so much. The Xenstore database is
purely functional already, and Dave and Anil have been refactoring it into a
standalone library that separates the protocol from the database
functionality. This should make it easier to re-use the database (perhaps as
a functor) for other persistent storage tasks.

Current status: *Still planning*