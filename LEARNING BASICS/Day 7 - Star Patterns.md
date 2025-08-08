# Square Star Pattern
```js
let n = 5;
for (let i = 0; i < n; i++){
    let row = "";
    for (let j = 0; j < n; j++){
        row += " * ";
    }
    console.log(row)
}
```
![[Screenshot 2025-08-07 at 19.16.02.png]]


# Right Angle Triangle
```js
let n = 5;
for (let i = 0; i < n; i++) {
  let row = " ";
  for (let j = 0; j <= i; j++) {
    row += " " + "*" + " ";
  }
  console.log(row);
}
```
![[Screenshot 2025-08-07 at 19.32.56.png]]


# Inverse Right Angle Triangle
```js
let n = 5;
for (let i = 0; i < n; i++) {
  let row = " ";
  for (let j = n; j > i; j--) {
    row += " " + "*" + " ";
  }
  console.log(row);
}
```
![[Screenshot 2025-08-07 at 21.45.59.png]]

# Triangle
```js
let n = 5;
for (let i = 0; i < n; i++) 
{
  let row = "";
	  for (let k = n; k > i; k--) 
	  {
	    row += " ";
	  }
	  for (let j = 0; j <= i; j++) 
	  {
	    row += "*"+" ";
	  }
  console.log(row);
}
```
![[Screenshot 2025-08-07 at 21.37.15.png]]


# Inverted Triangle
```js
let n = 5;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j <= i; j++) {
    row += " ";
  }
  for (let k = n; k > i; k--) {
    row += "*" + " ";
  }
  console.log(row);
}
```
![[Screenshot 2025-08-07 at 21.41.25.png]]

# Number Stairs
![[Screenshot 2025-08-07 at 23.00.31.png]]
```js
let n = 10;

for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j <= i; j++) {
    row += " " + (j + 1);
  }
  console.log(row);
}
```
# Reverse Number Stairs
![[Screenshot 2025-08-07 at 23.21.48.png]]
```js
let n = 10;

for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = n; j > i; j--) {
    row += " " + (n - (j - 1));
  }
  console.log(row);
}
```

# Number Stairs
![[Screenshot 2025-08-07 at 23.54.42.png]]
```js
let n = 10;

for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = n; j > i + 1; j--) {
    row += "   ";
  }
  for (let k = 0; k <= i; k++) {
    row += " " + (n - (n - (k + 1))) + " ";
  }
  console.log(row);
}

```

# Repeating Number Stairs
![[Screenshot 2025-08-07 at 23.04.38.png]]
```js
let n = 8;

for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j <= i; j++) {
    row += " " + (i + 1);
  }
  console.log(row);
}

```

# Switching Pattern Stairs 
![[Screenshot 2025-08-08 at 00.11.31.png]]
- We can write this code in two ways one in my way another my teacher ways 
```js
// MY CODE //
let n = 10;

for (let i = 0; i < n; i++) {
  let row = "";
  for (let j = 0; j <= i; j++) {
    row += " " + ((j + 1) % 2) + " ";
  }
  console.log(row);
}
```

###  using ***switch variable.***(Switcher Inside loop)
```js
// Teacher CODE //
let n = 10;

for (let i = 0; i < n; i++) {
  let row = "";
  let switcher = 1;
  for (let j = 0; j <= i; j++) {
    row += " " + switcher + " ";
    if (switcher == 1) {
      switcher = 0;
    } else {
      switcher = 1;
    }
  }
  console.log(row);
}
```

# Switching Pattern Stairs (Switcher Outside loop)
![[Screenshot 2025-08-08 at 00.23.13.png]]