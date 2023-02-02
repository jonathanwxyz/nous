#Programming-Languages
#Haskell 

- Literals begin with uppercase letters (True, False)
- Identifiers begin with lowercase letters (think of variables but immutable)
- A new definition must begin at the beginning of a line
	- To carry on a definition on a new line, there must be whitespace
```haskell
b = False || (True && True)

main = print (b)
``` 
`True`
```haskell
b = False || (True && False)

v = 7 * (if b then 5 else 6)
main = print (v)
``` 
`42`