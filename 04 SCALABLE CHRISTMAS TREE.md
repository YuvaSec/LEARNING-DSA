
# CHRISTMAS TREE
```
let n = 20;
for (let i = 0; i < n; i++) {
  let row = "";
  for (let k = n; k > i; k--) {
    row += " ";
  }
  for (let j = 0; j <= i; j++) {
    row += "*" + " ";
  }
  console.log(row);
}
let n1 = n / 4;

for (let i = 0; i < n1; i++) {
  let row1 = "";
  for (let k = 0; k < n - n / 10; k++) {
    row1 += " ";
  }
  for (let j = 0; j < n1 / 2; j++) {
    row1 += "*" + " ";
  }
  console.log(row1);
}
```

# Scalable Trees
![[Screenshot 2025-08-07 at 22.44.23.png]]
```js
function tree(arry) {
  for (let a = 0; a < arry.length; a++) {
    let n = arry[a];
    for (let i = 0; i < n; i++) {
      let row = "";
      for (let k = n; k > i; k--) {
        row += " ";
      }
      for (let j = 0; j <= i; j++) {
        row += "*" + " ";
      }
      console.log(row);
    }
    let n1 = n / 4;
    let n2 = n - n / 10;
    let n3 = n1 / 2;

    for (let i = 0; i < n1; i++) {
      let row1 = "";
      for (let k = 0; k < n2; k++) {
        row1 += " ";
      }
      for (let j = 0; j < n3; j++) {
        row1 += "*" + " ";
      }
      console.log(row1);
    }
  }
}

let arry = [3, 5, 10, 15];
tree(arry);

```


#  Asked AI to Modify my code to standards 
![[Screenshot 2025-08-07 at 22.51.48.png]]
```js
function drawTree(heights) {
  heights.forEach((height) => {
    // 1. Draw the leafy part
    for (let row = 1; row <= height; row++) {
      // Number of leading spaces to center the stars
      const spaces = " ".repeat(height - row);
      // Create the stars for this row, separated by a space
      const leaves = "* ".repeat(row).trimEnd();
      console.log(spaces + leaves);
    }

    // 2. Calculate trunk dimensions (integers only)
    const trunkHeight = Math.max(1, Math.floor(height / 4)); // at least 1 row
    const trunkWidth =
      trunkHeight % 2 === 0 // make trunk width odd
        ? trunkHeight + 1
        : trunkHeight;
    // Center the trunk under the leaves: total leaf width is (height * 2 - 1)
    const totalLeafWidth = height * 2 - 1;
    const padding = " ".repeat(Math.floor((totalLeafWidth - trunkWidth) / 2));

    // 3. Draw the trunk
    for (let i = 0; i < trunkHeight; i++) {
      console.log(padding + "*".repeat(trunkWidth));
    }

    // 4. Blank line between trees
    console.log();
  });
}

// Example usage:
const sizes = [5, 10, 15];
drawTree(sizes);
```