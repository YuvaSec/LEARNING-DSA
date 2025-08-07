```js 
function howMany(n) {
  let counter = 0;
  if (n < 0) {
    n = n * -1;
  }
  let i = 0;
  while (n > 0) {
    n = Math.floor(n / 10);
    i++;
    counter++;
  }
  console.log(counter);
}
let n = 12345;
howMany(n);
```