---
title:   Scala and Typescript Synergy
date:    2025-06-13
tags:    [lambdadays]
aliases: []
---

Collaborative editing by:

- Consistent auto-merging rule
    - conflicts are fixed for each user in the same way
- Operations (insert, delete) must be
    - commutative: it does not matter which operation appears first
    - Idempotency: repeated operations produce the same result

    => This properties are implemented using operational transformation

Cursor synchronization:

- each users cursors is shown for each other user
- inserting or deleting characters also affects the positions of the cursors


Undo/redo:

- define reverse operations and put them for each operation on the stack


## References

- [https://www.lambdadays.org/lambdadays2025/mihaela-gheorgheroman](https://www.lambdadays.org/lambdadays2025/mihaela-gheorgheroman)
- [https://en.wikipedia.org/wiki/Operational_transformation](https://en.wikipedia.org/wiki/Operational_transformation)

