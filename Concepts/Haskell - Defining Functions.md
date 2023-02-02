#Programming-Languages 
#Haskell 

### Defining a Function
```haskell
add7 n = 7 + n
main = print (add7 8)
```
`15`
```haskell
small 0 = True
small 1 = True
small n = False

main = print (small 5)
```
`False`
You can think of pairs `(m, n)` like a single parameter
```haskell
addUp (0, n) = n
addUp (m, 0) = m
addUp (m, n) = m + n

main = print (addUp (5,6))
```
`11`

## Additional Forms of Definitions
### Case Statements
```haskell
small n = case n + 1 of
 0 -> True
 1 -> True
 n -> False
```
### Haskell Guards
Used to test the properties of an expression
```haskell
sideOfFive n
 | d > 0  = 1
 | d < 0 = -1
 | otherwise = 0
 where d = n - 5

main = print (sideOfFive 5)
 ```
 `0`
### Let
```haskell
y = let x = 10 + 10 in x + x
main = print (y)
``` 
`40`
```haskell
z = let x = 10 in
 let x = 20 in x
main = print (z)
```
`20`
```haskell
w = let x = 5 in
 let f = \n -> x in 
 let x = 6 in
 f 0
main = print (w)
```
`5`
## Higher Order Functions
- Functions that return other functions
- Or functions that take other functions as inputs

### Anonymous Functions
```haskell
\n -> 2 * n
```
### Shadowing
```haskell
h n = (\n -> n)
main = print (h 1 2)
```
`2`
Prints 2 because 2 was the most recently defined n.
### Function as input
```haskell
repFromZero 0 f = 0
repFromZero n f = f(repFromZero (n-1) f)

main = print (repFromZero 3 (\x -> x + 1))
```
`3`
### Functions as outputs
```haskell
addConst n = \m -> n + m
addThree = addConst 3

main = print (addThree 7)
```
`10`