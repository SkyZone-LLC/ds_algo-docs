# Big O Notation Introduction with Examples
> To see results call each function: functionName(value)

## TOPICS

Topic: **BIG O: O(n)**<br>
Time Complexity: **O(n)**  

```javascript
function logItems(n){
  for(let i=0; i < n; i++) {
    console.log(i);
  }
}
```

--- 
Topic: **Drop Contstants** <br>
Time Complexity: **O(n)** <br>
Explanation: n + n = 2n => O(2n) But simplify to drop the constant 2,3,4 ...

```javascript
function logItems2(n){
  for(let i=0; i < n; i++) { // n
    console.log(i);
  }
  for(let j=0; j < n; j++) { // n
    console.log(j);
  }
}
```

--- 
Topic:  **BIG O: O(n^2)** <br>
Time Complexity: **n x n = n^2 => O(n^2)** <br>
Explanation: Usually you want to avoid nested loops, since its considered inefficient and slow code

```javascript
function logItems3(n){
  for(let i=0; i < n; i++) { // n
    for(let j=0; j < n; j++) { // n
      console.log(i, j);
    }
  }
}
``` 
Time Complexity: **n x n * n = n^3 => O(n^2) time complexity** <br>
Explanation: Doesn't matter how many deep we go still n^2

 ```javascript
function logItems3two(n){
  for(let i=0; i < n; i++) { // n
    for(let j=0; j < n; j++) { // n
      for(let k=0; k < n; k++) { // n
        console.log(i, j, k);
      }
    }
  }
}
```

--- 
Topic: **Drop Non-Dominants** <br>
Time Complexity: **n x n + n = O(n^2 + n) ~ O(n^2)** <br>
Explanation: we dropped non-dominat + n

```javascript
 function logItems4(n){
  for(let i=0; i < n; i++) { 
    for(let j=0; j < n; j++) { 
      console.log(i, j);
    }
  }
  for(let k=0; k < n; k++) { 
    console.log(k);
  }
}
```

---
Topic: **BIG O: O(1) - Constant time** <br>
Time Complexity: **O(1)** <br>
Explanation: we only perform single operation. Regardless of how many n's we add. We still equate it to `O(1) (O(2), O(3), ... => O(1))`

```javascript
function addItems(n) {
  return n + n; // same
}
function addItems(n) {
  return n + n + n; // same 
}
```

---
Topic: **BIG O: O(log n)** <br>
Time Complexity: **O(log n)** <br>
Explanation: Log in Big O has always have base of 2. Not 10 like in math. 2^x = N <br>
Example algorithm: Divide and Conquer

**O(nlog n)** is the best you can make for somne sorting algorithms.

Example for above 2 will be in sorting algorithms topic


---
Topic: **Different Terms for Input** <br>
Time Complexity: **Depends** <br>
Explanation: Inputs values can be different. You can't ignore either of them.
 
```javascript 
function logItems5(a, b) { // O(a + b)
  for(let i=0; i < a; i++) { 
    console.log(i);
  }
  for(let k=0; k < b; k++) { 
    console.log(k);
  }
}
 function logItems6(a, b) { // O(a * b)
  for(let i=0; i < a; i++) { 
    for(let k=0; k < b; k++) { 
      console.log(i, k);
    }
  }
}
```

---
Topic: **BIG O: Arrays** <br>
Time Complexity: **Depends**

**Explanation:** We don't reindex anything

```javascript 
const someArray = [];
someArray.push() // O(1) 
someArray.pop() // O(1)
```

**Explanation:** We have to reindex elements

```javascript 
someArray.shift() // O(n) 
someArray.unshift() // O(n)
someArray.splice(1,0,'someVal') // O(1/2n) ~ O(n)
```

**Explanation:** Searching in an array is O(1) since we use index to find element <br>
But if you use arrays for lots of removing-adding operations. <br>
Consider using differnet data structure <br>

---
Topic: **BIG O: Some Namings** <br>
Explanation: You might hear these words used.

```javascript
O(1): constant
O(n): proportional
O(log n): divide and conquer
O(n^2): loop within a loop
```


