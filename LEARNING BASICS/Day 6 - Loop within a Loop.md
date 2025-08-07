# LOOP WITHIN A LOOP
```js
let counter = 0;
for(let i=0; i<3; i++){
	for(let j=0; j<3; j++){
	counter++ 
	}
}
```
# FixedNestedPrinter/ StaticLoop
```js
let counter = 0;
for (let i = 0; i < 3; i++) {
  console.log("i is" + " " + i);
  console.log("*******");
  for (let j = 0; j < 3; j++) {
    counter++;
    console.log("j is" + " " + j);
  }
  console.log("  *  ");
}
console.log("Total number of runs" + counter);
```

# IncrementalNestedPrinter / DynamicLoop
```js
let counter = 0;
for (let i = 0; i < 3; i++) {
  console.log("i is" + " " + i);
  console.log("*******");
  for (let j = 0; j < i; j++) {
    counter++;
    console.log("j is" + " " + j);
  }
  console.log("  *  ");
}
console.log("Total number of runs " + counter);
```
**This will create loop increments in j loop as the i gets larger.**
- if j <=i
```js
for (let i = 0; i < 3; i++){
    console.log(i)
    console.log("*")
    for (let j = 0; j <= i; j++){
        console.log(j + 1)
    }
    console.log("**")
}

```

# ReverseNestedPrinter / ReverseDynamicLoop
```js
for (let i = 0; i < 3; i++) 
{
	for (let j = 0; j <= i; j++) 
	{
	console.log("I is " + i + " " + "J is " + j)
	}
	console.log(" *** ")
}
```
# DescendingNestedPrinter / ReverseTieredLoop 
```js
for (let i = 3; i > 0; i--) 
{
    for (let j = 0; j <= i; j++) 
    {
        console.log("I is " + i + " " + "J is " + j)
    }
    console.log("     ***     ")
}

```