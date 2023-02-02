### What is it?
A technique used to store certain results of an algorithm, particularly useful for [[Divide and Conquer]]/recursive problems as it avoids repetition in calculation
It is a ==top-down== approach to [[Dynamic Programming]], this is as opposed to [[Tabulation]] which is ==bottom-up==

### Python Fibonacci Example
```python
lookup = {0: 1, 1: 1}

def fib(n: int) -> int:
	if n in lookup:
		return lookup[n]
	res = fib(n - 1) + fib(n - 2)
	lookup[n] = res
	return res
```