- I have Written this Logic on my own
- But I was failing to check for 32-bit limit.
- Later i did fix it.
```js 
function reverse(x) {
  let cpyx = Math.abs(x);
  let rev = 0;
  while (cpyx > 0) {
    let rem = cpyx % 10;
    cpyx = Math.floor(cpyx / 10);
    rev = rev * 10 + rem;
  }
  if (rev > 2147483647) return 0;
  else {
    if (x < 0) {
      return rev * -1;
    } else return rev;
  }
}
let x = 1534236469;
let n = reverse(x);
console.log(n);
```
![[Screenshot 2025-08-08 at 23.40.10.png]]

# Cleaned up code 
```js
function reverse(x) {
  let cpyx = Math.abs(x);
  let rev = 0;
  while (cpyx !== 0) {
    rev = rev * 10 + (cpyx % 10);
    cpyx = Math.floor(cpyx / 10);
  }
  if (rev > 2147483647) return 0;
  return x < 0 ? -rev : rev;
}
let x = 1534236469;
let n = reverse(x);
console.log(n);
```
![[Screenshot 2025-08-08 at 23.33.20.png]]![[Screenshot 2025-08-09 at 00.11.17.png]]
