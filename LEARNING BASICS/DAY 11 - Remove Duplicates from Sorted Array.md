# question
Given an integer array `nums` sorted in **non-decreasing order**, remove the duplicates [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) such that each unique element appears only **once**. The **relative order** of the elements should be kept the **same**. Then return _the number of unique elements in_ `nums`.

Consider the number of unique elements of `nums` to be `k`, to get accepted, you need to do the following things:

- Change the array `nums` such that the first `k` elements of `nums` contain the unique elements in the order they were present in `nums` initially. The remaining elements of `nums` are not important as well as the size of `nums`.
- Return `k`.

**Custom Judge:**
The judge will test your solution with the following code:

int[] nums = [...]; // Input array
int[] expectedNums = [...]; // The expected answer with correct length

int k = removeDuplicates(nums); // Calls your implementation

assert k == expectedNums.length;
for (int i = 0; i < k; i++) {
    assert nums[i] == expectedNums[i];
}


# My Solution 
```js
function find(nums) {
  let a = [];
  let b = -Infinity;
  for (let i = 0; i < nums.length; i++) {
    if (b <= nums[i]) {
      if (b == nums[i]) {
        b = nums[i];
      } else {
        a.push(nums[i]);
        b = nums[i];
      }
    }
  }
  return a;
}


let nums = [-3, -3, -2, -1, -1, 0]
let k = find(nums);
console.log(k) // OUTPUT : [-3,-2,-1,0]
```
- But the main problem is 
	- I am creating new Array instead of [[TIME AND SPACE COMPLEXITY#**Common Space Complexities**|O(1)]]
	- And the output "a" is an array instead of a integer key
	- Which is used to check the Amended "nums" in the Key range.

# Corrected code.
```js
function find(nums) {
  let a = 0;
  let b = -Infinity;

  for (let i = 0; i < nums.length; i++) {
    if (b < nums[i]) {
      nums[a] = nums[i]; // in-place overwrite nums array
      b = nums[i];
      a++;
    }
  }

  return a; 
}

let nums = [-3, -3, -2, -1, -1, 0]
let k = find(nums);
console.log(k) // OUTPUT : 4

//The Rearranged array is [-3,-2,-1,0,-1,0]
// Check using this.
console.log("*****")
for (let i = 0; i < nums.length; i++){
console.log(nums[i])
}
```