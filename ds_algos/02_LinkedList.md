# LINKEDLIST
> Prerequisite: Knowledge in Class, Arrays

- It has HEAD and TAIL,
- each will point to the next element
- last element will point to null
- check [image](https://miro.medium.com/max/953/1*elJncKhH_P9oQglfI1aVQA.png)
- Unlike Array, LinkedList elements doesn't have to be in contigious order.

# Topics

---
Topic: **LL: Constructor** <br>
Explanation: Create a new Node. We also keep the length.

```javascript
  class Node {
    constructor(value){
      this.value = value;
      this.next = null
    }
  }
  class LinkedList {
    constructor(value) {
      const newNode = new Node(value);
      this.head = newNode
      this.tail = this.head
      this.lenght = 1
    }
  }
  let myLinkedList = new LinkedList(4);
  console.log(myLinkedList);
```

---
Topic: **LL: Push** <br>
Time Complexity: **O(1)** <br>
Explanation: add to the end and refer tail to newNode. Handle edge case where both head, tail refers to null. Increase length by 1

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
}
let myLinkedList = new LinkedList(7);
myLinkedList.push(4);
console.log(myLinkedList);
```

---
Topic: **LL: Pop** <br>
Time Complexity: **O(n)** <br>
Explanation: 
2 edge cases 
 - a. Where head, tail both points to null.
 - b. where head, tail both points to single element. 

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined; 
    let temp = this.head;
    let pre = this.hea
    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
}
let myLinkedList = new LinkedList(1);
myLinkedList.push(2);
myLinkedList.pop(); 
myLinkedList.pop(); //. head: null, tail: null, length: 0
console.log(myLinkedList.pop()); // undefined
console.log(myLinkedList);
```

---
Topic: **LL: Unshift**  <br>
Time Complexity: **O(1)**  <br>
Explanation:  1 edge case where head, tail point to null. 
- Create node.  
- Point head to new node. 
- Increment length

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined; 
    let temp = this.head;
    let pre = this.hea
    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
  unshift(value) {
   const newNode = new Node(value);
   if(!this.head) {
     this.head = newNode;
     this.tail = newNode;
   } else {
     newNode.next = this.head;
     this.head = newNode;
   }  
   this.length++;
   return this;
  }
}
let myLinkedList = new LinkedList(11);
myLinkedList.push(3);
myLinkedList.push(23);
myLinkedList.push(7);
console.log(myLinkedList);
myLinkedList.unshift(4);
console.log(myLinkedList
```


Topic: **LL: Shift** <br>
Time Complexity: **O(1)** <br>
Explanation:  2 edge cases 
- a. where head, tail point to null
- b. where head, tail point to single item
- decrement length

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined; 
    let temp = this.head;
    let pre = this.head;
    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
  unshift(value) {
   const newNode = new Node(value);
   if(!this.head) {
     this.head = newNode;
     this.tail = newNode;
   } else {
     newNode.next = this.head;
     this.head = newNode;
   }  
   this.length++;
   return this;
  }
  shift() {
    // edge case a.
    if(!this.head) return undefined;
    let temp = this.head;
    this.head = this.head.next;
    temp.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.tail = null;
    }
    return temp;
  }
}
let myLinkedList = new LinkedList(2);
myLinkedList.push(1);
console.log(myLinkedList);
myLinkedList.shift();
console.log(myLinkedList);
myLinkedList.shift(); 
console.log(myLinkedList); // head: null, tail: null
console.log(myLinkedList.shift()); // undefined
```

---
Topic: **LL: Get** <br>
Time Complexity: **O(n)** <br>
Explanation: We can't get negative index elements

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined; 
    let temp = this.head;
    let pre = this.head;
    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
  unshift(value) {
   const newNode = new Node(value);
   if(!this.head) {
     this.head = newNode;
     this.tail = newNode;
   } else {
     newNode.next = this.head;
     this.head = newNode;
   }  
   this.length++;
   return this;
  }
  shift() {
    // edge case a.
    if(!this.head) return undefined;
    let temp = this.head;
    this.head = this.head.next;
    temp.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.tail = null;
    }
    return temp;
  }
  get(index) {
    if(index < 0 || index >= this.length) {
      return undefined;
    }
    let temp = this.head;
    for(let i=0; i < index; i++) {
      temp = temp.next;
     }
     return temp;
  }
}
let myLinkedList = new LinkedList(0);
myLinkedList.push(1);
myLinkedList.push(2);
myLinkedList.push(3);
console.log(myLinkedList);
console.log(myLinkedList.get(-1)); // undefined
console.log(myLinkedList.get(10)); // undefined
console.log(myLinkedList.get(3)); // value:
```

---
Topic: **LL: Set** <br>
Time Complexity: ? <br>
Explanation: We use Get method 

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined; 
    let temp = this.head;
    let pre = this.head;
    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
  unshift(value) {
   const newNode = new Node(value);
   if(!this.head) {
     this.head = newNode;
     this.tail = newNode;
   } else {
     newNode.next = this.head;
     this.head = newNode;
   }  
   this.length++;
   return this;
  }
  shift() {
    // edge case a.
    if(!this.head) return undefined;
    let temp = this.head;
    this.head = this.head.next;
    temp.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.tail = null;
    }
    return temp;
  }
  get(index) {
    if(index < 0 || index >= this.length) {
      return undefined;
    }
    let temp = this.head;
    for(let i=0; i < index; i++) {
      temp = temp.next;
     }
     return temp;
  }
  set(index, value) {
    let temp = this.get(index);
    if(temp) {
      temp.value = value;
      return true;
    }
    return false;
  }
}
let myLinkedList = new LinkedList(11);
myLinkedList.push(3); // change this to 4
myLinkedList.push(23);
myLinkedList.push(7);
console.log(myLinkedList);
console.log(myLinkedList.set(1, 4)); // true
console.log(myLinkedList);
```

