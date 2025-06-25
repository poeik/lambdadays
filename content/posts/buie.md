---
title:   Haskell is eating my rails app from the inside out
date:    2025-06-12
tags:    [lambdadays, haskell]
aliases: []
---

Two approaches:

1. Replacing standalone services written in Ruby with Haskell
2. Haskell interop with already existing Ruby code


## Challenges & Successes

Challenges:

- Slower development initially not much to build on
- learning curve

Successes:

- Blended with feature work
- surpassed JS in 1 year
- surpassed Ruby in 2 years

## Standalone Services

- duplicate code (in Ruby & Haskell)

## Language Interop

> Using dll/so!

- almost all languages interop with C code anyway
- Haskell can compile to a binary library

### Benefits of Interop

- Function calls between languages
- data not serialized => Ruby objects from the Haskell C method!
- Migrating small pieces possible!
- Run ruby tests on Haskell code
- it allows to delete ruby version immediately

### Use Haskell in ruby code

#### How does it work on Haskell side?

1. Change parameter from ruby's C representation to Haskell types
2. Run Haskell logic
3. Change return value from Haskell type to Ruby's C representation

##### Generalizing type decoding/encoding

- use a type class `Decodable`/`Encodable` and instantiate them for all types

#### How does it work on Ruby side?

- `call_haskell(module_name, method_name, arg_array)` is the only exposed
  function, which is able to call a Haskell function

### Run Ruby in Haskell code

> Using a code generation script

## References

-  [https://www.lambdadays.org/lambdadays2025/brian-carroll](https://www.lambdadays.org/lambdadays2025/brian-carroll)

