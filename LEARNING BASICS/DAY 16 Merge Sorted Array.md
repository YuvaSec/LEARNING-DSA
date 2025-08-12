You are given 
- two integer arrays `nums1` and `nums2`, 
- sorted in **non-decreasing order**, 
- two integers `m` and `n`,
	- representing the number of elements in `nums1` and `nums2` respectively.

**Merge** `nums1` and `nums2` into a single array sorted in [[IMPORTANT THING TO REMEMBER#2. NON DECREASING == CAN HAVE DUPLICATES|non-decreasing order]].

# Constraints
> The final sorted array should ***not be** returned by the function, 

> Should be _stored inside the array_ `nums1`. 

> To accommodate this, `nums1` has a length of `m + n`, 
> where the first `m` elements denote the elements that should be merged, and the last `n` elements are set to `0` and should be ignored. `nums2` has a length of `n`.

# Test Cases
nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
nums1 = [1], m = 1, nums2 = [], n = 0
nums1 = [0], m = 0, nums2 = [1], n = 1


# Simpler Inbuilt approach
```js
let nums1 = [2, 2, 3, 5,0,0,0,0] 
let nums2 = [2, 3, 3, 9] 
let m = 4 let n = 4 
let tot = m+n 

while (m < tot) 
	{ 
		nums1[m] = nums2[m - n] 
		m++ 
	} 
nums1.sort() 
console.log(nums1)"
```
```
Time: 𝑂((𝑚+𝑛)log(𝑚+𝑛)), Space: 𝑂(1) to 𝑂(log(𝑚+𝑛)) extra
```

# AI Optimized Version
```js
let nums1 = [2, 2, 3, 5, 0, 0, 0, 0];
let nums2 = [2, 3, 3, 9];
let m = 4, n = 4;

let m1 = (m - 1);        // last valid in nums1
let n1 = (n - 1);        // last in nums2
let k = ((m + n) - 1);    // fill position in nums1

while (n1 >= 0) {
  if (m1 >= 0 && nums1[m1] > nums2[n1]) {
    nums1[k--] = nums1[m1--];
  } else {
    nums1[k--] = nums2[n1--];
  }
}

console.log(nums1); // [2, 2, 2, 3, 3, 5, 9]

```

# Teachers Solution
```js
let nums1 = [2, 2, 3, 5, 0, 0, 0, 0];
let nums2 = [2, 3, 3, 9];
let m = 4;
let n = 4;

let p1 = 0;
let p2 = 0;
let nums1copy = nums1.slice(0, m);

for (let i = 0; i < m + n; i++) {
  if (p2 >= n || (p1 < m && nums1copy[p1] < nums2[p2])) {
    nums1[i] = nums1copy[p1];
    p1++;
  } else {
    nums1[i] = nums2[p2];
    p2++;
  }
}
```

