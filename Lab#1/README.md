# Lab#1 - Javascript (ES6) basics

1. Where to write javascript code?

   1. `script` tag in HTML

      ```html
      <html>
        <head></head>
        <body>
          <script>
            // Here goes your code
          </script>
        </body>
      </html>
      ```

   2. Included Javascript file

      ```html
      <html>
        <head></head>
        <body>
          <script src="path_to_js_file"></script>
        </body>
      </html>
      ```

2. Our first Hello World application in javascript.

   ```javascript
   // print to console
   console.log("Hello World");

   // print to HTML document
   document.write("Hello World");

   // print to an alert
   alert("Hello World");
   ```

3. Variables

   1. Primitives types

      - `Boolean`
      - `Null`
      - `Undefined`
      - `Number`
      - `String`
      - `Symbol`

   2. Declaration

      ```javascript
      // Old Javascript 'var' keyword
      var n = 12.5;

      // ES6 'let' keyword
      let b = true;

      // ES6 'const' keyword
      const s = "baNaNa";
      ```

4. Objects

   1. Definition

      ```javascript
      let person = {
        firstName: "John",
        lastName: "Doe"
      };
      ```

   2. Fields invocation

      ```javascript
      // Using '.' (dot) operator
      const name = person.firstName + " " + person.lastName;

      // Using associative array like syntax
      const lastName = person["lastName"];
      ```

   3. Object **destructuring**

      ```javascript
      let person = {
        firstName: "John",
        lastName: "Doe"
      };

      const personWithAge = {
        ...person,
        age: 23
      };
      ```

5. Functions | Arrow functions

   1. Normal function definition

      ```javascript
      // Normal function definition
      function abs(a) {
        return a < 0 ? -a : a;
      }

      // Anonymous function definition
      const add = function(a, b) {
        return a + b;
      };
      ```

   2. Arrow function definition

      ```javascript
      // Arrow function with multiple arguments and multiple lines in body
      const fn1 = (a, b) => {
        if (a == b) return 0;
        if (a > b) return 1;
        return -1;
      };

      // Arrow function with one argument and one line in body
      const fn2 = a => a % 2;
      ```

6. Arrays

   1. Declaration

      ```javascript
      const arr1 = [];
      let arr2 = [1, 2, 3, 0];
      const arr3 = [1, true, "string", {}];
      ```

   2. Associative arrays

      ```javascript
      const arr = [];
      arr[99] = false;
      arr["bar"] = "foo";
      ```

7. Operations on arrays

   1. `array.filter(fn)` creates a new array with all elements that pass the test implemented by the provided function `fn`.
   2. `array.map(fn)` creates a new array with the results of calling a provided function `fn` on every element in the calling array.
   3. `array.reduce(fn)` executes a reducer function `fn` on each member of the array resulting in a single output value.

   ```javascript
   const sumOfBalances = (accounts, name) =>
     accounts
       .filter(account => account.owner === name)
       .map(account => account.balance)
       .reduce((sum, cur) => sum + cur, 0);

   const accounts = [
     {
       num: "AB52CF5",
       owner: "John",
       balance: 1253.12
     },
     {
       num: "AF59R43",
       owner: "John",
       balance: 9862.15
     },
     {
       num: "ZX45AD7",
       owner: "Jane",
       balance: 3652.0
     },
     {
       num: "EG56F53",
       owner: "John",
       balance: 5999
     },
     {
       num: "36F5FG4",
       owner: "Jane",
       balance: 10000
     },
     {
       num: "PC5AA42",
       owner: "Noah",
       balance: -15.02
     }
   ];

   console.log("john : " + sumOfBalances(accounts, "John"));
   console.log("jane: " + sumOfBalances(accounts, "Jane"));
   console.log("jane: " + sumOfBalances(accounts, "Noah"));
   ```
