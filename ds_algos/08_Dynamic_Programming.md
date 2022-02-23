
# Dynamic Programming

Dynamic Programming (DP) is an algorithmic technique for solving an optimization problem by breaking it down into simpler subproblems and utilizing the fact that the optimal solution to the overall problem depends upon the optimal solution to its subproblems. [Reference](https://www.educative.io/courses/grokking-dynamic-programming-patterns-for-coding-interviews/m2G1pAq0OO0)

To decide whether problem can be solved by applying Dynamic programming we check for two properties. If problem has these two properties then we can solve that problem using Dynamic programming.

- [Overlapping Sub-problems](https://algorithms.tutorialhorizon.com/introduction-to-dynamic-programming-fibonacci-series/)
- [Optimal Substructure](https://algorithms.tutorialhorizon.com/introduction-to-dynamic-programming-fibonacci-series/)


### Video Tutorial
- [What is Dynamic Programming ?](https://www.youtube.com/watch?v=vYquumk4nWw&ab_channel=CSDojo)
- [Minimum steps to minimize n to 1](https://www.youtube.com/watch?v=f2xi3c1S95M) ==> [JS Solutions](https://www.geeksforgeeks.org/minimum-steps-minimize-n-per-given-condition/)

##### Key Notes:
- **Memoization:** Storing the results of expensive function calls and returning the cached result when the same inputs occur again.
- **Tabulation:** Tabulation is an approach where you solve a dynamic programming problem by first filling up a table, and then compute the solution to the original problem based on the results in this table.
- [Tabulation vs Memoization](https://www.geeksforgeeks.org/tabulation-vs-memoization/)
- **Cache:** is a hardware or software component that stores data so that future requests for that data can be served faster; the data stored in a cache might be the result of an earlier computation or a copy of data stored elsewhere.
- **Recursion:** is a method of solving a problem where the solution depends on solutions to smaller instances of the same problem. 
- [Overlapping Subproblems](https://www.geeksforgeeks.org/overlapping-subproblems-property-in-dynamic-programming-dp-1/)


### Code
Memoized solution for fibonacci series. [Video Explanation](https://www.youtube.com/watch?v=e0CAbRVYAWg&ab_channel=CSDojo)

```javascript

function fib(n, memo=[]) {
    if(memo(n) !=== undefined) return memo[n]
    if(n <= 2) return 1;
    let res = fib(n-1, memo) + fib(n-2, memo);
    memo[n] = res;
    return res;
}

```
Tabulation solution for fibonacci series. [Text Explanation](https://www.geeksforgeeks.org/overlapping-subproblems-property-in-dynamic-programming-dp-1/)

```javascript

function fib(n){
    if(n <= 2) return 1;
    var fibNums = [0,1,1];
    for(var i = 3; i <= n; i++){
        fibNums[i] = fibNums[i-1] + fibNums[i-2];
    }
    return fibNums[n];
}

```

### Big O
- Without using DP but only recursion time comlexity: **T(n) = T(n-1) + T(n-2) + 1 = 2^n = O(2^n)**
- With DP: Memoized Solution: **O(n) time | O(n) space**
- [Reference](https://algorithms.tutorialhorizon.com/introduction-to-dynamic-programming-fibonacci-series/)


### Problem Set
- [Basic Problems](https://www.geeksforgeeks.org/dynamic-programming/#basicProblems)
- [Leetcode - Climbing Stairs](https://www.youtube.com/watch?v=Y0lT9Fck7qI&ab_channel=NeetCode)

### Extra Video Explanation
- [CS Dojo](https://www.youtube.com/watch?v=vYquumk4nWw&ab_channel=CSDojo)
