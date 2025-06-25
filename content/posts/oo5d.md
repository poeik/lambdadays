---
title:   Your docs are a program
date:    2025-06-12
tags:    [lambdadays]
aliases: []
---

> Just like programs, docs often have a "source to artifact"-pipeline

E.g. you write markdown, and it is compiled to HTML.

So you should be able to:

- Compile docs
- integrate to CI pipelines
- manipulate things
- To run a compiled documentation (or at least some interaction in it)

## Types of docs

- Tutorial:         Getting started
- Conceptual guide: Motivation and model
- How-to:           Task focused
- Reference:        Code focused

### Reference docs

- Written in source code, and then used in the IDE
- [Doctest](https://github.com/sbt-doctest/sbt-doctest) can verify them
    - can be integrated into a build tool
    - it produces & runs tests based on the code snippet

![[attachments/Pasted image 20250612104913.png]]

=> This test fails, because the result is not `Option(String)` but `String`

### Guides

> Often written as Markdown

> [MDOC](https://scalameta.org/mdoc/) does checks on Markdown

- runs Scala snippets in Markdown files
    - Snippets are annotated with `scala mdoc`
- Variable substitution e.g. replace the version in a md file using @@VERSION@@
- You can write extra functions, which adds some additional things to a snippet,
  e.g. displaying an image


### Interactive docs

[Livebook](https://livebook.dev/)

- Enables to run and modify code in the generated HTML documentation out of
  markdown

### Programming Docs

> Racket is a language to write DSLs

- it is easy to write a parser, tokenizer and interpreter
- [Pollen](https://docs.racket-lang.org/pollen/) is a markup language (similar
  to markdown) written in Racket
- It lets you easily execute Racket functions

![[attachments/Pasted image 20250612112033.png]]

- you import a Racket file (`catname.rkt`), and you are able to call functions of it. E.g. `catname` in this case.
- `catname` would be able to raise an error if `Cinder` is invalid

## References

- [https://www.lambdadays.org/lambdadays2025/zainab-ali](https://www.lambdadays.org/lambdadays2025/zainab-ali)
- [Slides](https://kebab-ca.se/presentations/2025-06-12-your-docs-are-a-program/main.html)


Further reading:

- [A core calculus for documents](https://cs.brown.edu/~sk/Publications/Papers/Published/ck-core-calc-doc-lambda-ultimate-doc/paper.pdf)
- [Racket intro](https://beautifulracket.com/)

