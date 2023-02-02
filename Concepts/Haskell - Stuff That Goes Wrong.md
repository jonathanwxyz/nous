#Programming-Languages 
#Haskell

### Non exhaustive pattern matching
```haskell
oops True = True

main = print (oops False)
```
We haven't defined oops of False!

### Undefined recursion
```haskell
eep 0 = 0
eep n = 1 + eep n
```
Would run forever!

### Shadowing in let statements
```haskell
yikes = let x = 1 in
 let x = x + 1 in x
```
Runs forever because in each let, x is shadowed and thus doesn't have access to its previous value
same result:
```haskell
yikes = let x = x in x
```