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

### More about Types
```haskell
-- PARAMETRIC POLYMORPHISM
-- ignore the following line:
--{-# LANGUAGE RankNTypes #-}


-- In Week 9, we saw that a type can contain a type variable

f :: a -> Bool
f _ = True

-- This means the function is defined for all types a, but note that
-- we have to use the same definition for each type. This is called
-- "parametric polymorphism"

-- main = print((f 7) && (f False))

-- Now let's talk a bit more about what type variables mean in detail.
-- You should imagine that they are quantified by a "for all" which comes
-- before the start of the type.
-- This means the definition

--g :: (b -> Bool) -> Bool
--g h = (h 7) && (h False)

-- makes no sense! It looks similar to the way we used f above, but
-- here we are claiming that g is a function which given a function of type 
-- b -> Bool FOR ALL TYPES B, will give you a Bool. But then g goes on to
-- assume that it can apply this to numbers and Booleans -- but that wouldn't
-- make sense for e.g. b = String.

-- An example which might be easier to understand is the type (a,a). Can we
-- construct an element of this type by itself?
-- We might think this means giving an element of (a,a) for *some* type a,
-- and trying

--p :: (a,a)
--p = (1,1)

-- But this does not typecheck because p::(a,a) means that p is in the type
-- (a,a) for *every* type a, which is impossible to satisfy (without using
-- bottom or error values...).


-- ***Non-examinable aside***
-- One of the cool aspects of Haskell is that while it is applied (e.g
-- by Facebook), it also interacts with research into programming language
-- design. ghc comes with many cool language extensions which let us
-- experiment with language features which might one day be standard.
-- For instance, if we uncomment the {-# LANGUAGE RankNTypes #-}
-- at the beginning of this file, the following definition will compile.
-- It lets us explicitly state where in the type the "for all" is supposed
-- to happen!

--g :: (forall b. b -> Bool) -> Bool
--g h = (h 7) && (h False)

-- ***End of non-examinable aside ***

-- TYPECLASSES

-- There is also a different kind of polymorphism in Haskell, often called
-- 'ad hoc polymorphism', or 'overloading', which means we can have a
-- function name defined for several types, but in such a way that
-- it behaves *differenty* for each type. This is in contrast to
-- parametric polymorphism where we use the same definition for all types

--main =   print((1::Float) + (1::Float))
--main =   print((1::Float) + (1::Float))

-- This works using 'typeclasses' which are more like what is called
-- 'interfaces' in imperative languages. A typeclass describes a bunch
-- of operations which a type could implement.

-- Let's do a silly example first, a typeclass with a function that
-- returns a string description of an element

class Descriptive a where
  describe :: a -> String

-- To implement the 'describe' function for a type, we declare that
-- type to be an instance of the typeclass

instance Descriptive Bool where
  describe False = "Wouldn't bet on it!"
  describe True = "This actually holds!"

instance Descriptive Int where
 describe 1 = "The lonliest number!"
 describe _ = "A boring number..."
 
--main = print(describe (1 == 2))
--main = print(describe (1::Int))
--note that type inference doesn't work well here -- ghc doesn't
--try to use the fact that we've only implemented this for one numberical
--type

--We can now implement polymorphic functions which don't work for all
-- types, but only those types which are instances of a typeclass

descrLen :: Descriptive a => a -> Int
descrLen x = length (describe x)

--main = print(descrLen False)

-- How would we go about implementing a describe function for
-- lists? The problem is that we can have a type [b] of lists of any
-- type b, but the type b might not be an instance of Descriptive.
-- We can solve this by saying that IF b is Descriptive, THEN so is [b]

instance (Descriptive b) => Descriptive [b] where
    describe [] = "Nothing left!"
    describe (x:xs) = (describe x) ++ ", then " ++ (describe xs)

-- main = print(describe [True,False])

-- A more realistic example is the typeclass Eq of types whose elements
-- can be compared for equality. For instance, we expect numbers to be
-- comparable for equality, but not functions since we are modelling
-- computable equality!

-- Syntax: a Haskell function name can consist of all symbols. Such 
-- functions are treated as infix operators. When defining them or passing 
-- them to higher-order functions, we have to wrap the name in brackets.

class MyEq a where
  (===) :: a -> a -> Bool
  (/==) :: a -> a -> Bool
  x /== y = not(x === y)

-- Note that I couldn't use == and /= as these are already used by
-- the built-in Eq typeclass -- more on that later.

-- In the above typeclass, we provide an implementation of /== in terms of
-- === , so instance only have to define ===

instance MyEq Bool where
 False === False = True
 True  === True  = True
 _     === _     = False

--main = print(True /== False)

-- Functions can specify that an input type must be an instance of
-- multiple typeclasses

ifEqD :: (MyEq a, Descriptive a) => a -> a -> a -> a -> String
ifEqD w x y z = if w === x then (describe y) else (describe z)

--main = print(ifEqD False False True False)

-- BUILT-IN TYPECLASSES

-- There is a typeclass Show a which is like Descriptive: it provides
-- a function show :: a -> String, but usually you give a sensible
-- string, not like the example above! This is how the print function knows
-- how to turn various values into strings

--main = print(take 5 (show [1,2,3,4,5,6]))

-- We can manually implement this for our own types if we want:

data Pcolours = R | G | B

instance Show Pcolours where
  show R = "Red"
  show G = "Green"
  show B = "Blue"

--main = print([R,G,B])

-- but for this built-in typeclass there is also a default implementation
-- which we can access by adding "deriving (Show)" to the type definition

data Colour = RGB Int Int Int | HSV Int Int Int deriving (Show)

-- main = print(RGB 10 11 12)

-- Similarly we mentioned the built-in typeclass Eq which provides == and /=
 
data ToyType =  Bird | Comet | Cloud deriving (Eq, Show)

data Mobile = Toy ToyType | Stick Mobile Mobile deriving (Show)
 
-- For Mobile we will define our own instance of Eq to get custom behaviour
 
instance Eq Mobile where
   Toy a == Toy b = a == b
   Stick w x == Stick y z = (w == y && x == z) || (w == z) && (x == y)
   _ == _ = False
 
main = print((Stick (Toy Bird) (Stick (Toy Cloud) (Toy Comet))) ==
       (Stick  (Stick (Toy Comet) (Toy Cloud) ) (Toy Bird))  )
```