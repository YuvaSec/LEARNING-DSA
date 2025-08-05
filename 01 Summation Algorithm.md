
or **Iterative Accumulation** or  **Linear Time Algorithm (O(n))**
##### DATA:
**Initial number: 5**
**Last number:35**
```JS
function addup(num) {
	let addnum = 0;
	for (let i = 0; i < num; i++) {
		addnum += i+5     //Here this will start adding up form 2+3+4+5+6
	}
	return addnum;
}
console.log(addup(35))
```
- **THIS CAN BE WRITTEN USING PLAIN MATH WITHOUT WHILE LOOP**
```js
function addupp(num) {
	//((fisrt number+last number)xtotal number)/2
		//((5+(num+4))*num)/2
			//or//
	return ((5 + (5+num-1)) * num) / 2;   // its the same.
}
console.log(addupp(35))
```