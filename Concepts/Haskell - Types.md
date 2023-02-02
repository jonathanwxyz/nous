#Programming-Languages 
#Haskell 

### Types and Type Inference
Everything in [[Haskell]] has a type at compile time

We can explicitly give the type of a function:
```haskell
f :: Int -> Int
f x = x + 1
```
other numeric types: `Float`, `Double`, `Integer` (which is unbounded, can be of any size)
`Bool` is also a type and can be `True` or `False`

We can also use ==type inference==:
If we don't provide the types then the haskell compiler will work out the types required
```haskell
j x = True
```
Haskell also uses ==parametric polymorphism== or generics, so we can call `j` with different types:
```haskell
main = print(j 1 && j True)
```
To  do this explicitly, use a lowercase type definition for generic types:
```haskell
j :: a -> Bool
```
### Type Constructors
Using type constructors we can use types to make more complex types:
```haskell
sumPair :: (Int, Int) -> Int
sumPair (x,y) = x + y
```
The `::` indicates that what is to the right of it is a type, the `->` indicates it's a function so we're stating that `sumPair` is a function taking `(Int, Int)` as as input and outputting `Int`.

### Algebraic Datatypes
```haskell
data SwitchState = On | Off

isOn On = True
isOn Off = False

toggle On = Off
toggle Off = On
```

```haskell
data MyIntPair = IntPair Int Int

mySumPair (IntPair x y) = x + y

main = print(mySumPair(IntPair 10 11))
```

Can combine the algebraic datatype features of having enums (on or off) and pairs/tuples:
```haskell
data BoolOrInt = Abool Bool | Anint Int

intval :: BoolOrInt -> Int
intval (Abool True) = 1
intval (Abool False) = 0
intval (Anint x) = x
```

Can be used generically:
```haskell
data MyPair a b = Pair a b
```

Can be used recursively:
```haskell
data MyList a = Empty | Append a (MyList a)

myHead Empty = Nothing
myHead (Append x l) = Just x

main = print(myHead (Append 10 (Append 11 Empty)))
```


### Maybe
Good for error handling, a variable can be something or nothing:
```haskell
-- Maybe a = Nothing | Just a
Maybe Int
```
### Lists
List syntax `[]`, `:` to append
```haskell
myIntHead :: [Int] -> Maybe Int

myHeadb [] = Nothing
myHeadb (x:xs) = Just x

main = print(myHeadb (1:2:[]))
-- syntax sugar
main = print(myHeadb [2,2,3,4])
```

`..` syntax:
```haskell
main = print([1..5])
```
prints [1,2,3,4,5]
```haskell
main = print([1,3..10])
```
works out the difference between the first 2 and creates a pattern from it:
prints [1,3,5,7,9]

There's also ==list comprehension==
```haskell
l = [(w,n) | w <- "Hi!", n <- [1..3]]
```
prints:
```
[('H', 1), ('H', 2) ... , ('!', 2), ('!', 3)]
```

```haskell
l = [(w,n) | w <- "Hi!", n <- [1,2], w /= 'i']

main = print(l)
```
skips when `w` would otherwise be assigned 'i'
