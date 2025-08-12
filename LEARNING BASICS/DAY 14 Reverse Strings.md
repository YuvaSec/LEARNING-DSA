Write a function that reverses a string. The input string is given as an array of characters `s`.
You must do this by modifying the input array
let s = ["h", "e", "l", "l", "o"]
let s = ["H", "a", "n", "n", "a", "h"];

**Constraints:**
- `1 <= s.length <= 105`
- `s[i]` is a [printable ascii character](https://en.wikipedia.org/wiki/ASCII#Printable_characters).
- in-place with 
- O(1)` extra memory.


# My Solution
```js
function fun(s) {
  let s1 = [];
  for (let i = s.length; i > 0; i--) {
    s1.push(s[i - 1]);
  }
  return s1;
}

//let s = ["h", "e", "l", "l", "o"]
let s = ["H", "a", "n", "n", "a", "h"];
let k = fun(s);
console.log(k);
```
**I forgot about the 0(1) space complexity constraint**
**Its a new learning**

# After Realization using AI
```js
function fun(s) {
  let left = 0;
  let right = s.length - 1;

  while (left < right) {
    let temp = s[left];
    s[left] = s[right];
    s[right] = temp;

    left++;
    right--;
  }
  return s;
}

let s = ["h", "e", "l", "l", "o"];
//let s = ["H","a","n","n","a","h"]
let k = fun(s);
console.log(k);

```

