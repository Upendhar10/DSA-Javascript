## Understanding the Problem statement :
```
Given, 
    integer array => arr
    arr.length => n
    secondLargest => ? // find this
```

## Bruteforce Approach 

### Pseudo code:
 - Sort the given array in the ascending order.
 - Traverse the array from the second last index,
 - Return the first element, that is less than the element at last index of the sorted array.

### Code:
```javascript
function SecondLargestBrute(arr, n){
	
	// Sort in ascending order
	arr.sort((a,b) => a < b);
	
	// Largest Element
	let largest = arr[n-1];
	
	// Find the second largest element
	for(let i=n-2; i>=0; i--){
		if(arr[i] < largest){
			return arr[i];
		}
	}
	
	return -1;
}
```
### Algorithmic Analysis:

**Time Complexity:**
```
O(n log n) + O(log n) 
    => O(2n log n)
        => O(n log n)
```
**Space Complexity:** O(1)

---

## Optimal Approach

### Pseudo Code :

- Initialize two variables :
	- Largest => arr[0]
	- SecondLargest => -1
- Traverse the array from first index,
	-  if (currElement > Largest) 
		- secondLargest = Largest
		- Largest = currElement
	- else if (currElem < Largest && currElem > secondLargest)
		- secondLargest = currElem
- Finally, return the secondLargest.

### Code :

```javascript
function secondLargestOptimal(arr, n){
	
	let largest = arr[0];
	let secondLargest = -1;
	
	for(let i=0; i<n; i++){
		if(arr[i] > largest){
			secondLargest = largest;
			largest = arr[i];
		}else if(arr[i] < largest && arr[i] > secondLargest){
			secondLargest = arr[i];
		}
	}
	return secondLargest;
}
```

### Algorithmic Analysis:

**Time Complexity:** O(n)

**Space Complexity:** O(1)