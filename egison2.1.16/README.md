# egison-quine-mccluskey/egison2.1.16
Egison 2.1.16 Implementation of Quine-McCluskey method

**WARNING**: Egison 2 is NOT backward compatible. The code does NOT work on egison 2.2.0 or later.

## Contents

* `src/`
  * `qm.egi`
    Implementation of Quine-McCluskey method
  * `input.egi`
    Sample input
* `docs/`
  * `qm.pdf`
    Slides in Japanese (originally created for the 1st Egison Workshop)

## Requisites

* [egison](https://github.com/egison/egison) 2.1.16

## Input Representation

Input is a collection of collections of boolean values.
```egison
{{#t #t} {#f #f}}
```
represents the truth table

| p | q | output |
| :-: | :-: | :------: |
| T | T |   T    |
| T | F |   F    |
| F | T |   F    |
| F | F |   T    |

## How to work

```
$ egison
Egison Version 2.1.16 (c) 2011-2012 Satoshi Egi
http://hagi.is.s.u-tokyo.ac.jp/~egi/egison/
Welcome to Egison Interpreter!
> (load-file "src/qm.egi")
src/qm.egi loaded.
> (load-file "src/input.egi")
src/input.egi loaded.
> (test (QM input))
{{<d> #t #f #f} {#t #f <d> <d>} {#t <d> #t <d>}}
> (test (QM l0))
{{<d> #f #f #t} {#f #t <d> #f} {#t #f <d> <d>} {<d> #t #t #t}}
> (test (QM l1))
{{<d> <d> #f <d> <d> #t} {<d> <d> #t <d> <d> #f}}
> (execute)
input : {{#t #f} {#t #t}}
output : {{#t <d>}}
```

`<d>` stands for "dont't care".
