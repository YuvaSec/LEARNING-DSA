# TIME COMPLEXITY

>TIME COMPLEXITY   ! =   TIME TAKEN RUN.
> “If my input doubles, how will ? the number of steps my algorithm takes, change.”

*Think of **time complexity** as a way to measure how the running time of an algorithm grows when the size of its input changes.*  Independent to the HARDWARE used.


#### Real-world analogy:  
Imagine you’re sorting a deck of cards.
- If you have **10 cards**, you can finish quickly.
- If you have **1,000 cards**, it will take "much longer".  
Time complexity measures how _fast_ that “much longer” grows compared to the number of cards.

![[output.png]]

### **1. O(1) — Constant Time**

The running time **doesn’t depend on the input size**.  
Example:

```js
function getFirstElement(arr) {
    return arr[0]; // Just 1 step, no matter how big arr is
}
```

- Even if `arr` has 10 or 10 million elements, it still takes the same time.
- Because It only returns the value in 0th position of the array.

---

### **2. O(log n) — Logarithmic Time**

The work **shrinks the problem by a constant fraction each time**.  
Typical in **binary search**: log2(n)


```js
function binarySearch(arr, target) {
    let left = 0, right = arr.length - 1;
    while (left <= right) {
        let mid = Math.floor((left + right) / 2);
        if (arr[mid] === target) return mid;
        else if (arr[mid] < target) left = mid + 1;
        else right = mid - 1;
    }
    return -1;
}
```

If you double the input size, it only adds **one extra step** in the worst case.

![[IMG_0858.png]]

### **3. O(n) — Linear Time**

The work grows **directly proportional to the input size**.  
Example:

```js
function printAll(arr) {
    for (let i = 0; i < arr.length; i++) {
        console.log(arr[i]); // Runs n times
    }
}
```
![[IMG_0859.jpg]]

---
### **4. O(n log n) — Linearithmic Time**

Common in **efficient sorting** like Merge Sort, Quick Sort (average case).  
- It basically Running a log2(n) loop inside a "n" loop for each.

---

### **5. O(n²) — Quadratic Time**

When every we see **nested loops** over the same data. its n²
Example:

```js
function printPairs(arr) {
    for (let i = 0; i < arr.length; i++) {
        for (let j = 0; j < arr.length; j++) {
            console.log(arr[i], arr[j]); // Runs n * n times
        }
    }
}
```

If you double the input size, the work becomes **4×** bigger.

---

### **6. O(2ⁿ) — Exponential Time**

Work **doubles** for each extra input element.  
Example: recursive solutions to problems like the Fibonacci sequence without memoization.

---

💡 **Cheat Sheet: Growth Rates**

```
Fast → Slow
O(1) < O(log n) < O(n) < O(n log n) < O(n²) < O(2ⁿ)
```


# SPACE COMPLEXITY

### **What is Space Complexity?**

It measures **how much extra memory** (RAM) an algorithm needs to run, as the input size changes.  

1. **Input space** — memory taken by the input data.
    
2. **Auxiliary space** — extra memory used by variables, arrays, stacks, etc.
    
3. **Function call stack** — memory used in recursion.


---

**Example:**

```js
function sumArray(arr) {
    let sum = 0; // 1 variable → O(1) space
    for (let i = 0; i < arr.length; i++) {
        sum += arr[i];
    }
    return sum;
}
```
 *This algorithm doesn’t create any extra data structures — so **space complexity = O(1)**.*

---

**Another Example:**

```js
function copyArray(arr) {
    let copy = []; // creates another array of size n → O(n) space
    for (let i = 0; i < arr.length; i++) {
        copy.push(arr[i]);
    }
    return copy;
}
```
*Here, extra memory grows with the input size — so **O(n) space**.*

---
### **Common Space Complexities**

| Space Complexity | Meaning              | Example                       |
| ---------------- | -------------------- | ----------------------------- |
| O(1)             | Constant space       | Using just a few variables    |
| O(log n)         | Space grows slowly   | Recursive binary search       |
| O(n)             | Space grows linearly | Storing a copy of input       |
| O(n²)            | Space grows rapidly  | 2D matrices like Star Pattern |

---

💡 **Key Insight:**  
A faster algorithm may use **more space** (time–space tradeoff), and a slower one may use less space.

---
