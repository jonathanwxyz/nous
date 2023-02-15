#Programming-Languages 
#Haskell 

```haskell
-- INPUT AND OUTPUT

-- In Haskell, everythin is a value, so what is the meaning of:

--main = print "Hi!"

-- The idea is that there is a special type of values which represent
-- input-output behaviours

--main = (print "Hi!"::IO ())

-- A Haskell program is just a complicated definition of a particular IO
-- value called main. The compiler looks at the definition of this value
-- and creates an executable with the specified behaviour.

--a = print "a!"
--b = print "b!"
--main = print "main!"

--main = head [print 1, print 2, print 3]

-- IO values are ordinary values in many ways, for instance we can return
-- them from functions:

greet n = print ("Hi " ++ n)

-- main = greet "Joe"

-- There are also various operations on these values, for example >>
-- which denotes one behaviour followed by another

--main = (greet "Joe") >> (print "You are great!")

-- Aside from print, there are many other IO actions, for instance

--main = getLine

-- the type of getline is

--main = (getLine:: IO String)

-- In general we can use types IO b for any type a
-- This represents a type of input-output behaviours
-- which end up with a value of type b being stored

-- We can take any ordinary value and convert it to
-- an IO value

--main = return 6
--main = (return 6:: IO Int)

-- This represents an input-output behaviour which
-- does nothing, but ends up with the number 6 being
-- stored. In particular it does *not* print 6, that
-- isn't doing nothing!

-- If we don't care what value gets stored, we use the
-- 'empty tuple' (), an element of the type (), which
-- has only one value.

--main = return ()
--main = (return ()::IO ())

-- How can we make a program that prints different
-- things, depending on the user input?
-- There is an operator >>= whose type is
-- IO b -> (b -> IO c) -> IO c
-- It lets us embed the logic described by a function
-- into the behaviour of an IO value.

-- main = print "Enter your name:" >>
--       getLine >>= (\n -> print (n ++ " is so cool!"))

-- An input-output behaviour can be infinite, we define
-- this in the usual way, via recursion

{-
main = putStrLn "Who is the greatest?" >>
       getLine >>=
      (\n -> if n == "Joe"
             then putStrLn "Don't forget it!"
             else (putStrLn "Be serious!" >> main))
-}

-- Note that 'return' is not a control-flow operator
-- there are no control flow operators!
{-
main = putStrLn "Who is the greatest?" >>
       getLine >>=
      (\n -> if n == "Joe"
             then putStrLn "Don't forget it!"
             else (return "Be serious!" >> main))
-}

-- It can get annoying when we have lots of >> and >>=
-- everywhere

{-
main = putStrLn "Enter a name:" >>
       getLine >>=
       \n -> 
       putStrLn "Enter another name:" >>
       getLine >>=
       \m -> putStrLn ("Hello " ++ n ++ " and " ++ m)
-}

-- There is special syntax sugar called 'do notation'
-- which inserts these automatically

main = do
         putStrLn "Enter a name:"
         n <- getLine
         putStrLn "Enter another name:"
         m <- getLine
         putStrLn ("Hello " ++ n ++ " and " ++ m)

-- Haskell people think this is good for some reason
-- Frankly I am suspicious of syntax sugar which
-- saves keystrokes but makes the meaning less clear!
```