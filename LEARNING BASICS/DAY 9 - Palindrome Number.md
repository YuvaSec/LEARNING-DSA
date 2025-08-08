
# Check if Palindrome
```js
let num = 0;
// CHECKS FOR NEGATIVE AND STRINGS //
if (num < 0 || typeof num == "string") {
  console.log("False");
} else {
  let cpy = num;
  let rev = "";
  // CHECKS FOR PALINDROME //
  while (num > 0) {
    rev += num % 10;
    num = Math.floor(num / 10);
  }
  rev = Math.floor(rev);
  if (rev == cpy) {
    console.log("True");
  } else {
    console.log("False");
  }
}
```

# Check For Palindrome Numbers
```js
function palindrome(n) {
  for (let i = 0; i < n.length; i++) {
    let num = n[i];
    let rev = "";
    while (num > 0) {
      rev += num % 10;
      num = Math.floor(num / 10);
    }
    rev = Math.floor(rev);
    if (rev == n[i]) {
      console.log("Yes " + n[i] + " is a Palidrome");
    } else {
      console.log("No " + n[i] + " is not a Palindrome");
    }
  }
}
let n = [0, 143, 121, -141, 1331, 1, -999];
palindrome(n);
```

# But My Teacher Solved it using Math 
```js
var isPalindrome = function(x) {
  if (x < 0) return false;
  let xCopy = x;
  let rev = 0;
  while (x > 0) {
    let rem = x % 10;
    rev = rev * 10 + rem;
    x = Math.floor(x / 10);
  }
  return rev === xCopy;
};

console.log(isPalindrome(121)); // true
```