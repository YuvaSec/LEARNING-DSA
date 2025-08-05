From 1 to 30
- Print `"Fizz"` if the number is a **multiple of 3**
- Print `"Buzz"` if it's a **multiple of 5**
- Print `"Bazz"` if it's a **multiple of 7**
- Combine them if more than one applies:
    - e.g. 15 → `"FizzBuzz"`
    - e.g. 21 → `"FizzBazz"`
    - e.g. 105 → `"FizzBuzzBazz"`
```js
for (let i = 1; i <= 30; i++) {
	let x=""
	if (i % 3 == 0) {
		x += "Fizz"
	}
	if (i % 5 == 0) {
		x += "Buzz"
	}
	if (i % 7 == 0) {
		x += "Bazz"
	}
	if (x === "") {	
		x = i;          // if there is no string by now!
			    // It will just be "i"
	}
	console.log(x)
}
```
- **OPTIMIZED CODE**
```js
for (let i=1; i<=30; i++)
{
	let x ="";
	if (i % 3 === 0) x += "Fizz";
	if (i % 5 === 0) x += "Buzz";
	if (i % 7 === 0) x += "Bazz";
	if(x==="") x=i;
	console.log(x);
}
```
