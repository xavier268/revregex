
# rgen

[![Go Reference](https://pkg.go.dev/badge/github.com/xavier268/rgen.svg)](https://pkg.go.dev/github.com/xavier268/rgen) [![Go Report Card](https://goreportcard.com/badge/github.com/xavier268/rgen)](https://goreportcard.com/report/github.com/xavier268/rgen)

This package generate all the strings with a given length matching a provided regexp pattern.

**Generate()** provides an asynchroneous generation model, with a channel.

**Generator** provides synchroneous generation model 
* NewGenerator() creates a Generator
* Reset(n int) defines the required length (exact)
* Next() compute the next string
* Last() retrieve the computed string.

## How to use 

See examples & test files.

## Supported operations :

* Parenthesis for grouping, without capture
* Zero-or-more(*)
* One-or-more(+)
* Zero-or-one (?)
* Repeat {n,m}
* Alternatives (|)
* Concatenation
* Character classes [a-z] or [abc] or [0-3 8-9]

The provided context allows for timeout and cancelation management.
Operations are threadsafe accross generators.

## Unsupported opérations :

The following operations are not supported, because they make little sense in this context.

* dot(.) operator
* flags
* capture
* boundaries, start/end of word, text, line ...