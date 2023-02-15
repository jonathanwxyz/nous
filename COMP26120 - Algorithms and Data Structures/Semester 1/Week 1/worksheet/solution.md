![[Pasted image 20221002170742.png]]
# Algorithm 1
## Pseudocode
```
function fixedPoint(A int array) {
	for each index, value in A {
		if i = v return i
	}
	return "No"
}
```
## Correctness
To find the fixed point of an array it is sufficient to check every element and its index. For each element we check we can compare it to its index. If it is the same then we can return the index.
## Complexity
O(n) as we loop through each item in the array.

# Algorithm 2
## Pseudocode
```
function fixedPoint(A: int array) {
	index <- A.length // 2
	if A[index] = index return index
	if A.length = 1 return "No"

	if A[index] < index {
		fixedPoint(A[index:])
	} else if A[index] > index {
		fixedPoint(A[:index])
	}
}
```
## Correctness
To find the fixed point of an array it is sufficient to check to do a binary search where we check if the index differs from the element at that index and to half the array accordingly. If the index is less than the element at that index then we take the left side of the array, if the index is greater than the element at that index then we take the right side of the array.

## Complexity
O(logn) because we halve size of the array on each iteration.