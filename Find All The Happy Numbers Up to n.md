
```js
function isHappy(num) {
  for (let i = 0; i < num.length; i++) {
    let digit1 = num[i];
    let sqr = 0;
    let counter = 0;
    let maxIterations = 1000;
    while (digit1 != 1) {
      if (counter >= maxIterations) {
        console.log("Unhappy Number");
        break;
      }
      if (sqr == 0 && sqr !== 1) {
        while (digit1 > 0) {
          let digit2 = digit1 % 10;
          sqr += digit2 * digit2;
          digit1 = Math.floor(digit1 / 10);
        }
        digit1 = sqr;
        sqr = 0;
        //console.log("Loop iteration:", counter);
        counter++;
      }
    }
    if (digit1 == 1) {
      console.log("Happy Number");
    }
  }
}

let n = 30;
let num = Array.from({ length: 20 }, (_, i) => i + 1);
isHappy(num);
//console.log(digit1)
//console.log(sqr)

```