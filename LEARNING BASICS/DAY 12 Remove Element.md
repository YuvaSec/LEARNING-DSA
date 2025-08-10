# My solution
```js
function find(nums, val) {
  if (nums.length === 0) return 0;
  let b = 0;
  for (let i = 0; i < nums.length; i++) {
    if (Math.abs(nums[i]) !== val) {
      nums[b] = nums[i]; // in-place
      b++;
    }
  }
  return b;
}

//let nums = [0,0,1,1,1,2,2,3,3,4]
//let nums = []
//let nums = [5]
//let nums = [1,2,3,4]
//let nums = [-3, -3, -2, -1, -1, 0]
let val = 2;
let k = find(nums, val);
console.log(k);

console.log("*****");
for (let i = 0; i < nums.length; i++){
     console.log(nums[i])
 }
console.log("*****");
console.log(nums);

```