Topic: **LL: Insert** <br>
Time Complexity: **O(n)** <br>
Explanation: We use other methods

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined; 
    let temp = this.head;
    let pre = this.hea
    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
  unshift(value) {
   const newNode = new Node(value);
   if(!this.head) {
     this.head = newNode;
     this.tail = newNode;
   } else {
     newNode.next = this.head;
     this.head = newNode;
   }  
   this.length++;
   return this;
  }
  shift() {
    // edge case a.
    if(!this.head) return undefined;
    let temp = this.head;
    this.head = this.head.next;
    temp.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.tail = null;
    }
    return temp;
  }
  get(index) {
    if(index < 0 || index >= this.length) {
      return undefined;
    }
    let temp = this.head;
    for(let i=0; i < index; i++) {
      temp = temp.next;
     }
     return temp;
  }
  set(index, value) {
    let temp = this.get(index);
    if(temp) {
      temp.value = value;
      return true;
    }
    return false;
  }
  insert(index, value) {
    // insert at the beggining
    if(index === 0) return this.unshift(value);
    // insert at the end
    if(index === this.length) return this.push(value);
    // insert out of range
    if(index < 0 || index > this.length) return false;
    // insert in the middle
    const newNode = new Node(value);
    const temp = this.get(index-1);
    newNode.next = temp.next;
    temp.next = newNode;
    this.length++;
    return true;
  }
}
let myLinkedList = new LinkedList(0);
myLinkedList.push(2); // insert 1
console.log(myLinkedList);
console.log(myLinkedList.insert(1, 1)); // true
console.log(myLinkedList);
```

---
Topic: **LL: Remove** <br>
Time Complexity: **O(n)** <br>
Explanation: We use other method

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined; 
    let temp = this.head;
    let pre = this.head;
    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
  unshift(value) {
   const newNode = new Node(value);
   if(!this.head) {
     this.head = newNode;
     this.tail = newNode;
   } else {
     newNode.next = this.head;
     this.head = newNode;
   }  
   this.length++;
   return this;
  }
  shift() {
    // edge case a.
    if(!this.head) return undefined;
    let temp = this.head;
    this.head = this.head.next;
    temp.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.tail = null;
    }
    return temp;
  }
  get(index) {
    if(index < 0 || index >= this.length) {
      return undefined;
    }
    let temp = this.head;
    for(let i=0; i < index; i++) {
      temp = temp.next;
     }
     return temp;
  }
  set(index, value) {
    let temp = this.get(index);
    if(temp) {
      temp.value = value;
      return true;
    }
    return false;
  }
  insert(index, value) {
    // insert at the beggining
    if(index === 0) return this.unshift(value);
    // insert at the end
    if(index === this.length) return this.push(value);
    // insert out of range
    if(index < 0 || index > this.length) return false;
    // insert in the middle
    const newNode = new Node(value);
    const temp = this.get(index-1);
    newNode.next = temp.next;
    temp.next = newNode;
    this.length++;
    return true;
  }
  remove(index) {
    // insert from the beggining
    if(index === 0) return this.shift();
    // insert from end
    if(index === this.length - 1) return this.pop();
    // insert from out of range
    if(index < 0 || index >= this.length) return undefined;
    // insert from the middle
    const before = this.get(index - 1);
    const temp = before.nex
    before.next = temp.next;
    temp.next = null;
    this.length--;
    return temp;
  }
}
let myLinkedList = new LinkedList(0);
myLinkedList.push(3);
myLinkedList.push(23); // remove index 2
myLinkedList.push(7); 
console.log(myLinkedList);
console.log(myLinkedList.remove(2)); // true
console.log(myLinkedList
```


