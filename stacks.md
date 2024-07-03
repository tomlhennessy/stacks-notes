# Stacks

* Abstraction:
    • Abstract Data Types (ADTs) hide complexity, allowing high-level code interaction
    • Examples: Array functions like `shift()` and `splice()`

* Stacks:
    • ADT with Last In, First Out (LIFO) behaviour
    • Example: stack of plates - last plate is the first removed

* Operations:
    • `push`: add item to the top
    • `pop`: remove item from the top
    • Both operations are O(1) on average with dynamic arrays

* Stack Implementation in JavaScript:
    ```js
    class Stack {
        constructor() {
            this.data = [];
        }

        push(value) {
            this.data.push(value);
        }

        pop() {
            return this.data.pop();
        }

        size() {
            return this.data.length;
        }
    }

    const stackOfPlates = new Stack();
    stackOfPlates.push(`plate 1`);
    stackOfPlates.push(`plate 2`);
    stackOfPlates.pop(); // `plate 2`
    ```

* Applications:
    • Browser History:
        - `push` current URL on navigation
        - `pop` to go back

        ```js
        let browserHistory = [];
        let currentURL = `homepage`;

        function clickLink(newURL) {
            browserHistory.push(currentURL);
            currentURL = newURL;
        }

        function clickBack() {
            currentURL = browserHistory.pop();
        }
        ```

* Performance:
    • Time Complexity: O(1) for `push` and `pop` (average)
    • Space Complexity: O(n), efficient due to continuous storage


* Call Stack:
    • Manages function calls in LIFO order
    • Example: recursive function calls

    ```js
    function factorial(n) {
        if (n <= 1) return 1;
        return n * factorial(n - 1);
    }

    factorial(5); // call stack grows with each recursive call
    ```

* Recursive vs. Iterative Solutions:
    • Recursive functions have O(n) space complexity
    • Iterative solutions can reduce space complexity to O(1)

    ```js
    function factorialIterative(n) {
        let total = 1;
        for (let i = n; i > 0; i--) {
            total *= i;
        }
        return total;

    }
    ```

* Key Takeaways
    • Stacks follow LIFO
    • Implemented using arrays
    • Crucial for understanding function call management and practical applications like browser history
    • Recursive solutions have higher space complexity compared to iterative solutions
