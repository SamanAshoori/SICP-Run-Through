this is chapter one of [[Structure and Interpretation of Computer Programs]]

# 1.1 - Elements of Programming

Every powerful [[Programming Language]] is built on three pillars
primitive expressions - which represent the simplest entities the language is concerned with
means of combination - in which compound elements are built from simpler ones
means of abstraction - compound elements can be named and manipulated as units

With these three pillars you can combine simple ideas to form more complex ideas.

In programming you deal with two elements - [[statement]]s and [[data]] - therefore any powerful programming language should be able to describe primitive data and statements.

## 1.1.1 Expressions
In Scheme / Lisp you can type a simple expression like 420 and the terminal will return 420 - this is an example of a primitive expression e.g. an Integer.

```Scheme
420
```

in Lisp/Scheme you can combine an expressions representing numbers e.g 420 with expressions representing [[statement]] e.g + or -

```Scheme
(+ 137 349)
```
the following expression will return
486

in Lisp the expressions use a prefix notation for operators and operands which is why the + appears on the left of the numbers. One advantage is the way it can allow combinations to be nested e.g

```Scheme
(+ (* 3 5) (- 10 6))
```
will return 19
because the 35 is 15 , the 10 - 6 is 4 and then the final left operand is the + so it then becomes (+ 15 4)
which makes 19

## 1.1.2 - Naming and the Environment
In any programming language it is a critical aspect to name a [[variable]] this is because it is a simple form of abstraction because it allows us to use simple names to refer to the results of compound operations.

it would very inconvenient to remember and repeat the output from functions over and over so saving them with a simple name is vital

in Lisp / Scheme it is done as so

```Scheme
(define size 2)
(+ size size)
```
this would return 4 as size is 2 and 2+2 = 4

## 1.1.3 Evaluating Combinations

To evaluate a combination, do the following:
1. Evaluate the sub expressions of the combination.
2. Apply the procedure that is the value of the leftmost sub expression (the operator) to the arguments that are the values of the other sub expressions (the operands).

## 1.1.4 Compound Procedures

We have seen some elements in Lisp that must appear in any powerful programming language:
	- Numbers and arithmetic operations are primitive data and procedures
	- Nesting of Combinations provide a means of combining operations
	- Definitions that associate names with values provide a limited means of abstraction

Now we can learn about procedure definitions, a more useful abstraction technique in which a compound operation can be given a name and then referred to
```Lisp
(define (square x) (* x x))
```

This above procedure gives you the function to square something

lets break it down

define (square x) (* x x))
TO square any given value (x) - you have to multiply x by x (itself)

like creating a function in another language - you define the name , the parameters and the body of the function

once square has been defined we can use it like any other function in lisp as well as use it as a building block in other functions e.g

```lisp
 (define (sum-of-squares x y) (+ (square x) (square y)))
```

what this does it it squares x and squares y and then sums the results
e.g 
```Lisp
(sum-of-squares 3 4)
```
would return 25
