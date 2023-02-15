#Programming-Languages 
#Haskell 

```haskell
-- ERROR VALUES

-- We have seen that sometimes things can 'go wrong' at runtime
-- for example

x = x

-- the meaning of this expression is undefined. It is sometimes called
-- 'bottom'

bottom = bottom

-- We definitely don't want to run  

-- print(bottom)

-- as this will cause the computer to go into an infinite loop!

-- We have seen other runtime errors, like what happens when we
-- evaluate a function defined by pattern matching on an argument where 
-- it is not defined

badhead :: [Int] -> Int 
badhead (x:xs) = x 

uhoh = badhead []

-- main = print(uhoh)

-- When reasoning about a function is is easier to only consider the case where
-- it's inputs don't go wrong. But what if we want to reason about all inputs?
-- Let's probe the behaviour of some functions when given error values
-- Rather than testing with real errors, we can use the 'error' expression to deliberately
-- cause errors

eInt :: Int
eInt = error "Hang on, I'm thinking..."

eBool :: Bool
eBool = error "Hang on, I'm thinking..."

-- you should avoid the use of the error expression at all costs! It is *not* a good way
-- of implementing error handling in Haksel. For instance, badhead should be re-rwitten
-- to use the Maybe datatype, which will mean it can be totally defined.
-- However, it is useful for testing code to see what it would do in the presence of
-- an error as input.

--main = print(eInt) 

-- Now let's define a function and see how it behaves when its input goes wrong

f x = x + 3  

-- main = print (f eInt)

-- But something interesting happens if the function does not look at the argument

g x = 5

-- main = print(g eInt)

--just prints 5 !
-- this means it is safe to call g with the value bottom!

-- main = print(g bottom)

-- even though trying to print bottom will cause an infinite loop, Haskell never evaluates
-- the unused argument. We say that f is *strict* in its argument, but g is *not strict* 
-- in its argument. A function is strict in an argument if and only if when that argument is
-- bottom or an error, the value of the function is bottom or an error.

-- Let's see if the * operator is strict or not in its arguments
-- running
-- main = print(0 *  (eInt))

-- strict in the second argument

-- main = print((eInt) *  0)

-- strict in the first argument



-- REASONING IN THE PRESENCE OF ERRORS

-- if we probe functions using error values, we might get behaviour we don't expect.
-- for instace, we might try to see which argument + looks at first, which breaks the
-- abstraction that it is a mathematical functions

-- main = print((error "left!" + error "right!"))

-- main = print(error "right!" + error "left!")

-- Does this mean that + is not really commutative in Haskell, if we consider errors?
-- The answer is actually 'no' for a slightly complicated reason. In Haskell, if the value
-- of an expression is an error, including non-termination, its theoretical value is the
-- set of all errors which could result from evaluating in any order.
-- An implementation can freely choose which of these actually happens, and that could
-- depend on random factors at the time of running. So theoretically + is still commutative
-- in the presence of errors, because the *set* of possible behaviours doesn't depend on
-- the order of the arguments, even though the error we actualy see might depend on that,
-- and on other, perhaps mysterious things!

-- However, we could define a "short circuiting" definition of * which ignores one of its
-- arguments

stimes :: Int -> Int -> Int
stimes 0 _ = 0
stimes x y = x * y

-- Remark: one nice bit of Haskell syntax is that you can a funtion as an inline operator
-- if you enclose it's name in backticks: `...`

-- main = print(0 `stimes` eInt)
-- main = print(eInt `stimes` 0)

-- this is fundamentally noncommutative, because if an expression denotes a non-error
-- value, then it is *not* allowed to return an error that would have resulted from
-- evaluating part of the expression that is not looked at!

--This means it is safe to apply stimes to bottom in the second arguments

--main = print(0 `stimes` bottom)

-- the boolean operators && and || are impememnted in this way:

--main = print(False && eBool)
--main = print(True && eBool)
--main = print(eBool && False)

-- So && is strict in its first argument, but non-strict in its second argument.

-- Something interesting happens for more complicated kinds of data, like pairs.

strangePair = (eInt, eBool)
ePair = error "Hang on, I'm thinking..."

h :: (Int, Bool) -> Int
h (x,y) = 42

j :: (Int, Bool) -> Int
j p = 10

--main = print(h strangePair)
--main = print(h ePair)
--main = print(j ePair)

-- so there is a dfference between an error of type (a,b), and a pair of errors!
-- we can pattern match on a pair of errors sucessfully, as long as we don't try to use 
-- the components. But a pair which is an error in itself can't even be pattern matched on.
-- Some people would say that the function h is strict in the 'spine' (i.e. shape) of the
-- pair, but non-strict in the components, whereas j is non-strict in the spine.

-- This is necessary if we want the fst and snd operations, which get the first and
-- second components of a pari, to obey the expected equations
-- fst(x,y) == x
-- and
-- snd(x,y) == y  

--main = print(fst(1,eBool))
--main = print(snd(eInt,True))

-- but it *breaks* another expected equation, namely that for all pairs p we have
-- p == (fst p, snd p), because of what happens when the components are errors

ePairB = (fst ePair, snd ePair)

--main = print(h ePairB)

-- so ePairb behaves differently to ePair when passed to h.
-- This is why it is usually easier to reason about how function behave when their
-- arguments are not errors.

--INFINITE DATA 

-- Suppose we define an Algebraic Data Type

data MyIntList = Emp | Cons Int (MyIntList) 

-- lets construct a value of this datatype which contains an error, but which is not 
-- an error in itself

v1 = Cons 10 (Cons eInt Emp)
v2 = Cons 11 (error "Hi!")

-- Let's write a function to get the head  

myhead :: MyIntList -> Maybe Int
myhead Emp = Nothing
myhead (Cons x xs) = Just x

--main = print(myhead v1)
--main = print(myhead v2)

-- this tells us that it makes sense to think of values of algebraic Data Types as being
-- patially errors and partially sensible values. Functions which are non-strict in part 
-- of the data structure  can work with these. We say that myhead is strict in the head of 
-- the list, and non-strict in the tail.

-- The built-in list type works the same way.

--main = print(head [1,eInt])

--main = print(head (1:(error "Hi!")))

-- Let's write a length function

mylen [] = 0  
mylen (x:xs) = 1 + mylen xs

--main = print(mylen [eInt,eInt,eInt])

--main = print(mylen (1:(error "Hi!")))

--This shows that mylen is strict in the spine of the list, but non-strict in the
--elements of the list. But myhead was also non-strict in the spine of the list: it
--didn't care that the tail was an error. Another function like that is the built in take.

--main = print(take 2 (1:2:(error "hi!")))

-- This means we can write recursive definitions of lists which describe infinite lists
-- as long as we only apply functions to them which explore a finite part of the lists
-- everything will be ok!

ones = 1:(ones)

--main = print(take 5 ones)

-- there are built in bits of syntax which denote infinite lists

--main = print(take 5 [0..])

--main = print(take 5 (drop 6 [0..]))

-- We can try implementing [0..] ourselves

nats = 0:[n + 1 | n <- nats]

--main = print(take 5 nats)

-- We can do very advanced things when recursively defining a list. For instance
-- in Haskell there is a !! operator which gets the n'th element of a list. We can use
-- it to define the list of all fibbonacci numbers

fibb = 1:1:[(fibb !! n) + (fibb !! (n + 1)) | n <- [0..]]

--main = print(take 6 fibb)

-- Finally, let's define the list of all primes. The way this is done
-- following https://hernandis.me/2019/10/20/haskell-infinite-structures.html
-- is to define a recursive function sieve on lists, which removes
-- all multiples of the head of the list from the result of sieving the
-- tail!

sieve [] = []
sieve (x:xs) = x:[v | v <- xs, v `mod` x /= 0]

primes = sieve [2..]

main = print(take 10 primes)
```