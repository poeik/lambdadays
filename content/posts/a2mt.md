---
title:   Suspension - the magic behind composability Kyo Monad
date:    2025-06-13
tags:    [lambdadays]
aliases: [kyomonad]
---

> Algebraic effect handling library

Kyo:

- monadic effect system based on algebraic effects
- implemented in Scala 3
- suspends side effect & multi-shot continuation
    - side effects are handled with special handlers
    - you can add more effects to already existing suspension, it will just be
      appended using flatMap
    - the inner effect is always ID
    - a computation can only be evaluated when no effect is left

## Pending type

> In Kyo, computations are expressed via the infix type <, known as "Pending"

```scala
infix seald trait <[+A, -S]
```

In front of `<` we have the result of the computation, on the right side the
effects which still need to be run:

E.g.:

```scala
type X = Int < IO
``` 

=> Computation needs IO-effect to create an Int 

## Example effects

Any (`Any`)

- the empty effect, it needs no handler. This is automatically applied if you
  use `map`, which makes it basically a `flatMap`. Therefore it is exactly the
  same.

Environments-Effects (`Env`)

- has a `get` function which gives access to the environment
- has a `run` function which handles the effect

Abort-Effect (`Abort`)

- has a fail method, which aborts the computation and returns `Nothing` (bottom
  type)
- has a run method to handle the effect

## The laws of Kyo

- satisfies the monadic laws
- pure handling
    - calling handle with no effects is the same as just running the computation
- effect handling
    - ???
- handler rotation
    - if the current handler is not the most outer effect, it is just passed to
      the continuation

## Bridging the real-world gap

- stack safety handled by safe-points


## References

- [https://www.lambdadays.org/lambdadays2025/flavio-brasil](https://www.lambdadays.org/lambdadays2025/flavio-brasil)
- [GitHub](https://github.com/getkyo/kyo/)

