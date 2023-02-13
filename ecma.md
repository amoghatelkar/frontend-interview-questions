# ECMAScript Features or Cheatsheet

> Click :star:if you like the project. Pull Request are highly appreciated. Follow me [@SudheerJonna](https://twitter.com/SudheerJonna) for technical updates.

## Downloading PDF/Epub formats

You can download the PDF and Epub version of this repository from the latest run on the [actions tab](https://github.com/sudheerj/ECMAScript-cheatsheet/actions).

## How to run examples
```cmd
npm install
npx babel-node es2020/bigint // Try other examples too
```

# What is ECMAScript?

**ECMAScript** is the scripting language which acts as the basis of JavaScript. ECMAScript standardized by the ECMA International standards organization in the ECMA-262 and ECMA-402 specifications.
Each proposal for an ECMAScript feature goes through the following maturity stages:

1. Stage 0: Strawman;
2. Stage 1: Proposal;
3. Stage 2: Draft;
4. Stage 3: Candidate;
5. Stage 4: Finished.


## Version History

| Edition | Date |
| --- | --------- |
| ES2015 Or ES6  | June 2015 |
| ES2016 Or ES7  | June 2016 |
| ES2017 Or ES8  | June 2017 |
| ES2018 Or ES9  | June 2018 |
| ES2019 Or ES10  | June 2019 |
| ES2020 Or ES11  | June 2020 |
| ES2021 Or ES12  | June 2021 |

### Table of Contents

| No. | Feature |
| --- | --------- |
|   | **ES2015 Or ES6** |
|1  | [Variable Scoping](#variable-scoping) |
|2  | [Arrow functions](#arrow-functions) |
|3  | [Classes](#classes) |
|4  | [Enhanced object literals](#Enhanced-object-literals) |
|5  | [Template literals](#template-literals) |
|6  | [Destructuring](#destructuring) |
|7  | [Default parameters](#default-parameters) |
|8  | [Rest parameter](#rest-parameter) |
|9  | [Spread Operator](#spread-operator) |
|10 | [Iterators & For..of](#iterators-&-forof) |
|11 | [Generators](#generators) |
|12 | [Modules](#modules) |
|13 | [Set](#set) |
|14 | [Weakset](#weakset) |
|15 | [Map](#map) |
|16 | [Weakmap](#weakmap) |
|17 | [Unicode](#unicode) |
|18 | [Proxies](#proxies) |
|19 | [Symbols](#symbols) |
|20 | [Promises](#promises) |
|21 | [Reflect](#reflect) |
|22 | [Binary and Octal](#binary-and-octal) |
|23 | [Proper Tail calls](#proper-tail-calls)|
|24 | [Array find methods](#array-find-methods)
|   | **ES2016 Or ES7** |
|1  | [Array includes](#array-includes) |
|2  | [Exponentiation Operator](#exponentiation-operator) |
|   | **ES2017 Or ES8** |
|1  | [Async functions](#async-functions) |
|2  | [Object values](#object-values) |
|3  | [Object entries](#object-entries) |
|4  | [Object property descriptors](#object-property-descriptors) |
|5  | [String padding](#string-padding)|
|6  | [Shared memory and atomics](#shared-memory-and-atomics)|
|7  | [Trailing commas](#trailing-commas) |
|   | **ES2018 Or ES9**|
|1  | [Async iterators](#async-iterators) |
|2  | [Object rest and spread operators](#object-rest-and-spread-operators) |
|3  | [Promise finally](#promise-finally) |
|   | **ES2019 Or ES10**|
|1  | [Array flat and flatMap](#array-flat-and-flatmap) |
|2  | [Object formEntries](#object-formentries) |
|3  | [String trimStart and trimEnd](#string-trimstart-and-trimend) |
|4  | [Symbol description](#symbol-description)|
|5  | [Optional Catch Binding](#optional-catch-binding)|
|6  | [JSON Improvements](#json-improvements)|
|7  | [Array Stable Sort](#array-stable-sort)|
|8  | [Function.toString()](#functiontostring())|
|9  | [Private Class Variables](#private-class-variables)|
|   | **ES2020 Or ES11**|
|1  | [BigInt](#bigint) |
|2  | [Dynamic Import](#dynamic-import) |
|3  | [Nullish Coalescing Operator](#nullish-coalescing-operator)|
|4  | [Optional chaining](#optional-chaining)|
|5  | [Promise allSettled](#promiseallsettled)|
|6  | [String matchAll](#string-matchall)|
|7  | [globalThis](#globalthis)|
|8  | [import.meta](#importmeta)|
|9  | [for..in order](#forin-order)|
|   | **ES2021 Or ES12**|
|1  | [replaceAll](#replaceall) |
|2  | [promise.any](#promiseany) |
|3  | [WeakRef](#weakref)|
|4  | [Numeric Separators](#numeric-separators)|
|5  | [Logical Operators](#logical-operators)|

## ES2015 Or ES6

1. ### Variable Scoping

    The variable scoping determines the visibility or accessibility of a variable within the certain part of the program or region.

    In ES6, both `const` and `let` keywords allow developers to declare variables in the block scope.

    The `let` statement declares a block-scoped local variable which can be reassigned. i.e, `let` declaration creates a mutable variable.

    ```js
    let a = 1;

    if (a === 1) {
      let a = 2;

      console.log(a); //2
    }

    console.log(a); //1
    ```

    **const** variables are similar to **let** variables but they can't be changed through reassignment. i.e, The const declaration creates a read-only reference to a value.

    ```js
    const x = 1;

    if (x === 1) {
        const y = 2; // You cannot re-assign the value similar to let variable

        console.log(y); //2
    }

    console.log(x); //1
    ```

    **[⬆ Back to Top](#table-of-contents)**

2. ### Arrow functions

    The arrow functions provides a more concise syntax for writing function expressions by opting out the function and return keywords using fat arrow(=>) notation. Let's see how this arrow function looks like,

    ```js
    // Function Expression
    var multiplyFunc = function(a, b) {
      return a * b;
    }
    console.log(multiplyFunc(2, 5)); // 10

    // Arrow function
    var multiplyArrowFunc = (a, b) => a * b;
    console.log(multiplyArrowFunc(2, 5)); // 10
    ```
    You can also skip parenthesis(()) if the function has exactly one parameter(either zero or more than one parameter). Apart from this, you can wrap braces({}) if the function has more than one expression in the body.

    Let's list down all the variations of arrow functions,
    ```js
    //1. Single parameter and single statement
    const message = name => console.log("Hello, " + name + "!");
    message("Sudheer"); // Hello, Sudheer!

    //2. Multiple parameters and single statement
    const multiply = (x, y) => x * y;
    console.log(multiply(2, 5)); // 10

    //3. Single parameter and multiple statements
    const even = number => {
      if(number%2) {
        console.log("Even");
      } else {
        console.log("Odd");
      }
    }
    even(5); // odd

    //4. Multiple parameters and multiple statements
    const divide = (x, y) => {
      if(y != 0) {
        return x / y;
      }
    }
    console.log(divide(100, 5)); // 20

    //5. No parameter and single statement
    const greet = () => console.log('Hello World!');
    greet(); // Hello World!
    ```

    **[⬆ Back to Top](#table-of-contents)**

3. ### Classes
    The classes are introduced as syntactic sugar over existing prototype based inheritance and constructor functions. So this feature doesn't bring new object-oriented inheritance model to JavaScript.

    There are two ways to define classes,

    1. **Class declarations:**

    ```js
    class Square {
      constructor(length) {
        this.length = length;
      }

      get area() {
        return this.length * this.length;
      }

      set area(value) {
        this.area = value;
      }
    }
    ```
    2. **Class expressions:**

    ```js
    const square = class Square {
      constructor(length) {
        this.length = length;
      }

      get area() {
        return this.length * this.length;
      }

      set area(value) {
        this.area = value;
      }
    }
    ```

    You can use **extend** keyword to use inheritance. This enables the subclass to get all features of a parent class.

    ```js
    class Vehicle {
      constructor(name) {
        this.name = name;
      }

      start() {
        console.log(`${this.name} vehicle started`);
      }
    }

    class Car extends Vehicle {
      start() {
        console.log(`${this.name} car started`);
      }
    }

    const car = new Car('BMW');
    console.log(car.start()); // BMW car started
    ```

    **Note:** Even though ES6 classes looks similar to classes in other object oriented languages, such as Java, PHP, etc but they do not work exactly the same way.

    **[⬆ Back to Top](#table-of-contents)**

4. ### Enhanced object literals

    Object literals are extended to support setting the prototype at construction, shorthand for foo: foo assignments, defining methods, making super calls, and computing property names with expressions.

    The important enhancements of object literals are,

    1. **Property Shorthand:**

    Object's properties are often created from variables with the same name.

    Let's see the ES5 representation

    ```js
    var a = 1, b = 2, c = 3,
      obj = {
        a: a,
        b: b,
        c: c
      };
      console.log(obj);
    ```
    and it can be represented in a shorter syntax as below,

    ```js
    const a = 1, b = 2, c = 3;
    const obj = {
      a,
      b,
      c
    };
    console.log(obj);
    ```

    2. **Method Shorthand:**
    In ES5, Object methods require the function statement as below,

    ```js
    var calculation = {
      sum: function(a, b) { return a + b; },
      multiply: function(a, b) { return a * b; }
    };

    console.log(calculation.sum(5, 3));  // 8
    console.log(calculation.multiply(5, 3)); // 15
    ```

    This can be avoided in ES6,

    ```js
    const calculation = {
      sum(a, b) { return a + b; },
      multiply(a, b) { return a * b; }
    };

    console.log(calculation.sum(5, 3));  // 8
    console.log(calculation.multiply(5, 3)); // 15
    ```

    3. **Computed Property Names:**
    In ES5, it wasn’t possible to use a variable for a key name during object creation stage.

    ```js
    var
      key = 'three',
      obj = {
        one: 1,
        two: 2
      };

    obj[key] = 3;
    ```

    Object keys can be dynamically assigned in ES6 by placing an expression in square brackets([])

    ```js
    const
      key = 'three',
      computedObj = {
        one: 1,
        two: 2,
        [key]: 3
      };
    ```

    **[⬆ Back to Top](#table-of-contents)**

5. ### Template literals
    Prior to ES6, JavaScript developers would need to do ugly string concatenation to creat dynamic strings.

    Template literals allows you to work with strings in a new way compared to ES5. These are just string literals allowing embedded expressions denoted by the dollar sign and curly braces (`${expression}`). Also, these literals are enclosed by the backtick (`` ` ``) character instead of double or single quotes.

    ES6 has two new kinds of literals:

    1. **Template literals:** string literals which exists across multiple lines and include interpolated expressions(i.e, ${expression})

    ```js
    const firstName = 'John';
    console.log(`Hello ${firstName}!
    Good morning!`);
    ```

    2. **Tagged template literals:** Function calls which are created by mentioning a function before a template literal.

    The real world use case is creating components in CSS-In-JS styled components to use across the application

    ```js
    const Button = styled.a`
      display: inline-block;
      border-radius: 3px;
    `
    ```

    **[⬆ Back to Top](#table-of-contents)**

6. ### Destructuring

    Destructuring is a javascript expression for extracting multiple values from data stored in objects(properties of an object) and Arrays.

    **Object destructuring:**

    This feature is used to extract values from an object.

    ```js
    const user = { firstName: 'John', lastName: 'Kary' };
    const {firstName, lastName} = user;
    console.log(firstName, lastName); // John, Kary
    ```

    **Array destructuring:**

    This feature is used to extract values from an array.

    ```js
    const [one, two, three] = ['one', 'two', 'three'];
    console.log(one, two, three); // one, two, three
    ```

    You can use destructing in below places,

    1. Variable declarations
    2. Assignments
    3. Parameter definitions
    4. for-of loop

    **[⬆ Back to Top](#table-of-contents)**

7. ### Default parameters

    Default parameters allow named parameters of a function to be initialized with default values if no value or undefined is passed.

    Prior to ES6, you need check for undefined values and provide the default value for undefined values using if/else or ternary operator
    ```js
    function add(a, b) {
      a = (typeof a !== 'undefined') ? a : 10;
      b = (typeof b !== 'undefined') ? b : 20;
      return a + b;
    }
    add(20); // 40
    add(); // 30
    ```
    In ES6, these checks can be avoided using default parameters

    ```js
    function add(a = 10, b = 20) {
      return a + b;
    }
    add(20); // 40
    add(); // 30
    ```

    **[⬆ Back to Top](#table-of-contents)**

8. ### Rest parameter
    The rest parameter is used to represent an indefinite number of arguments as an array. The important point here is only the function's last parameter can be a "rest parameter". This feature has been introduced to reduce the boilerplate code that was induced by the arguments.

    ```js
    function sum(...args) {
      return args.reduce((previous, current) => {
        return previous + current;
      });
    }

    console.log(sum(1, 2, 3)); // 6
    console.log(sum(1, 2, 3, 4)); // 10
    console.log(sum(1, 2, 3, 4, 5)); // 15
    ```

    **[⬆ Back to Top](#table-of-contents)**

9. ### Spread Operator
    Spread Operator allows iterables( arrays / objects / strings ) to be expanded into single arguments/elements.

    1. In function and constructor calls, the spread operator turns iterable values into arguments

    ```js
    console.log(Math.max(...[-10, 30, 10, 20])); //30
    console.log(Math.max(-10, ...[-50, 10], 30)); //30
    ```
    2. In Array literals and strings, the spread operator turns iterable values into Array elements

    ```js
    console.log([1, ...[2,3], 4, ...[5, 6, 7]]); // 1, 2, 3, 4, 5, 6, 7
    ```

    **Note:** The spread syntax is opposite of rest parameter.

    **[⬆ Back to Top](#table-of-contents)**

10. ### Iterators & For..of

    String, Array, TypedArray, Map, and Set are all built-in iterables but objects are not iterables by default.
    Iterators are a new way to loop over any collection in JavaScript. These are objects which defines a sequence and potentially a return value upon its termination.
    An iterator implements the Iterator protocol by having a next() method that returns an object with two properties:

    1. **value:** The next value in the iteration sequence.
    2. **done:** returns rue if the last value in the sequence has already been consumed.

    You can make the object iterable by defining a `Symbol.iterator` property on it.

    ```js
    const collection = {
      one: 1,
      two: 2,
      three: 3,
      [Symbol.iterator]() {
        const values = Object.keys(this);
        let i = 0;
        return {
          next: () => {
            return {
              value: this[values[i++]],
              done: i > values.length
            }
          }
        };
      }
    };

    const iterator = collection[Symbol.iterator]();

    console.log(iterator.next());    // → {value: 1, done: false}
    console.log(iterator.next());    // → {value: 2, done: false}
    console.log(iterator.next());    // → {value: 3, done: false}
    console.log(iterator.next());    // → {value: undefined, done: true}

    for (const value of collection) {
      console.log(value);
    }
    ```

    The for...of statement creates a loop iterating over user defined collection object. But this loop can be used for built-in objects too.

    **Note:** The abrupt iteration termination can be caused by break, throw or return.

    **[⬆ Back to Top](#table-of-contents)**

11. ### Generators
    A generator is a function that can stop or suspend midway and then continue from where it stopped while maintaining the context(saved across re-entrances). It can be defined using a function keyword followed by an asterisk(i.e, function* ()).

    This function returns an iterator object and this iterator's **next()** method returns an object with a value property containing the yielded value and a done property which indicates whether the generator has yielded its last value.

    ```js
    function* myGenerator(i) {
      yield i + 10;
      yield i + 20;
      return i + 30;
    }

    const myGenObj = myGenerator(10);

    console.log(myGenObj.next().value); // 20
    console.log(myGenObj.next().value); // 30
    console.log(myGenObj.next().value); // 40
    ```

    **Note:** We can use `yield*` to delegate to another generator function

    **[⬆ Back to Top](#table-of-contents)**

12. ### Modules
    Modules are small units of independent, reusable code to be used as the building blocks in a Javascript application.

    Prior to ES6, there was no native modules support in JavaScript. There were 3 major module standards used,

       1. Asynchronous Module Definition (AMD)
       2. RequireJS Modules
       3. CommonJS Modules (module.exports and require syntax used in Node.js)

    ES6 has provided the built-in support for modules. Everything inside a module is private by default, and runs in strict mode. Public variables, functions and classes are exposed using `export` statement and import the same using `import` statement.

    **Export Statement:**

    There are two types of exports:

    1. Named Exports (Zero or more exports per module)

    You can export each element or a single export statement to export all the elements at once

    ```js
    // module "my-module.js"

    const PI = Math.PI;

    function add(...args) {
      return args.reduce((num, tot) => tot + num);
    }

    function multiply(...args) {
      return args.reduce((num, tot) => tot * num);
    }

    // private function
    function print(msg) {
      console.log(msg);
    }

    export { PI, add, multiply };
    ```

    2. Default Exports (One per module)

    If we want to export a single value, you could use a default export

    ```js
    // module "my-module.js"

    export default function add(...args) {
      return args.reduce((num, tot) => tot + num);
    }
    ```

    **Import Statement:**

    The static import statement is used to import read only live bindings which are exported by another module.

    There are many variations of import scenarios as below,

    ```js
    // 1. Import an entire module's contents
    import * as name from "my-module";

    //2.Import a single export from a module
    import { export1 } from "my-module";

    //3.Import multiple exports from a module
    import { export1 , export2 } from "my-module";

    //4.Import default export from a module
    import defaultExport from "my-module";

    //5.Import an export with an alias
    import { export1 as alias1 } from "my-module";

    ```

    **[⬆ Back to Top](#table-of-contents)**

13. ### Set

    Set is a built-in object to store collections of unique values of any type.

    ```js
    let mySet = new Set()

    mySet.add(1);
    mySet.add(2);
    mySet.add(2);
    mySet.add('some text here');
    mySet.add({one: 1, two: 2 , three: 3});
    console.log(mySet); // Set [ 1, 2, 'some text here', {one: 1, two: 2 , three: 3} ]
    console.log(mySet.size) // 4
    console.log(mySet.has(2)); // true
    ```

    **[⬆ Back to Top](#table-of-contents)**

14. ### Weakset

    The Set is used to store any type of data such as primitives and object types. Whereas WeakSet is an object to store weakly held objects in a collection. (i.e, WeakSet is the collections of objects only). Here weak means,  If no other references to an object stored in the WeakSet exist, those objects can be garbage collected.

    ```js
    let myUserSet = new WeakSet();

    let john = { name: "John" };
    let rocky = { name: "Rocky" };
    let alex = { name: "Alex" };
    let nick = { name: "Nick" };

    myUserSet.add(john);
    myUserSet.add(rocky);
    myUserSet.add(john);
    myUserSet.add(nick);

    console.log(myUserSet.has(john)); // true
    console.log(myUserSet.has(alex)); // false
    console.log(myUserSet.delete(nick));
    console.log(myUserSet.has(nick)); // false

    john = null;
    ```

    **[⬆ Back to Top](#table-of-contents)**

15. ### Map

    Map is a collection of elements where each element is stored as a Key, value pair. It can hold both objects and primitive values as either key or value and iterates its elements in insertion order.

    Let's take a map with different types of primitives and objects as key-value pairs and various methods on it,

    ```js
    let typeMap = new Map();

    var keyObj = {'one': 1}

    typeMap.set('10', 'string');   // a string key
    typeMap.set(10, 'number');     // a numeric key
    typeMap.set(true, 'boolean');  // a boolean key
    typeMap.set(keyObj, 'object'); // an object key


    console.log(typeMap.get(10));         // number
    console.log(typeMap.get('10'));       // string
    console.log(typeMap.get(keyObj));     // object
    console.log(typeMap.get({'one': 1})); // undefined

    console.log(typeMap.size ); // 3

    for(let item of typeMap) {
      console.log(item);
    }


    for(let item in typeMap) {
      console.log(item);
    }
    ```

    **[⬆ Back to Top](#table-of-contents)**

16. ### Weakmap

    WeakMap object is a collection of key/value pairs in which the keys are weakly referenced. For this object, the keys must be objects and the values can be arbitrary values.

    Let's see various methods of weakmap with below example,

    ```js
    var weakMap = new WeakMap();

    var obj1 = {}
    var obj2 = {}


    weakMap.set(obj1, 1);
    weakMap.set(obj2, 2);
    weakMap.set({}, {"four": 4});

    console.log(weakMap.get(obj2)); // 2
    console.log(weakMap.has({})); // return false even though empty object exists as key. Because the keys have different references

    delete obj2;
    console.log(weakMap.get(obj2)); // 2
    weakMap.delete(obj1)
    console.log(weakMap.get(obj1)); //undefined
    ```

    **[⬆ Back to Top](#table-of-contents)**

17. ### Unicode

    Prior to ES6, JavaScript strings are represented by 16-bit character encoding (UTF-16). Each character is represented by 16-bit sequence known as code unit. Since the character set is been expanded by Unicode, you will get unexpected results from UTF-16 encoded strings containing surrogate pairs(i.e, Since it is not sufficient to represent certain characters in just 16-bits, you need two 16-bit code units).

    ```js
    let str = '𠮷';

    console.log(str.length);            // 2
    console.log(text.charAt(0));        // ""
    console.log(text.charAt(1));        // ""
    console.log(text.charCodeAt(0));    // 55362(1st code unit)
    console.log(text.charCodeAt(1));    // 57271(2nd code unit)

    console.log(/^.$/.test(str)); // false, because length is 2
    console.log('\u20BB7'); // 7!(wrong value)
    console.log(str === '\uD842\uDFB7'); // true
    ```

    ECMAScript 6 added full support for UTF-16 within strings and regular expressions. It introduces new Unicode literal form in strings and new RegExp u mode to handle code points, as well as new APIs(codePointAt, fromCodePoint) to process strings.

    ```js
    let str = '𠮷';

    // new string form
    console.log('\u{20BB7}'); // "𠮷"

    // new RegExp u mode
    console.log(new RegExp('\u{20BB7}', 'u'));
    console.log(/^.$/u.test(str)); // true

    //API methods
    console.log(str.codePointAt(0)); // 134071
    console.log(str.codePointAt(1)); // 57271

    console.log(String.fromCodePoint(134071)); // "𠮷"
    ```

    **[⬆ Back to Top](#table-of-contents)**

18. ### Symbols

    Symbol is a new peculiar primitive data type of JavaScript, along with other primitive types such as string, number, boolean, null and undefined. The new symbol is created just by calling the Symbol function. i.e, Every time you call the Symbol function, you’ll get a new and completely unique value. You can also pass a parameter to Symbol(), which is useful for debugging purpose only.

    Even though equality checks on two symbols is always false, it will be true while comparing symbols with `.for` method due to global registry (i.e, Symbols.for('key') === Symbols.for('key'))

    These symbols are useful to uniquely identify properties or unique constants,

    ```js
    //1. Object properties
    let id = Symbol("id");
    let user = {
      name: "John",
      age: 40,
      [id]: 111
    };

    for (let key in user) {
    console.log(key); // name, age without symbols
    }

    console.log(JSON.stringify(user)); // {"name":"John", "age": 40}
    console.log(Object.keys(user)); // ["name", "age"]

    console.log( "User Id: " + user[id] ); // Direct access by the symbol works

    //2. Unique constants
    const logLevels = {
      DEBUG: Symbol('debug'),
      INFO: Symbol('info'),
      WARN: Symbol('warn'),
      ERROR: Symbol('error'),
    };
    console.log(logLevels.DEBUG, 'debug message');
    console.log(logLevels.INFO, 'info message');

    //3. Equality Checks

    console.log(Symbol('foo') === Symbol('foo')); // false
    console.log(Symbol.for('foo') === Symbol.for('foo')); // true
    ```

    **[⬆ Back to Top](#table-of-contents)**

19. ### Proxies
    The Proxy object is used to create a proxy for another object, which can intercept and redefine fundamental operations for that object such as property lookup, assignment, enumeration, function invocation etc. These are used in many libraries and some browser frameworks.

    The proxy object is created with two parameters with below syntax,

    ```js
    let proxy = new Proxy(target, handler)
    ```

    1. **target:** Object on which you want to proxy
    2. **handler:** An object that defines which operations will be intercepted and how to redefine them.

    The property Lookup Behavior of a user proxied object will be as below,

    ```js
    const target = {
      name: "John",
      age: 3
    };

    const handler = {
      get: function(target, prop) {
        return prop in target ?
            target[prop] :
            `${prop} does not exist`;
      }
    };

    const user = new Proxy(target, handler);
    console.log(user.name); // John
    console.log(user.age); // 3
    console.log(user.gender); // gender does not exist
    ```

    These proxies also enforce value validations. Let's take an example with set handler,

    ```js
    let ageValidator = {
      set: function(obj, prop, value) {
        if (prop === 'age') {
          if (!Number.isInteger(value)) {
            throw new TypeError('The age is not an integer');
          }
          if (value > 200) {
            throw new RangeError('Invalid age');
          }
        }

        obj[prop] = value; // The default behavior to store the value

        return true; // Indicate success
      }
    };

    const person = new Proxy({}, ageValidator);

    person.age = 30;
    console.log(person.age); // 30
    person.age = 'old';      // Throws an exception
    person.age = 200;        // Throws an exception
    ```

    **[⬆ Back to Top](#table-of-contents)**

20. ### Promises

    A promise is an object which represent the eventual completion or failure of an asynchronous operation.

    It is in one of these states:

    **pending:** Represents initial state, neither fulfilled nor rejected.
    **fulfilled:** Indicates that the operation is completed successfully.
    **rejected:** Indicates that the operation is failed.

    A promise is said to be settled if it is either fulfilled or rejected, but not pending. The instance methods `promise.then()`, `promise.catch()`, and `promise.finally()` are used to associate further action with a promise that becomes settled. And these methods also return a newly generated promise object, which can optionally be used for chaining.

    ![Screenshot](images/promises.png)

    The promise chaining structure would be as below,

    ```js
    const promise = new Promise(function(resolve, reject) {
      setTimeout(() => resolve(1), 1000);
    });

    promise.then(function(result) {
        console.log(result); // 1

        return result * 2;
      }).then(function(result) {
        console.log(result); // 2

        return result * 3;
      }).then(function(result) {
        console.log(result); // 6

        return result * 4;
      }).catch(function(error){
        console.log(error);
      });
    ```

    **[⬆ Back to Top](#table-of-contents)**

21. ### Reflect

    Reflection is the ability of a code to inspect and manipulate variables, properties, and methods of objects at runtime. JavaScript already provides `Object.keys(), Object.getOwnPropertyDescriptor(), and Array.isArray()` methods as classic refection features. In ES6, it has been officially provided through Reflect object. Reflect is a new global object which is used to call methods, construct objects, get and set properties, manipulate and extend properties.

    Unlike most global objects, Reflect is not a constructor. i.e, You cannot use Reflect with the new operator or invoke the Reflect as a function. It is similar to Math and JSON objects in which all the methods of this object are static.

    Let's see the usage of Reflect API with below examples,

    1. **Creating objects using Reflect.construct();**

     The `construct()` method behaves like the regular new operator, but as a function. It is equivalent to calling new target(...args) with an option to specify a different prototype. The syntax looks like as below,

     ```js
     Reflect.construct(target, args [, newTarget]);
     ```

     The method has below parameters,

     1. target: The target function to call.
     2. argumentsList: An array-like object specifying the arguments with which target should be called.
     3. newTarget: The constructor whose prototype should be used. This is an optional parameter. i.e, If newTarget is not present, its value defaults to target.


    **Example:**
    ```js
    class User {
      constructor(firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
      }
      get fullName() {
        return `${this.firstName} ${this.lastName}`;
      }
    };

    let args = ['John', 'Emma'];

    let john = Reflect.construct(
      User,
      args
    );

    console.log(john instanceof User);
    console.log(john.fullName); // John Doe
    ```

    2. **Calling a function using Reflect.apply():**
    Prior to ES6, you can invoke a function with a specified `this` value and arguments by using the `Function.prototype.apply()` method.

    For example, you can call `max()` static method of Math object,
    ```js
    const max = Function.prototype.apply.call(Math.max, Math, [100, 200, 300]);
    console.log(max);
    ```

    In ES6, Reflect.apply() provides the same features as Function.prototype.apply() but in a less verbose syntax.

    ```js
    const max = Reflect.apply(Math.max, Math, [100, 200, 300]);
    console.log(max);
    ```
    3. **Defining a property using Reflect.defineProperty():**
    The `Reflect.defineProperty()` method is similar to `Object.defineProperty()` but it returns a Boolean value indicating whether or not the property was defined successfully instead of throwing an exception.

    The syntax of this method looks like below,
    ```js
    Reflect.defineProperty(target, propertyName, propertyDescriptor)
    ```

    Let's define the age property on user object,
    ```js
    class User {
      constructor(firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
      }
      get fullName() {
        return `${this.firstName} ${this.lastName}`;
      }
    };

    let john = new User('John', 'Resig');

    if (Reflect.defineProperty(john, 'age', {
        writable: true,
        configurable: true,
        enumerable: false,
        value: 33,
      })) {
      console.log(john.age);
    } else {
      console.log('Cannot define the age property on the user object.');
    }
    ```

    4. **Delete property using Reflect.deleteProperty():**

    The `Reflect.deleteProperty()` method is used to delete properties like the delete operator but as a function. It returns Boolean value indicating whether or not the property was successfully deleted.

    ```js
    const user = {
      name: 'John',
      age: 33
    };

    console.log(Reflect.deleteProperty(user, 'age')); // true
    console.log(user.age); // undefined
    ```

    5. **Get property of an object using Reflect.get():**
    The `Reflect.get` method is used to get a property on an object like the property accessor syntax but as a function.

    ```js
    const user = {
      name: 'John',
      age: 33
    };

    console.log(Reflect.get(user, 'age')); // 33
    ```

    6. **:**

    **[⬆ Back to Top](#table-of-contents)**

22. ### Binary and Octal
    ES5 provided numeric literals in octal (prefix 0), decimal (no prefix), and hexadecimal ( 0x) representation. ES6 added support for binary literals and improvements on octal literals.

    **1. Binary literals:**

    Prior to ES5, JavaScript didn’t provide any literal form of binary numbers. So you need to use a binary string with the help of `parseInt()`

    ```js
    const num = parseInt('110',2);
    console.log(num); // 6
    ```

    Whereas ES6 added support for binary literals using the **0b** prefix followed by a sequence of binary numbers (i.e, 0 and 1).

    ```js
    const num = 0b110;
    console.log(num); // 6
    ```

    **2. Octal literals:**

    In ES5, to represent an octal literal, you use the zero prefix (0) followed by a sequence of octal digits (from 0 to 7).

    ```js
    const num = 055;
    console.log(num); // 45

    let invalidNum = 058;
    console.log(invalidNum); // treated as decimal 58
    ```

    Whereas ES6 represents the octal literal by using the prefix **0o** followed by a sequence of octal digits from 0 through 7.

    ```js
    const num = 055;
    console.log(num); // 45

    const invalidNum = 028;
    console.log(invalidNum); // treated as decimal 28
    ```

    Remember If you use an invalid number in the octal literal, JavaScript will throw a SyntaxError as below,

    ```js
    const invalidNum = 028;
    console.log(invalidNum); // SyntaxError
    ```

    **[⬆ Back to Top](#table-of-contents)**

23. ### Proper Tail Calls

 **Proper tail call(PTC)** is a technique where the program or code will not create additional stack frames for a recursion when the function call is a tail call.

   For example, the below classic or head recursion of factorial function relies on stack for each step. Each step need to be processed upto `n * factorial(n - 1)`

   ```js
    function factorial(n) {
      if (n === 0) {
        return 1
      }
      return n * factorial(n - 1)
    }
    console.log(factorial(5)); //120
   ```

   But if you use Tail recursion functions, they keep passing all the necessary data it needs down the recursion without relying on the stack.

   ```js
    function factorial(n, acc = 1) {
      if (n === 0) {
        return acc
      }
      return factorial(n - 1, n * acc)
    }
    console.log(factorial(5)); //120
   ```

   The above pattern returns the same output as first one. But the accumulator keeps track of total as an argument without using stack memory on recursive calls.

   The browsers which supports PTC do not generate stack overflow instead shows Infinity with below inputs,
   ```js
    console.log(factorial(10));
    console.log(factorial(100));
    console.log(factorial(1000));
    console.log(factorial(10000));
   ```
   
   **[⬆ Back to Top](#table-of-contents)**
   
24. ### Array find methods
    ES6 introduced few array methods and two of them are `Array.find()` and `Array.findIndex()`.

  **Array.find()** 
    This method returns the value of the first element in an array that satisfies the given test. Let's take an example of array with all even elements except one element and use `find` method to find the odd element.

    ```js
    let arr = [2, 4, 5, 6, 8, 10];

    function isOdd(i) {
      return i % 2 !== 0;
    }

    console.log(arr.find(isOdd)); // 5
    ```
  **Array.findIndex()**

  This method returns the index of the first element in the array that satisfies the given test. Let's take an example of array with all even elements except one element and use `findIndex` method to find the index of odd element.

    ```js
    let arr = [2, 4, 5, 6, 8, 10];

    function isOdd(i) {
      return i % 2 !== 0;
    }

    console.log(arr.findIndex(isOdd)); //2
    ```

   **[⬆ Back to Top](#table-of-contents)**

## ES2016 Or ES7

   ES2015/ES6 introduced a huge set of new features. But ECMAScript 2016 Or ES7 introduced only two new features:

   1. Array.prototype.includes()
   2. Exponentiation operator

1. ### Array Includes
   Prior to ES7, you have to use `indexOf` method and compare the result with '-1' to check whether an array element contains particular element or not.
   ```js
    const array = [1,2,3,4,5,6];
    if(array.indexOf(5) > -1 ){
      console.log("Found an element");
    }
   ```
   Whereas in ES7, `array.prototype.includes()` method is introduced as a direct approach to determine whether an array includes a certain value among its entries or not.
    ```js
    const array = [1,2,3,4,5,6];
    if(array.includes(5)){
      console.log("Found an element");
    }
    ```
  In addition to this, `Array.prototype.includes()` handles NaN and Undefined values better than `Array.prototype.indexOf()` methods. i.e, If the array contains NaN and Undefined values then `indexOf()` does not return correct index while searching for NaN and Undefined.
  ```js
  let numbers = [1, 2, 3, 4, NaN, ,];
  console.log(numbers.indexOf(NaN)); // -1
  console.log(numbers.indexOf(undefined)); // -1
  ```
  On the otherhand, `includes` method is able to find these elements
  ```js
  let numbers = [1, 2, 3, 4, NaN, ,];
  console.log(numbers.includes(NaN)); // true
  console.log(numbers.includes(undefined)); // true
  ```
  
  **[⬆ Back to Top](#table-of-contents)**

2. ### Exponentiation Operator

   The older versions of javascript uses `Math.pow` function to find the exponentiation of given numbers. ECMAScript 2016 introduced the exponentiation operator, **(similar to other languages such as Python or F#) to calculate the power computation in a clear representation using infix notation.
   ```js
   //Prior ES7
   const cube = x => Math.pow(x, 3);
   console.log(cube(3)); // 27

   //Using ES7
   const cube1 = x => x ** 3;
   console.log(cube1(3)); // 27
   ```

    **[⬆ Back to Top](#table-of-contents)**

## ES2017 Or ES8

1. ### Async functions

  In ES6, Promises were introduced to solve the famous callback hell problem. When a series of nested asynchronous functions need to be executed in order, it leads to a callback hell
  ```js
  function task() {
    task1((response1) => {
      task2(response1, (response2) => {
        task3(response2, (response3) => {
          // etc...
        };
      });
    });
  }
  ```
  But the Chained Promises creates complex flow for asynchronous code.

  Async functions were introduced as a combination of promises and generators to give us the possibility of writing asynchronous in a synchronous manner. i.e, This function is going to be declared with the `async` keyword which enable asynchronous, promise-based behavior to be written in a cleaner style by avoiding promise chains.  These functions can contain zero or more `await` expressions.

  Let's take a below async function example,

  ```js
  async function logger() {
    let data = await fetch('http://someapi.com/users'); // pause until fetch returns
      console.log(data)
  }
  logger();
  ```
     
  **[⬆ Back to Top](#table-of-contents)**
  
2. ### Object values
   Similar to Object.keys which iterate over JavaScript object’s keys, Object.values will do the same thing on values. i.e, The Object.values() method is introduced to returns an array of a given object's own enumerable property values in the same order as `for...in` loop.

   ```js
    const countries = {
      IN: 'India',
      SG: 'Singapore',
    }
    Object.values(countries) // ['India', 'Singapore']
   ```

   By the way, non-object argument will be coerced to an object

  ```js
  console.log(Object.values(['India', 'Singapore'])); // ['India', 'Singapore']
  console.log(Object.values('India')); // ['I', 'n', 'd', 'i', 'a']
  ```
   
   **[⬆ Back to Top](#table-of-contents)**
   
3. ### Object entries
   The `Object.entries()` method is introduced to returns an array of a given object's own enumerable string-keyed property [key, value] pairsin the same order as `for...in` loop.
   ```js
      const countries = {
        IN: 'India',
        SG: 'Singapore',
      }
      Object.entries(countries) // [["IN", "India"], ["SG", "Singapore"]]
   ```
   By the way, non-object argument will be coerced to an object
   ```js
      const countriesArr = ['India', 'Singapore'];
      console.log(Object.entries(countriesArr)); // [ ['0', 'India'], ['1', 'Singapore']]

      const country = 'India';
      console.log(Object.entries(country)); // [["0", "I"], ["1", "n"], ["2", "d"], ["3", "i"], ["4", "a"]]

      console.log(Object.entries(100)); // [], an empty array for any primitive type because it won't have any own properties
   ```
   
    **[⬆ Back to Top](#table-of-contents)**
    
4. ### Object property descriptors

   Property descriptors describe the attributes of a property. The `Object.getOwnPropertyDescriptors()` method returns all own property descriptors of a given object.

   It provides the below attributes,

   1. **value:** The value associated with the property (data descriptors only).
   2. **writable:** true if and only if the value associated with the property may be changed
   3. **get:** A function which serves as a getter for the property.
   4. **set:** A function which serves as a setter for the property.
   5. **configurable:** true if and only if the type of this property descriptor may be changed or deleted.
   6. **enumerable:** true if and only if this property shows up during enumeration of the property.

   The usage of finding property descriptors for any property seems to be as below,

   ```js
    const profile = {
      age: 42
    };

    const descriptors = Object.getOwnPropertyDescriptors(profile);
    console.log(descriptors); //  {age: {configurable: true, enumerable: true, writable: true }}
   ```
   
    **[⬆ Back to Top](#table-of-contents)**

5. ### String padding
   Some strings and numbers(money, date, timers etc) need to be represented in a particular format. Both `padStart() & padEnd()` methods introduced to pad a string with another string until the resulting string reaches the supplied length.

   1. **padStart():** Using this method, padding is applied to the left or beginning side of the string.

    For example, you may want to show only the last four digits of credit card number for security reasons,

    ```js
    const cardNumber = '01234567891234';
    const lastFourDigits = cardNumber.slice(-4);
    const maskedCardNumber = lastFourDigits.padStart(cardNumber.length, '*');
    console.log(maskedCardNumber); // expected output: "**********1234"
    ```

   2. **padEnd():** Using this method, padding is applied to the right or ending side of the string.

   For example, the profile information padded for label and values as below
   ```js
   const label1 = "Name";
   const label2 = "Phone Number";
   const value1 = "John"
   const value2 = "(222)-333-3456";

   console.log((label1 + ': ').padEnd(20, ' ') + value1); // Name:                     John
   console.log(label2 + ": " + value2); // Phone Number: (222)-333-3456
   ```
   
    **[⬆ Back to Top](#table-of-contents)**

6. ### Shared memory and atomics
   The Atomics is a global object which provides atomic operations to be performed as static methods. They are used with SharedArrayBuffer(fixed-length binary data buffer) objects. The main use cases of these methods are,

   1. **atomic operations:** When memory is shared, multiple threads can read and write the same data in memory. So there would be a chance of loss of data. But atomic operations make sure that predictable values are written and read, that operations are finished before the next operation starts and that operations are not interrupted.

      It provides static methods such as add, or, and, xor, load, store, isLockFree etc as demonstrated below.

        ```js
        const sharedMemory = new SharedArrayBuffer(1024);
        const sharedArray = new Uint8Array(sharedMemory);
        sharedArray[0] = 10;

        Atomics.add(sharedArray, 0, 20);
        console.log(Atomics.load(sharedArray, 0)); // 30

        Atomics.sub(sharedArray, 0, 10);
        console.log(Atomics.load(sharedArray, 0)); // 20

        Atomics.and(sharedArray, 0, 5);
        console.log(Atomics.load(sharedArray, 0));  // 4

        Atomics.or(sharedArray, 0, 1);
        console.log(Atomics.load(sharedArray, 0));  // 5

        Atomics.xor(sharedArray, 0, 1);
        console.log(Atomics.load(sharedArray, 0)); // 4

        Atomics.store(sharedArray, 0, 10); // 10

        Atomics.compareExchange(sharedArray, 0, 5, 10);
        console.log(Atomics.load(sharedArray, 0)); // 10

        Atomics.exchange(sharedArray, 0, 10);
        console.log(Atomics.load(sharedArray, 0)); //10

        Atomics.isLockFree(1); // true
        ```

   2. **waiting to be notified:**
      Both `wait()` and `notify()` methods provides ways for waiting until a certain condition becomes true and are typically used as blocking constructs.

      Let's demonstrate this functionality with reading and writing threads.

      First define a shared memory and array
      ```js
      const sharedMemory = new SharedArrayBuffer(1024);
      const sharedArray = new Int32Array(sharedMemory);
      ```

      A reading thread is sleeping and waiting on location 0 which is expected to be 10. You can observe a different value after the value overwritten by a writing thread.
      ```js
      Atomics.wait(sharedArray, 0, 10);
      console.log(sharedArray[0]); // 100
      ```

      Now a writing thread stores a new value(e.g, 100) and notifies the waiting thread,
      ```js
      Atomics.store(sharedArray, 0, 100);
      Atomics.notify(sharedArray, 0, 1);
      ```

7. ### Trailing commas
   Trailing commas are  allowed in parameter definitions and function calls
   ```js
    function func(a,b,) { // declaration
      console.log(a, b);
    }
   func(1,2,); // invocation
   ```
   But if the function parameter definition or function call only contains a comma, a syntax error will be thrown
   ```js
    function func1(,) {  // SyntaxError: missing formal parameter
      console.log('no args');
    };
   func1(,); // SyntaxError: expected expression, got ','
   ```

   **Note:** Trailing commas are not allowed in Rest Parameters and JSON.

    **[⬆ Back to Top](#table-of-contents)**

## ES2018 Or ES9

1. ### Async iterators

   ECMAScript 6 provides built-in support for synchronously iterating over data using iterators. Both strings and collections objects such as Set, Map, and Array come with a Symbol.iterator property which makes them iterable.

   ```js
    const arr = ['a', 'b', 'c', 'd'];
    const syncIterator = arr[Symbol.iterator]();

    console.log(syncIterator.next()); // {value: a, done: false}
    console.log(syncIterator.next()); // {value: b, done: false}
    console.log(syncIterator.next()); // {value: c, done: false}
    console.log(syncIterator.next()); // {value: d, done: false}
    console.log(syncIterator.next()); // {value: undefined, done: true}
   ```

   But these iterators are only suitable for representing synchronous data sources.

   In order to access asynchronous data sources, ES2018 introduced the AsyncIterator interface, an asynchronous iteration statement (for-await-of), and async generator functions.

    **[⬆ Back to Top](#table-of-contents)**

2. ### Object rest and spread operators

   ES2015 or ES6 introduced both rest parameters and spread operators to convert arguments to array and vice versa using three-dot(...) notation.
   1. Rest parameters can be used to convert function arguments to an array

       ```js
        function myfunc(p1, p2, ...p3) {
          console.log(p1, p2, p3); // 1, 2, [3, 4, 5, 6]
        }
       myfunc(1, 2, 3, 4, 5, 6);
       ```

   2. The spread operator works in the opposite way by converting an array into separate arguments in order to pass to a function

       ```js
        const myArray = [10, 5, 25, -100, 200, -200];
        console.log( Math.max(...myArray) ); // 200
       ```

   ES2018 enables this rest/spread behavior for objects as well.

   1. You can pass object to a function

       ```js
        function myfunc1({ a, ...x }) {
          console.log(a, x); // 1, { b: 2, c: 3, d:4 }
        }
        myfunc1({
          a: 1,
          b: 2,
          c: 3,
          d: 4
        });
       ```

   2. The spread operator can be used within other objects

        ```js
        const myObject = { a: 1, b: 2, c: 3, d:4 };
        const myNewObject = { ...myObject, e: 5 }; // { a: 1, b: 2, c: 3, d: 4, e: 5 }
        ```
        
    **[⬆ Back to Top](#table-of-contents)**

3. ### Promise finally

   Sometimes you may need to avoid duplicate code in the then() and catch() methods.

   ```js
   myPromise
      .then(result => {
        // process the result and then clean up the resources
      })
      .catch(error => {
        // handle the error and then clean up the resources
      });
   ```

   The `finally()` method is useful if you want to do some processing or resource cleanup once the promise is settled(i.e either fulfilled or rejected).

   Let's take a below example to hide the loading spinner after the data is fetched and processed.

   ```js
     let isLoading = true;
     fetch('http://somesite.com/users')
        .then(data => data.json())
        .catch(err => console.error(err))
        .finally(() => {
          isLoading = false;
          console.log('Finished loading!!');
        })
   ```

    **[⬆ Back to Top](#table-of-contents)**

## ES2019 Or ES10

1. ### Array flat and flatMap

   Prior to ES2019, you need to use `reduce() or concat()` methods to get a flat array.

   ```js
   function flatten(arr) {
     const flat = [].concat(...arr);
     return flat.some(Array.isArray) ? flatten(flat) : flat;
   }
   flatten([ [1, 2, 3], ['one', 'two', 'three', [22, 33] ], ['a', 'b', 'c'] ]);
   ```

   In ES2019, the `flat()` method is introduced to 'flattens' the nested arrays into the top-level array. The functionality of this method is similar to Lodash's `_.flattenDepth()` function. This method accepts an optional argument that specifies the number of levels a nested array should be flattened and the default nested level is 1.
   **Note:** If there are any empty slots in the array, they will be discarded.

   ```js
    const numberArray = [[1, 2], [[3], 4], [5, 6]];
    const charArray = ['a', , 'b', , , ['c', 'd'], 'e'];
    const flattenedArrOneLevel = numberArray.flat(1);
    const flattenedArrTwoLevel = numberArray.flat(2);
    const flattenedCharArrOneLevel = charArray.flat(1);

    console.log(flattenedArrOneLevel); // [1, 2, [3], 4, 5, 6]
    console.log(flattenedArrTwoLevel); // [1, 2, 3, 4, 5, 6]
    console.log(flattenedCharArrOneLevel); // ['a', 'b', 'c', 'd', 'e']
   ```

   Whereas, **flatMap()** method combines `map()` and `flat()` into one method.  It first creates a new array with the return value of a given function and then concatenates all sub-array elements of the array.
   ```js
   const numberArray1 = [[1], [2], [3], [4], [5]];

   console.log(numberArray1.flatMap(value => [value * 10])); // [10, 20, 30, 40, 50]
   ```
   
    **[⬆ Back to Top](#table-of-contents)**

2. ### Object fromEntries

   In JavaScript, it is very commonn to transforming data from one format. ES2017 introduced `Object.entries()` method to objects into arrays.

   **Object to Array:**

   ```js
        const obj = {'a': '1', 'b': '2', 'c': '3' };
        const arr = Object.entries(obj);
        console.log(arr); // [ ['a', '1'], ['b', '2'], ['c', '3'] ]
   ```

   But if you want to get the object back from an array then you need iterate and convert it as below,

    ```js
    const arr = [ ['a', '1'], ['b', '2'], ['c', '3'] ];
    let obj = {}
    for (let [key, val] of arr) {
        obj[key] = val;
    }
    console.log(obj);
    ```
  We need a straightforward way to avoid this iteration. In ES2019, `Object.fromEntries()` method is introduced which performs the reverse of `Object.entries()` behavior. The above loop can be avoided easily as below,

  **Iterable( e.g Array or Map) to Object**
   ```js
    const arr = [ ['a', '1'], ['b', '2'], ['c', '3'] ];
    const obj = Object.fromEntries(arr);
    console.log(obj); // { a: "1", b: "2", c: "3" }
   ```
  One of the common case of this method usage is working with query params of an URL,
   ```js
    const paramsString = 'param1=foo&param2=baz';
    const searchParams = new URLSearchParams(paramsString);

    Object.fromEntries(searchParams);    // => {param1: "foo", param2: "baz"}
   ```
   
   **[⬆ Back to Top](#table-of-contents)**

3. ### String trimStart and trimEnd
   In order to make consistency with padStart/padEnd, ES2019 provided the standard functions named as `trimStart` and `trimEnd` to trim white spaces on the beginning and ending of a string. However for web compatilibity(avoid any breakage) `trimLeft` and `trimRight` will be an alias for `trimStart` and `trimEnd` respectively.

   Let's see the usage with an example,
   ```js
    //Prior ES2019
    let messageOne = "   Hello World!!    ";
    console.log(messageOne.trimLeft()); //Hello World!!
    console.log(messageOne.trimRight()); //   Hello World!!

    //With ES2019
    let messageTwo = "   Hello World!!    ";
    console.log(messageTwo.trimStart()); //Hello World!!
    console.log(messageTwo.trimEnd()); //   Hello World!!
   ```
   
   **[⬆ Back to Top](#table-of-contents)**

4. ### Symbol description

 While creating symbols, you also can add a description to it for debugging purposes. But there was no method to access the description directly before ES2019. Considering this, ES2019 introduced a read-only description property to retrieve a string containing the description of the Symbol.

 This gives the possibility to access symbol description for different variations of Symbol objects

 ```js
 console.log(Symbol('one').description); // one

 console.log(Symbol.for('one').description); // "one"

 console.log(Symbol('').description); // ''

 console.log(Symbol().description); // unefined

 console.log(Symbol.iterator.description); // "Symbol.iterator"
 ```
 
 **[⬆ Back to Top](#table-of-contents)**

5. ### Optional catch binding
   Prior to ES9, if you don't need `error` variable and omit the same variable then catch() clause won't be invoked. Also, the linters complain about unused variables. Inorder to avoid this problem, the optional catch binding feature is introduced to make the binding parameter optional in the catch clause. If you want to completely ignore the error or you already know the error but you just want to react to that the this feature is going to be useful.

   Let's see the below syntax difference between the versions,
   ```js
    // With binding parameter(<ES9)
    try {
      ···
    } catch (error) {
      ···
    }
    // Without binding parameter(ES9)
    try {
      ···
    } catch {
      ···
    }
   ```
   For example, the feature detection on a browser is one of the most common case
   ```js
    let isTheFeatureImplemented = false;
    try {
      if(isFeatureSupported()) {
        isTheFeatureImplemented = true;
      }
    } catch (unused) {}
   ```
   
   **[⬆ Back to Top](#table-of-contents)**
   
6. ### JSON Improvements

    JSON is used as a lightweight format for data interchange(to read and parse). The usage of JSON has been improved as part of ECMAScript specification. Basically there are 2 important changes related to JSON.

    1. **JSON Superset**

    Prior to ES2019, ECMAScript claims JSON as a subset in JSON.parse but that is not true. Because ECMAScript string literals couldn’t contain the characters `U+2028` (LINE SEPARATOR) and `U+2029` (PARAGRAPH SEPARATOR) unlike JSON Strings. If you still use those characters then there will be a syntax error. As a workaround, you had to use an escape sequence to put them into a string.
    ```js
    eval('"\u2028"'); // SyntaxError
    ```

    Whereas JSON strings can contain both U+2028 and U+2029 without producing errors.​

    ```js
    console.log(JSON.parse('"\u2028"')); // ''
    ```

    This restriction has been removed in ES2019. This simplifies the specification without the need of separate rules for ECMAScript string literals and JSON string literals.

    2. **Well Formed JSON.Stringify():**
    Prior to ES2019, JSON.stringify method is used to return unformed Unicode strings(ill-formed Unicode strings) if there are any lone surrogates in the input.

    ```js
    console.log(JSON.stringify("\uD800")); // '"�"'
    ```

    Whereas in ES2019, JSON.stringify outputs escape sequences for lone surrogates, making its output valid Unicode and representable in UTF-8.

    ```js
    console.log(JSON.stringify("\uD800")); // '"\ud800"'
    ```
    
   **[⬆ Back to Top](#table-of-contents)**

7. ### Array Stable Sort
    The sort method for arrays is stable in ES2020. i.e, If you have an array of objects and sort them on a given key, the elements in the list will retain their position relative to the other objects with the same key.​
    Now the array is using the stable `TimSort` algorithm for arrays over 10 elements instead of the unstable `QuickSort`.

    Let's see an example of users retain their original position with same age group.
    ```js
    const users = [
        { name: "Albert",  age: 30 },
        { name: "Bravo",   age: 30 },
        { name: "Colin",   age: 30 },
        { name: "Rock",    age: 50 },
        { name: "Sunny",   age: 50 },
        { name: "Talor",    age: 50 },
        { name: "John",   age: 25 },
        { name: "Kindo",  age: 25 },
        { name: "Lary",   age: 25 },
        { name: "Minjie",   age: 25 },
        { name: "Nova",    age: 25 }
    ]
    users.sort((a, b) => a.age - b.age);
    ```
   **[⬆ Back to Top](#table-of-contents)**

8. ### Function.toString()
    Functions have an instance method called `toString()` which return a string to represent the function code. Previous versions of ECMAScript removes white spaces,new lines and comments from the function code but it has been retained with original source code in ES2020.

    ```js
    function sayHello(message) {
        let msg = message;
        //Print message
        console.log(`Hello, ${msg}`);
    }

    console.log(sayHello.toString());
    // function sayHello(message) {
    //       let msg = message;
    //       //Print message
    //       console.log(`Hello, ${msg}`);
    //   }
    ```
    
   **[⬆ Back to Top](#table-of-contents)**

9. ### Private Class Variables
     In ES6, the classes are introduced to create reusable modules and variables are declared in clousure to make them private. Where as in ES2020, private class variables are introduced to allow the variables used in the class only. By just adding a simple hash symbol in front of our variable or function, you can reserve them entirely for internal to the class.
     ```js
      class User {
        #message = "Welcome to ES2020"

        login() { console.log(this.#message) }
      }

      const user = new User()

      user.login() // Welcome to ES2020
      console.log(user.#message) // Uncaught SyntaxError: Private field '#
     ```

     **Note:** As shown in the above code, If you still try to access the variable directly from the object then you will receive syntax error.

    **[⬆ Back to Top](#table-of-contents)**

## ES2020 Or ES11

ES2020 is the current newer version of ECMAScript corresponding to the year 2020. This is the eleventh edition of the ECMAScript Language Specification. Even though this release doesn't bring as many features as ES6, it included some really useful features.

Most of these features already supported by some browsers and try out with babel parser support for unsupported features. This edition is set for final approval by the ECMA general assembly in June, 2020. The [ECMAScript 2020 (ES2020) language specification](https://tc39.es/ecma262/2020/) is ready now.

1. ### BigInt
    In earlier JavaScript version, there is a limitation of using the Number type. i.e, You cannot safely represent integer values(`Number` primitive) larger than pow(2, 53). In ES2020,

    `BigInt` is introduced as the 7th primitive type to represent whole numbers(integers with arbitrary precision) larger than pow(2, 53) - 1(or 9007199254740991 or Number.MAX_SAFE_INTEGER). This is been created by appending `n` to the end of an integer literal or by calling the function BigInt().

    ```js
    // 1. Current number system
    const max = Number.MAX_SAFE_INTEGER;
    console.log(max + 1) // 9007199254740992
    console.log(max + 2) // 9007199254740992

    // 2. BigInt representation
    const bigInt = 9007199254740991n;
    const bigIntConstructorRep = BigInt(9007199254740991); // 9007199254740991n
    const bigIntStringRep = BigInt("9007199254740991"); // 9007199254740991n

    // 3. Typeof usage

    console.log(typeof 1)// number
    console.log(typeof 1n)// bigint
    console.log(typeof BigInt('1'))// bigint

    // 4. Operators

    const previousMaxNum = BigInt(Number.MAX_SAFE_INTEGER);
    console.log(previousMaxNum + 2n); //9007199254740993n (this was not possible before)
    console.log(previousMaxNum -2n); //9007199254740990n
    console.log(previousMaxNum * 2n); //18014398509481982n
    console.log(previousMaxNum % 2n); //1n
    console.log(previousMaxNum / 2n); // 4503599627370495n

    // 5. comparison
    console.log(1n === 1); // false
    console.log(1n === BigInt(1)); // true
    console.log(1n == 1); // true
    ```

   **[⬆ Back to Top](#table-of-contents)**

2. ### Dynamic Import
    Static imports supports some of the important use cases such as static analysis, bundling tools, and tree shaking, it is also it's desirable to be able to dynamically load parts of a JavaScript application at runtime.

    The new feature `dynamic import` is introduced to load a module conditionally or on demand. Since it returns a promise for the module namespace object of the requested module, the module can be resolved or import can now be assigned to a variable using async/await as below
    ```js
    <script>
    const moduleSpecifier = './message.js';
    import(moduleSpecifier)
      .then((module) => {
        module.default(); // Hello, default export
        module.sayGoodBye(); //Bye, named export
      })
      .catch(err => console.log('loading error'));
    </script>
    ```
    ```js
    <script>
    (async function() {
      const moduleSpecifier = './message.js';
      const messageModule = await import(moduleSpecifier);
      messageModule.default(); // Hello, default export
      messageModule.sayGoodBye(); //Bye, named export
    })();
    </script>
    ```
    and the imported module appears with both default and named exports
    ```js
    export default () => {
      return "Hello, default export";
    }
    export const sayGoodBye = () => {
      return "Bye, named export"
    }
    ```

    **Note:** Dynamic import does not require scripts of `type="module"`

   **[⬆ Back to Top](#table-of-contents)**

3. ### Nullish Coalescing Operator
    The nullish coalescing operator (??) is a logical operator that returns its right-hand side operand when its left-hand side operand is `null` or `undefined`, and otherwise returns its left-hand side operand. This operator replaces `||` operator to provide default values if you treat empty value or '', 0 and NaN as valid values. This is because the logical OR(||) operator treats(empty value or '', 0 and NaN) as falsy values and returns the right operand value which is wrong in this case. Hence, this operator truely checks for `nullish` values instead `falsy` values.
    ```js
    let vehicle = {
      car: {
        name: "",
        speed: 0
      }
    };

    console.log(vehicle.car.name || "Unknown"); // Unknown
    console.log(vehicle.car.speed || 90); // 90

    console.log(vehicle.car.name ?? "Unknown"); // ""(empty is valid case for name)
    console.log(vehicle.car.speed ?? 90); // 0(zero is valid case for speed)
    ```
    In a short note, nullish operator returns a non-nullish value and || operator returns truthy values.
    
   **[⬆ Back to Top](#table-of-contents)**

4. ### String matchAll

    There is `String#match` method to get all the matches of a string against a regular expression by iterating for each match. However this method gives you the substrings that match.

    The `String#matchAll()` is a new method added to String prototype, which returns an iterator of all results matching a string against a regular expression.
    ```js
    const regex = /t(e)(st(\d?))/g;
    const string = 'test1test2';
    const matchesIterator = string.matchAll(regex);
    Array.from(matchesIterator, result => console.log(result));
    ```
    When you this code in browser console, the matches iterator produces an array for each match including the capturing groups with a few extras.
    ```cmd
    ["test1", "e", "st1", "1", index: 0, input: "test1test2", groups: undefined]
    ["test2", "e", "st2", "2", index: 5, input: "test1test2", groups: undefined]
    ```
    
   **[⬆ Back to Top](#table-of-contents)**

5. ### Optional chaining

    In JavaScript, Long chains of property accesses is quite error-prone if any of them evaluates to `null` or `undefined` value. Also, it is not a good idea to check property existence on each item which in turn leads to a deeply-nested structured `if` statements.

    Optional chaining is a new feature that can make your JavaScript code look cleaner and robust by appending(?.) operator to stop the evaluation and return undefined if the item is undefined or null.
    By the way, this operator can be used together with nullish coalescing operator to provide default values
    ```js
    let vehicle = {
    };

    let vehicle1 = {
      car: {
        name: 'ABC',
        speed: 90
      }
    };

    console.log(vehicle.car?.name); // TypeError: Cannot read property 'name' of undefined

    console.log(vehicle.car?.name); // Undefined
    console.log(vehicle.car?.speed); // Undefined

    console.log(vehicle1.car?.name); // ABC
    console.log(vehicle1.car?.speed); // 90

    console.log(vehicle.car?.name ?? "Unknown"); // Unknown
    console.log(vehicle.car?.speed ?? 90); // 90
    ```
    
   **[⬆ Back to Top](#table-of-contents)**

6. ### Promise.allSettled

    It is really helpful to log(especially to debug errors) about each promise when you are handling multiple promises. The  `Promise.allSettled()` method returns a new promise that resolves after all of the given promises have either fulfilled or rejected, with an array of objects describing the outcome of each promise.
    ```js
    const promise1 = new Promise((resolve, reject) => setTimeout(() => resolve(100), 1000));

    const promise2 = new Promise((resolve, reject) => setTimeout(reject, 1000));

    Promise.allSettled([promise1, promise2]).then(data => console.log(data)); // [
                                                                              // Object { status: "fulfilled", value: 100},
                                                                              // Object { status: "rejected", reason: undefined}
                                                                              // ]
    ```
    As per the output, each outcome object returns `status` field which denotes either "fulfilled"(value present) or "rejected"(reason present)

   **[⬆ Back to Top](#table-of-contents)**
   
7. ### globalThis
    Prior to ES2020, you need to write different syntax in different JavaScript environments(cross-platforms) just to access the global object. It is really a hard time for developers because you need to use `window, self, or frames` on the browser side, `global` on the nodejs, `self` on the web workers side.

    On the other hand, `this` keyword can be used inside functions for non-strict mode but it gives undefined in strict mode. If you think about `Function('return this')()` as a solution for above environments, it will fail for CSP enabled environments(where eval() is disabled).

    In the older versions, you can use es6-shim as below,
    ```js
    var getGlobal = function () {
      if (typeof self !== 'undefined') { return self; }
      if (typeof window !== 'undefined') { return window; }
      if (typeof global !== 'undefined') { return global; }
      throw new Error('unable to locate global object');
    };

    var globals = getGlobal();

    if (typeof globals.setTimeout !== 'function') {
      console.log('no setTimeout in this environment or runtime');
    }
    ```
    In ES2020, `globalThis` property is introduced to provide a standard way of accessing the global this value across environments.
    ```js
    if (typeof globalThis.setTimeout !== 'function') {
      console.log('no setTimeout in this environment or runtime');
    }
    ```

8. ### import.meta

    The `import.meta` object was created by the ECMAScript implementation with a null prototype to get context-specific metadata about a JavaScript module.
    Let's say you are trying to load `my-module` from a script,
    ```js
    <script type="module" src="my-module.js"></script>
    ```
    Now you can access meta information(base URL of the module) about the module using the import.meta object
    ```js
    console.log(import.meta); // { url: "file:///home/user/my-module.js" }
    ```
    The above URL can be either URL from which the script was obtained (for external scripts), or the document base URL of the containing document (for inline scripts).

    **Note:** Remember `import` is not really an object but `import.meta` is provided as an object which is extensible, and its properties are writable, configurable, and enumerable.

9. ### for..in order

    Prior to ES2020, the specifications did not specify in which order for (a in b)  should run. Even though most of the javascript engines/browsers loop over the properties of an object in the order in which they were defined, it is not the case with all scenarios. This has been officially standardized in ES2020.
    ```js
    var object = {
      'a': 2,
      'b': 3,
      'c': 4
    }


    for(let key in object) {
      console.log(key); // a b c
    }
    ```

    **[⬆ Back to Top](#table-of-contents)**

## ES2021 Or ES12
  ECMAScript 2021 or ES12 has been released in mid of 2021 with few important features which can be used JavaScript.

1. ### replaceAll
   The new `replaceAll()` method from `String` prototype is used to replace all the occurrences of a string from another string value. Earlier it was not possible to replace all the instances of a substring without the use of regex.

   **Before ES2021**
   ```javascript
    console.log('10101010'.replace(new RegExp('0', 'g'), '1')); // 11111111
    console.log('01010101'.replace(/0/g, '1')); // 11111111
   ```

   **After ES2021**
   ```javascript
    console.log('10101010'.replaceAll('0', '1')); // 11111111
    console.log('01010101'.replaceAll('0', '1')); // 11111111
   ```

2. ### promise.any
   The new `promise.any` method takes multiple promises and resolves to the value of the first promise which is successfully fulfilled.

   ```javascript
   let promise1 = new Promise((resolve) => setTimeout(resolve, 100, 'Resolves after 100ms'));
   let promise2 = new Promise((resolve) => setTimeout(resolve, 200, 'Resolves after 200ms'));
   let promise3 = new Promise((resolve, reject) => setTimeout(reject, 0) );

   let promises = [promise1, promise2, promise3];

    Promise.any(promises)
        .then( value => console.log(value)); // Resolves after 100ms
   ```

   In case none of the promises resolved then it throws `AggregateError` exception.

   ```javascript
    (async () => {
      try {
        const output = await Promise.any([
          Promise.reject('Error 1'),
          Promise.reject('Error 2'),
          Promise.reject('Error 3'),
        ]);
        console.log(`Output: ${output}`);
      } catch (err) {
        console.log(`Error: ${err.errors}`);
      }
    })(); 
    // Error: Error1,Error2,Error3
   ```
3. ### WeakRef
    WeakRef provides two new pieces of functionality
      1. creating weak references to objects with the WeakRef class
      2. running user-defined finalizers after objects are garbage-collected, with the FinalizationRegistry class
    
    **WeakRef:**
    weak reference is a reference to an object that doesn’t prevent garbage collection if it is the only reference to the object in the memory.It’s useful when we don’t want to keep the object in memory forever(e.g, WebSocket). The main use of weak references is to implement caches or mappings to large objects for which you don't need to keep it in memory for rarely used objects.

    Prior to ES12, WeakMaps and WeakSets are the only way to kind-of-weakly reference an object in JavaScript. Whereas WeakRef in ES12 provides actual weak references, enabling a window into the lifetime of an object.

    Let's see an example of a weak reference object using `WeakRef` constructor and read the reference using `deref()` method

    ```javascript
    const myObject = new WeakRef({
      name: ‘Sudheer’,
      age: 34
    });
    console.log(myObject.deref()); //output: {name: “Sudheer”, age: 35}
    console.log(myObject.deref().name); //output: Sudheer
    ```
    **Finalizers:**
    A `FinalizationRegistry` object lets you request a callback when an object is garbage-collected. It works as a cleanup callback.

    ```javascript
    // Create new FinalizationRegistry:
    const reg = new FinalizationRegistry((val) => {
      console.log(val);
    });

    (() => {
    // Create new object:
      const obj = {}

    // Register finalizer for the "obj" as first argument and value for callback function as second argument:
      reg.register(obj, 'obj has been garbage-collected.')
    })();
    ```

    **Note:** The finalization callback does not run immediately after garbage-collecting the event listener, so don't use it for important logic or metrics.
4. ### Numeric Separators
    Numeric separators are helpful to read large numbers(or numeric literals) in JavaScript by providing separation between digits using underscores(_). In otherwords, numeric literals are more readable by creating a visual separation between groups of digits. 

    For example, one billion and one trillion becomes more readable with _ numeric separator,

    ```javascript
    const billion = 1000_000_000;
    console.log(billion); // 1000000000

    const trillion = 1000_000_000_000n; // BigInt number
    console.log(trillion); // 1000000000000
    ```

    It can be used for binary and hex literals as well.

    ```javascript
    const binaryLiteral = 0b1010_1010;
    console.log(binaryLiteral);
    const hexLiteral = 0xFF_FF_FF_FF;
    console.log(hexLiteral);
    ```

    **Note:** The separator can be placed anywhere within the number for readability purpose.

5. ### Logical Operators
   Logical assignment operators combines the logical operations(&&, || or ??) with assignment. They are quite useful for assigning default values to variables.
   
   **&&=:** 

   The `&&=` operator performs the assignment only when the left operand is truthy.
   ```javascript
    let x = 10;
    let y = 20;
    x &&= y;
    console.log(x); // 20
   ```

   The above logical assignment operation can be expanded to:

   ```javascript
    x = x && (x = y); 
    (OR)
    if (x) {
      x = y;
    }
   ```

   **||=:**
   
   The ||= operator performs the assignment only when the left operand is falsy.
   ```javascript
    let x = 0;
    let y = 20;
      x ||= y;
    console.log(x); // 20
   ```

   The above logical assignment operation can be expanded to:

   ```javascript
    x = x || (x = y); 
    (OR)
    if (!x) {
      x = y;
    }
   ```

   **??=:**
   
   The ??= operator performs the assignment only when the left operand is null or undefined.
   ```javascript
    let x;
    let y = 1;
    x ??= y;
    console.log(x); // 1
   ```

    The above logical assignment operation can be expanded to:

    ```javascript
      x ?? (x = y);
      (OR)
      if (!x) {
        x = y;
      }
    ```

    **[⬆ Back to Top](#table-of-contents)**