---
Topic: **LL: Reverse** <br>
Time Complexity: **O(n)** <br>
Explanation: More complicated

```javascript
class LinkedList {
  constructor(value) {
    const newNode = new Node(value);
    this.head = newNode
    this.tail = this.head
    this.length = 1
  }
  push(value) {
    const newNode = new Node(value);
    // edge case
    if(!this.head) {
      this.head = newNode;
      this.tail = newNode;
    } else {
      this.tail.next = newNode;
      this.tail = newNode;
    }
    this.length++;
    return this;
  }
  pop() {
    // edge case a.
    if(!this.head) return undefined;
    
    let temp = this.head;
    let pre = this.head;

    while(temp.next) {
      pre = temp;
      temp = temp.next;
    }
    this.tail = pre;
    this.tail.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.head = null;
      this.tail = null;
    }
  }
  unshift(value) {
   const newNode = new Node(value);
   if(!this.head) {
     this.head = newNode;
     this.tail = newNode;
   } else {
     newNode.next = this.head;
     this.head = newNode;
   }  
   this.length++;
   return this;
  }
  shift() {
    // edge case a.
    if(!this.head) return undefined;
    let temp = this.head;
    this.head = this.head.next;
    temp.next = null;
    this.length--;
    // edge case b.
    if(this.length === 0) {
      this.tail = null;
    }
    return temp;
  }
  get(index) {
    if(index < 0 || index >= this.length) {
      return undefined;
    }
    let temp = this.head;
    for(let i=0; i < index; i++) {
      temp = temp.next;
     }
     return temp;
  }
  set(index, value) {
    let temp = this.get(index);
    if(temp) {
      temp.value = value;
      return true;
    }
    return false;
  }
  insert(index, value) {
    // insert at the beggining
    if(index === 0) return this.unshift(value);
    // insert at the end
    if(index === this.length) return this.push(value);
    // insert out of range
    if(index < 0 || index > this.length) return false;
    // insert in the middle
    const newNode = new Node(value);
    const temp = this.get(index-1);
    newNode.next = temp.next;
    temp.next = newNode;
    this.length++;
    return true;
  }
  remove(index) {
    // insert from the beggining
    if(index === 0) return this.shift();
    // insert from end
    if(index === this.length - 1) return this.pop();
    // insert from out of range
    if(index < 0 || index >= this.length) return undefined;
    // insert from the middle
    const before = this.get(index - 1);
    const temp = before.next;

    before.next = temp.next;
    temp.next = null;
    this.length--;
    return temp;
  }
  reverse() {
    let temp = this.head;
    this.head = this.tail;
    this.tail = temp;

    let next = temp.next;
    let prev = null;
    for(let i = 0; i < this.length; i++) {
      next = temp.next;
      temp.next = prev;
      prev = temp;
      temp = next;
    }
    return this;
  }
}
let myLinkedList = new LinkedList(1);
myLinkedList.push(2);
myLinkedList.push(3); 
console.log(myLinkedList);
console.log(myLinkedList.reverse());
```

[NEXT: DOUBLYLINKEDLIST](/ds_algos/03_DoublyLinkedList.md)