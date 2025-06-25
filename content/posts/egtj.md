---
title:   Choreographic Distributed Systems
date:    2025-06-12
tags:    [lambdadays]
aliases: []
---

> choreographic programming in a distributed system, does the same as a
> choreographer on a dance floor.


## Choreographic Programming

### EPP (End-Point Projection)

```
# Simple handshake protocol

Initiator -> Responder: Hello
Responder -> Initiator: Hello
``` 

> The above description can be automatically compiled down to individual local
> programs.

- So EPP creates a program for each role/node

### HasChor

> [!] This is not yes production ready

> Functional Choreographic Programming library for Haskell

- you write Haskell programs
- `HasChor` depends on Freer Monad
- Functions return `Monad m => Choreo m ()`

Example to create a simple handshake protocol between an `initator` and a `responer`

![[attachments/74c98d0e-21a3-47fc-b467-79720879fe04~1.jpg]]

you can use it like: (with `nodeA` and `nodeB`):

![[attachments/44fb2acf-b4d5-41b9-adfd-ba83b42fefc5~1.jpg]]

## References

- [https://www.lambdadays.org/lambdadays2025/pawel-szulc](https://www.lambdadays.org/lambdadays2025/pawel-szulc)
- [https://github.com/gshen42/HasChor](https://github.com/gshen42/HasChor)
- [HasChor Paper](https://dl.acm.org/doi/10.1145/3607849)

