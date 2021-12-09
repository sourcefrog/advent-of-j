# Advent of Code 2020 in J

## Introduction

J is a very different language; as different from C as is Haskell or Lisp but in
a different direction.

In particular,
[idiomatic J uses no explicit loops](https://code.jsoftware.com/wiki/Vocabulary/Loopless),
instead manipulating arrays with operators ("verbs") implicitly applied to the
whole array. This may seem similar to a functional style of `map` or `filter`
over a list, but it's not quite the same thing: although those constructs don't
have an explicit `for i in...` they still tend to talk about applying something
to a cell at a time, and they can change the shape of the array.

It's a very different way of thinking about programming and that's interesting.

## Resources

- [J for C Programmers](https://www.jsoftware.com/help/jforc/contents.htm)

- [NuVoc][], a "new vocabulary", basically a table of built-in verbs.

[NuVoc]: https://code.jsoftware.com/wiki/NuVoc

## A few tips on J

- J code is scanned into words from left to right but then, more importantly,
  evaluated from right to left. There are few exceptions to this right-to-left
  evaluation other than parentheses, and no concept of associativity: so `10 -
  2 - 1` is not `7` as you might expect, but `9`, because it's equivalent to
  `10 - (2 - 1)`.

  A consequence of this is that I tend to build up expressions by getting some
  building block working and then adding more code to the start of it, that
  uses those results.

- J likes linguistic analogies: "noun" (object), "verb" (function), "adverb"
  (higher-order function), "word" (any of the above), ...

- One particularly surprising part is that a space-separated list of numbers
  parses as a single "word", which is a list.  This explains how `1 2 3 + 4 5
  6` "knows" to add the two lists with no explicit markers and with simple
  right-to-left evaluation: there are only three words here.

- All verbs can be evaluated in either of two _valences_:

  - "monadic": like a prefix operator, with a single argument `y`. For example, `- 3`.
  - "dyadic": like an infix operator, with two arguments `x` on the left and
    `y` on the right, like `10 - 1`.

  In C-descended languages `-` is the only case like this (or sometimes,
  trivially,`+`). In J everything does this. The meanings tend to be similar
  but they need not be.

- "Primitive" verbs (built-in functions) are generally named by a single
  punctuation character possibly followed by either `.` or `:`. In these cases
  I read them as being similar to a mathematical [prime
  symbol](https://en.wikipedia.org/wiki/Prime_(symbol)), like `x'`. It helps to
  learn to see them as part of the previous symbol.

  To read J one essentially has to memorize at least the common verbs from [NuVoc][].

- Verbs have informal short English names for each of their valences, which are
  a bit more descriptive. For example, `x = y` is called _equal_. I use them in
  parenthesis when introducing the verb. They are not recognized by the
  interpreter.

- J has a concept of
  ["rank"](https://code.jsoftware.com/wiki/Vocabulary/RankInfo) which basically
  controls whether a verb, when given an array argument, applies
  cell-at-a-time, or to the whole array, or otherwise. Verbs have a default
  rank but this can be modified by adverbs, in ways I have not yet deeply
  explored. 

## Puzzles

- [Day 01](01.md)
