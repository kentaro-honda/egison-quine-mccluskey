# egison-quine-mccluskey/egison3
Egison 3 Implementation of Quine-McCluskey method

## Contents

* `src/`
  * `qm.egi`
    Implementation of Quine-McCluskey method
  * `input.egi`
    Sample input

## Requisites

* [egison](https://github.com/egison/egison)

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
Egison Version 3.7.14 (C) 2011-2018 Satoshi Egi
https://www.egison.org
Welcome to Egison Interpreter!
> (load-file "src/qm.egi")
> (load-file "src/input.egi")
> (test (QM input))
{{#t #f <D> <D>} {<D> #t #f #f} {#t <D> #t <D>}}
> (test (QM l0))
{{<D> #f #f #t} {#f #t <D> #f} {#t #f <D> <D>} {<D> #t #t #t}}
> (test (QM l1))
{{<D> <D> #f <D> <D> #t} {<D> <D> #t <D> <D> #f}}
> (execute (main))
input : {{#t #f} {#t #t}}
output : {{#t <D>}}
```

`<D>` stands for "dont't care".
