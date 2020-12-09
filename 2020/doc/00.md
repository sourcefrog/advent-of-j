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

## Puzzles

- [Day 01](01.md)
