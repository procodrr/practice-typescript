# Section 3: Arrays and Tuples in TypeScript

## Table of Contents

- [Section 3.1 and Section 3.2](#section-31-and-section-32)
- [Section 3.3](#section-33)
- [Section 3.4](#section-34)

## Section 3.1 and Section 3.2

### 1. Which syntax is used to explicitly define an array of numbers in TypeScript?

- A. `let marks: number = [10, 20];`
- B. `let marks: number[] = [10, 20];`
- C. `let marks: array<number> = [10, 20];`
- D. `let marks = number[] [10, 20];`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. `let marks: number[] = [10, 20];`**

`number[]` means the array can only store numbers.

```ts
let studentMarks: number[] = [80, 95, 97];
```

</details>

---

### 2. What is the type of the following array?

Given:

```ts
let freshFruits: string[] = ["mango", "banana"];
```

- A. number[]
- B. any[]
- C. string[]
- D. unknown[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. string[]**

The array can only contain string values.

</details>

---

### 3. Which of the following is a valid `symbol[]` array?

- A. `[10, 20, 30]`
- B. `["mango", "banana"]`
- C. `[Symbol(10), Symbol("mango")]`
- D. `[true, false]`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. `[Symbol(10), Symbol("mango")]`**

A `symbol[]` array stores only Symbol values.

```ts
let alwaysUnique: symbol[] = [Symbol(10), Symbol("mango")];
```

</details>

---

### 4. Which array type behaves most like JavaScript?

- A. unknown[]
- B. never[]
- C. any[]
- D. number[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. any[]**

`any[]` disables type checking and behaves similarly to JavaScript.

```ts
let randomData1: any[] = [10, "prashant"];

randomData1[0].toUpperCase(); // allowed
randomData1[2] = 65; // allowed
```

</details>

---

### 5. Which statement about `unknown[]` is correct?

Given:

```ts
let randomData2: unknown[] = [10, "prashant", undefined, null, true, [10, 20]];
```

- A. It only stores strings.
- B. It only stores numbers.
- C. It can store values of any type.
- D. It can store only objects.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. It can store values of any type.**

`unknown[]` is a top-type container and can hold values of different types.

</details>

---

### 6. What type is inferred for the following array?

Given:

```ts
let userScoreHistory = [10, 20, 30];
```

- A. any[]
- B. string[]
- C. number[]
- D. unknown[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. number[]**

TypeScript infers the type from the initialization values.

</details>

---

### 7. Which operation is allowed on the following array?

Given:

```ts
let userScoreHistory = [10, 20, 30];
```

- A. `userScoreHistory.push("30")`
- B. `userScoreHistory.push(40)`
- C. `userScoreHistory.push(true)`
- D. `userScoreHistory.push(null)`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. `userScoreHistory.push(40)`**

The array is inferred as `number[]`, so only numbers can be pushed.

</details>

---

### 8. Which value was specifically shown as valid for a `number[]` array?

Given:

```ts
let userScoreHistory = [10, 20, 30];

userScoreHistory.push(NaN);
userScoreHistory.push(Infinity);
```

- A. `"100"`
- B. `null`
- C. `NaN`
- D. `"NaN"`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. NaN**

Both `NaN` and `Infinity` are considered numbers in JavaScript and TypeScript.

</details>

---

### 9. What type is inferred here?

Given:

```ts
let userDetails = ["Prashant", 21];
```

- A. string[]
- B. number[]
- C. any[]
- D. (string | number)[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **D. (string | number)[]**

TypeScript combines all initialization types into a union.

</details>

---

### 10. Why is the following operation not allowed?

Given:

```ts
let userDetails = ["Prashant", 21];

userDetails[0].toUpperCase();
```

- A. Arrays do not support methods.
- B. TypeScript sees a union type.
- C. Strings have no `toUpperCase()`.
- D. Arrays cannot contain strings.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. TypeScript sees a union type.**

The array contains both strings and numbers, so TypeScript cannot guarantee that every element is a string.

```ts
let userDetails: (string | number)[];
```

Therefore only methods common to both types are allowed.

</details>

---

### 11. What type is inferred here?

Given:

```ts
let moreTypes1 = [undefined, null];
```

- A. any[]
- B. (null | undefined)[]
- C. string[]
- D. object[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. (null | undefined)[]**

TypeScript combines both initialization types into a union.

</details>

---

### 12. What type is inferred here?

Given:

```ts
let moreTypes2 = [undefined, null, 10];
```

- A. (null | undefined | number)[]
- B. number[]
- C. any[]
- D. unknown[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **A. (null | undefined | number)[]**

TypeScript expands the union during initialization.

</details>

---

### 13. Which operator is used to combine multiple types?

Given:

```ts
let userResponse: (string | number)[] = [];
```

- A. `&`
- B. `=>`
- C. `|`
- D. `?`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. `|`**

The union operator allows multiple possible types.

```ts
(string | number)[]
```

</details>

---

### 14. Which declaration is valid?

- A. `let userResponse: (string | number)[] = [];`
- B. `let userResponse: string[] = [10];`
- C. `let userResponse: number[] = ["Prashant"];`
- D. `let userResponse: string[] = [10, "Rahul"];`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **A.**

An empty array is valid because its type is explicitly defined.

```ts
let userResponse: (string | number)[] = [];
```

</details>

---

### 15. Which value CANNOT be pushed into the following array?

Given:

```ts
let userResponse1: (string | number)[] = ["Prashant", 10, 30];
```

- A. `"Ankit"`
- B. `20`
- C. `null`
- D. `100`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. null**

The array only accepts strings and numbers.

```ts
userResponse1.push("Ankit"); // allowed
userResponse1.push(20); // allowed
```

</details>

---

### 16. Why is this method allowed?

Given:

```ts
let userResponse1: (string | number)[] = ["Prashant", 10];

userResponse1[0]?.toLocaleString();
```

- A. It exists on both string and number.
- B. It exists only on string.
- C. It exists only on number.
- D. It is an array method.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **A.**

TypeScript allows methods common to all members of the union.

`toLocaleString()` exists on both `string` and `number`.

</details>

---

### 17. What is the inferred type of the following expression?

Given:

```ts
let arr2 = 10 + "Prashant" + [10, 20, 30] + null + undefined;
```

- A. number
- B. boolean
- C. string
- D. any

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. string**

Once a string participates in `+`, concatenation occurs and the result becomes a string.

</details>

---

### 18. Which array method transforms every element and returns a new array?

Given:

```ts
let scores: number[] = [10, 15, 20, 25];
```

- A. reduce()
- B. filter()
- C. map()
- D. push()

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. map()**

```ts
scores.map((n) => n + 10);
```

Produces a new transformed array.

</details>

---

### 19. What is the inferred type of `increaseScoreBy10`?

Given:

```ts
let scores: number[] = [10, 15, 20, 25];

let increaseScoreBy10 = scores.map((n) => n + 10);
```

- A. string[]
- B. number[]
- C. boolean[]
- D. unknown[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. number[]**

The callback returns a number for every element.

```ts
[20, 25, 30, 35];
```

Therefore the result is `number[]`.

</details>

---

### 20. Which method is used to select elements that satisfy a condition?

Given:

```ts
let scores: number[] = [10, 15, 20, 25];
```

- A. reduce()
- B. filter()
- C. push()
- D. concat()

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. filter()**

```ts
scores.filter((n) => n % 2 !== 0);
```

</details>

---

### 21. What is the inferred type of `oddScores`?

Given:

```ts
let scores: number[] = [10, 15, 20, 25];

let oddScores = scores.filter((n) => n % 2 !== 0);
```

- A. string[]
- B. boolean[]
- C. number[]
- D. any[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. number[]**

The original array is `number[]`, therefore filtered values remain numbers.

</details>

---

### 22. Which method combines array elements into a single value?

Given:

```ts
let scores: number[] = [10, 15, 20, 25];
```

- A. filter()
- B. reduce()
- C. map()
- D. push()

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. reduce()**

```ts
scores.reduce((curr, acc) => curr + acc, 0);
```

</details>

---

### 23. What is the inferred type of `arraySum`?

Given:

```ts
let scores: number[] = [10, 15, 20, 25];

let arraySum = scores.reduce((curr, acc) => curr + acc, 0);
```

- A. string
- B. number
- C. number[]
- D. any

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. number**

The callback returns a number and the initial value is `0`.

</details>

---

### 24. What is the inferred type of `userNames`?

Given:

```ts
let scores2: (string | number)[] = [10, "Prashant", "Ankit", 20, "Atul", 30];

let userNames = scores2.filter((el) => typeof el == "string");
```

- A. any[]
- B. unknown[]
- C. string[]
- D. (string | number)[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. string[]**

The filter condition keeps only string values.

```ts
["Prashant", "Ankit", "Atul"];
```

TypeScript narrows the type to:

```ts
string[]
```

</details>

---

### 25. Why does `userNames.forEach(...)` provide string method suggestions?

Given:

```ts
let scores2: (string | number)[] = [10, "Prashant", "Ankit", 20];

let userNames = scores2.filter((el) => typeof el == "string");

userNames.forEach((name) => name.toUpperCase());
```

- A. Because the array is any[]
- B. Because TypeScript inferred string[]
- C. Because forEach converts everything to string
- D. Because filter returns any[]

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Because TypeScript inferred string[]**

After filtering strings, TypeScript knows every element is a string.

</details>

---

### 26. Declare Arrays Using Explicit Types

Create the following arrays:

1. A number array containing `100, 200, 300`
2. A string array containing `"Delhi", "Mumbai", "Kolkata"`
3. A symbol array containing two symbols

<details>
<summary>Show Solution</summary>

```ts
let nums: number[] = [100, 200, 300];

let cities: string[] = ["Delhi", "Mumbai", "Kolkata"];

let ids: symbol[] = [Symbol("A"), Symbol("B")];
```

</details>

---

### 27. Predict the Inferred Types

Given:

```ts
let arr1 = [10, 20, 30];
let arr2 = ["A", "B"];
let arr3 = [10, "A"];
let arr4 = [null, undefined];
let arr5 = [null, undefined, 50];
```

Write the inferred type of each array.

<details>
<summary>Show Solution</summary>

```ts
arr1 -> number[]
arr2 -> string[]
arr3 -> (string | number)[]
arr4 -> (null | undefined)[]
arr5 -> (null | undefined | number)[]
```

</details>

---

### 28. Create a Union Array

Create an array with the type:

```ts
(string | number)[]
```

Requirements:

- Add at least 3 strings
- Add at least 3 numbers
- Try adding `null`

<details>
<summary>Show Solution</summary>

```ts
let userResponse: (string | number)[] = [
  "Prashant",
  "Rahul",
  "Ankit",
  10,
  20,
  30,
];

// userResponse.push(null); // error
```

</details>

---

### 29. Practice map(), filter(), and reduce()

Given:

```ts
let scores = [10, 15, 20, 25, 30, 35, 40];
```

Perform the following:

1. Add 5 to every score using `map()`
2. Filter only even scores using `filter()`
3. Find the total using `reduce()`

<details>
<summary>Show Solution</summary>

```ts
let increased = scores.map((n) => n + 5);

let evenScores = scores.filter((n) => n % 2 === 0);

let total = scores.reduce((curr, acc) => curr + acc, 0);
```

</details>

---

### 30. Filter Strings From a Mixed Array

Given:

```ts
let scores2: (string | number)[] = [10, "Prashant", "Ankit", 20, "Atul", 30];
```

Perform the following:

1. Filter only strings.
2. Verify the inferred type.
3. Call a string method on every element using `forEach()`.

<details>
<summary>Show Solution</summary>

```ts
let userNames = scores2.filter((el) => typeof el == "string");

userNames.forEach((name) => name.toUpperCase());

// inferred type:
// string[]
```

</details>

---

### 31. Challenge Assignment

Predict the output and inferred type.

Given:

```ts
let result = 10 + "Prashant" + [10, 20, 30] + null + undefined;

console.log(result);
```

Questions:

1. What is the inferred type?
2. Why?
3. What is printed in the console?

<details>
<summary>Show Solution</summary>

### Inferred Type

```ts
string;
```

### Why?

A string appears in the expression:

```ts
10 + "Prashant";
```

From that point onward, `+` performs string concatenation.

### Output

```txt
10Prashant10,20,30nullundefined
```

</details>

---

## Section 3.3

### 1. Which statement correctly describes a tuple in TypeScript?

- A. A tuple can only store numbers.
- B. A tuple is a special array where order and types at specific positions matter.
- C. A tuple automatically becomes readonly.
- D. A tuple can only have two elements.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. A tuple is a special array where order and types at specific positions matter.**

Tuples allow you to define the exact type expected at each position.

```ts
let user: [string, number] = ["Prashant", 20];
```

</details>

---

### 2. What is the type of `user` below?

```ts
let user: [string, number] = ["Prashant", 20];
```

- A. `string[]`
- B. `number[]`
- C. `[string, number]`
- D. `(string | number)[]`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. `[string, number]`**

The tuple explicitly specifies that the first value is a string and the second value is a number.

</details>

---

### 3. Which tuple declaration is valid?

- A. `let user: [string, number] = ["Prashant", 20];`
- B. `let user: [string, number] = [20, "Prashant"];`
- C. `let user: [string, number] = ["Prashant"];`
- D. `let user: [string, number] = [20, 30];`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **A. `let user: [string, number] = ["Prashant", 20];`**

Tuple order and types must match exactly.

</details>

---

### 4. Why is the following code invalid?

```ts
let user: [string, number] = [20, "Prashant"];
```

- A. Tuple length is incorrect.
- B. First element should be a string and second should be a number.
- C. Tuples cannot store strings.
- D. Tuples cannot store numbers.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. First element should be a string and second should be a number.**

Tuple positions are strictly checked.

</details>

---

### 5. What will happen?

```ts
let pair: [number, number] = [10, 20, 30];
```

- A. Valid
- B. Runtime Error
- C. Compile-time Error
- D. Warning Only

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. Compile-time Error**

The tuple expects exactly two elements.

</details>

---

### 6. Which statement about tuple length is correct?

- A. Tuples always have unlimited length.
- B. Tuples usually have a fixed number of elements.
- C. Tuples can only contain one element.
- D. Tuple length is determined at runtime only.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Tuples usually have a fixed number of elements.**

Tuple definitions specify the expected number of values.

</details>

---

### 7. What is the type of `user[0]`?

```ts
let user: [string, number] = ["Prashant", 20];
```

- A. `number`
- B. `string`
- C. `string | number`
- D. `any`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. `string`**

TypeScript knows exactly what type exists at each position.

</details>

---

### 8. What is the type of `user[1]`?

```ts
let user: [string, number] = ["Prashant", 20];
```

- A. `string`
- B. `number`
- C. `string | number`
- D. `unknown`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. `number`**

The second position was explicitly declared as a number.

</details>

---

### 9. Which method call is valid?

```ts
let user: [string, number] = ["Prashant", 20];
```

- A. `user[0].toFixed(2)`
- B. `user[1].toUpperCase()`
- C. `user[0].toUpperCase()`
- D. `user[1].trim()`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. `user[0].toUpperCase()`**

The first element is a string.

</details>

---

### 10. Which method call is valid?

```ts
let user: [string, number] = ["Prashant", 20];
```

- A. `user[1].toFixed(2)`
- B. `user[1].toUpperCase()`
- C. `user[1].trim()`
- D. `user[1].includes(2)`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **A. `user[1].toFixed(2)`**

The second element is a number.

</details>

---

### 11. Why do tuples provide better tooling than normal arrays?

- A. They are faster.
- B. They use less memory.
- C. TypeScript knows the exact type at each index.
- D. They automatically become readonly.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. TypeScript knows the exact type at each index.**

This enables accurate autocomplete and type checking.

</details>

---

### 12. What is inferred for the following variable?

```ts
let tup1 = [10, "Prashant"];
```

- A. `[number, string]`
- B. `(string | number)[]`
- C. `any[]`
- D. `readonly [number, string]`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. `(string | number)[]`**

Without an explicit tuple type, TypeScript infers a regular array.

</details>

---

### 13. Why does the following produce an error?

```ts
let tup1 = [10, "Prashant"];

tup1[0].toFixed();
```

- A. `toFixed()` does not exist.
- B. `tup1[0]` may be a string.
- C. Arrays cannot use indexes.
- D. Tuple syntax is missing.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. `tup1[0]` may be a string.**

The inferred type is `(string | number)[]`.

</details>

---

### 14. Which declaration guarantees tuple behavior?

- A.

```ts
let tup = [10, "Prashant"];
```

- B.

```ts
let tup: [number, string] = [10, "Prashant"];
```

- C.

```ts
let tup: any[] = [10, "Prashant"];
```

- D.

```ts
let tup: object[] = [10, "Prashant"];
```

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B**

Explicit tuple declaration is required.

</details>

---

### 15. What does the following statement do?

```ts
pair[0] = 50;
```

Where:

```ts
let pair: [number, number] = [10, 20];
```

- A. Error
- B. Updates the first value
- C. Deletes the first value
- D. Makes tuple readonly

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Updates the first value**

Assignment is allowed because the type matches.

</details>

---

### 16. What happens here?

```ts
pair[0] = "50";
```

Where:

```ts
let pair: [number, number] = [10, 20];
```

- A. Valid
- B. Warning
- C. Compile-time Error
- D. Runtime Error

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. Compile-time Error**

A string cannot be assigned to a number position.

</details>

---

### 17. What happens here?

```ts
let pair: [number, number] = [10, 20];

pair.push(30);
```

- A. Compile-time Error
- B. Runtime Error
- C. Allowed
- D. Deletes existing value

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. Allowed**

Tuples are arrays internally.

</details>

---

### 18. Why is `push()` allowed on tuples?

- A. Tuples are objects.
- B. Tuples are arrays internally.
- C. TypeScript ignores tuple types.
- D. Push is converted into assignment.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Tuples are arrays internally.**

This is one of the most surprising tuple behaviors.

</details>

---

### 19. What happens here?

```ts
let pair: [number, number] = [10, 20];

pair.pop();
```

- A. Compile-time Error
- B. Runtime Error
- C. Allowed
- D. Tuple becomes readonly

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. Allowed**

Pop works because tuples are implemented using arrays.

</details>

---

### 20. Which tuple prevents modifications?

- A. `[number, number]`
- B. `(number | string)[]`
- C. `readonly [number, number]`
- D. `any[]`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. `readonly [number, number]`**

Readonly tuples disallow mutation operations.

</details>

---

### 21. What happens here?

```ts
const point: readonly [number, number] = [10, 20];

point[0] = 50;
```

- A. Allowed
- B. Compile-time Error
- C. Runtime Error
- D. Warning

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Compile-time Error**

Readonly tuples cannot be modified.

</details>

---

### 22. What happens here?

```ts
const point: readonly [number, number] = [10, 20];

point.push(30);
```

- A. Allowed
- B. Compile-time Error
- C. Runtime Error
- D. Push adds value

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Compile-time Error**

Readonly tuples disable mutation methods.

</details>

---

### 23. What are named tuples primarily used for?

- A. Runtime optimization
- B. Better readability
- C. Faster execution
- D. Reduced memory usage

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Better readability**

Named tuple labels help developers understand each position.

</details>

---

### 24. Do named tuple labels exist at runtime?

- A. Yes
- B. Only in browsers
- C. Only in Node.js
- D. No

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **D. No**

They exist only for development-time clarity.

</details>

---

### 25. Which is a named tuple?

- A.

```ts
let student: [string, number];
```

- B.

```ts
let student: [name: string, age: number];
```

- C.

```ts
let student: string[];
```

- D.

```ts
let student: number[];
```

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B**

Labels make tuple positions more readable.

</details>

---

### 26. When should you prefer a normal array?

- A. Fixed structure
- B. Different meaning at each position
- C. Variable number of similar values
- D. Coordinates

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. Variable number of similar values**

Arrays are better when the number of items can change.

</details>

---

### 27. Which example is best suited for a tuple?

- A. Student marks list
- B. Collection of products
- C. RGB color values
- D. List of cities

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. RGB color values**

Each position has a specific meaning.

</details>

---

### 28. Which example is best suited for a tuple?

- A. Employee record represented as `[name, salary]`
- B. List of scores
- C. List of usernames
- D. Collection of products

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **A**

Each position stores a different kind of information.

</details>

---

### 29. Which statement is true?

- A. Order does not matter in tuples.
- B. Tuples ignore types.
- C. Order matters in tuples.
- D. Tuples can store only strings.

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. Order matters in tuples.**

Changing order can cause type errors.

</details>

---

### 30. Which statement best summarizes tuples?

- A. Dynamic collections of similar values
- B. Fixed structured arrays with meaningful positions
- C. Objects with key-value pairs
- D. Readonly arrays

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Fixed structured arrays with meaningful positions**

That is the primary purpose of tuples.

</details>

---

# Assignments

### 31. Assignment 1

Create a tuple named `user` that stores:

1. Name (`string`)
2. Age (`number`)

Initialize it with your own values and print both elements.

---

### 32. Assignment 2

Create a tuple named `point` that stores X and Y coordinates.

Assign values and print them.

Example:

```ts
[10, 20];
```

---

### 33. Assignment 3

Create a tuple representing RGB color values.

Example:

```ts
[255, 0, 0];
```

Print each color component separately.

---

### 34. Assignment 4

Create a tuple:

```ts
[name: string, age: number, city: string]
```

Store your details and print all values.

---

### 35. Assignment 5

Create a tuple:

```ts
[string, number];
```

Try assigning values in the wrong order and observe the TypeScript error.

---

### 36. Assignment 6

Create a tuple:

```ts
[number, number];
```

Attempt to initialize it with three elements and observe the error.

---

### 37. Assignment 7

Create a tuple:

```ts
[number, number];
```

Update both indexes using assignment and print the updated tuple.

---

### 38. Assignment 8

Create a tuple:

```ts
[number, number];
```

Try assigning a string to one of the positions and observe the error.

---

### 39. Assignment 9

Create a tuple:

```ts
[number, number];
```

Use `push()` twice and print the tuple.

Observe how tuples behave like arrays.

---

### 40. Assignment 10

Create a tuple:

```ts
[number, number];
```

Push two values and then remove them using `pop()`.

Print the tuple before and after.

---

### 41. Assignment 11

Create a readonly tuple:

```ts
readonly[(number, number)];
```

Try:

```ts
point[0] = 50;
```

Observe the error.

---

### 42. Assignment 12

Create a readonly tuple and try calling:

```ts
push();
pop();
```

Observe the TypeScript errors.

---

### 43. Assignment 13

Create a named tuple for student details:

```ts
[name: string, age: number, marks: number]
```

Store values and print all properties using indexes.

---

### 44. Assignment 14

Create:

```ts
let tup1 = [10, "Prashant"];
```

Hover over the variable and note the inferred type.

---

### 45. Assignment 15

Create:

```ts
let tup2: [number, string] = [10, "Prashant"];
```

Call:

```ts
tup2[0].toFixed();
tup2[1].toUpperCase();
```

Verify that both work without errors.

---

### 46. Assignment 16

Create an employee tuple:

```ts
[string, number];
```

Store employee name and salary.

Print both values in a formatted message.

---

### 47. Assignment 17

Create a tuple representing a book:

```ts
[title: string, pages: number, price: number]
```

Store values and print them.

---

### 48. Assignment 18

Create a tuple representing a product:

```ts
[name: string, price: number, inStock: boolean]
```

Print all values.

---

### 49. Assignment 19

Create a tuple representing geographical coordinates:

```ts
[latitude: number, longitude: number]
```

Print both values.

---

### 50. Assignment 20

Create five real-world examples where tuples are more suitable than normal arrays and implement each example in TypeScript.

## Section 3.4

### 1. What does `readonly` do in the following tuple?

Given:

```ts
let tup1: readonly [string, number] = ["Prashant", 10];
```

- A. Makes the tuple store only strings
- B. Makes the tuple store only numbers
- C. Prevents modification of the tuple
- D. Converts the tuple into an array

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. Prevents modification of the tuple**

The `readonly` keyword makes the tuple read-only after creation.

```ts
let tup1: readonly [string, number] = ["Prashant", 10];
```

Values can be read but cannot be modified.

</details>

---

### 2. Which declaration correctly creates a readonly tuple?

- A. `let tup1: [string, number] readonly = ["Prashant", 10];`
- B. `let tup1: readonly [string, number] = ["Prashant", 10];`
- C. `let tup1: readonly string[] = ["Prashant", 10];`
- D. `let tup1: [readonly string, number] = ["Prashant", 10];`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B.**

The correct syntax is:

```ts
let tup1: readonly [string, number] = ["Prashant", 10];
```

</details>

---

### 3. Why does the following method not appear in IntelliSense?

Given:

```ts
let tup1: readonly [string, number] = ["Prashant", 10];

// tup1.push(...)
```

- A. Tuples never support methods
- B. `push()` exists only on arrays
- C. The tuple is readonly
- D. TypeScript removed `push()` from tuples

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. The tuple is readonly**

Because the tuple is marked as `readonly`, TypeScript hides mutating methods such as `push()`.

</details>

---

### 4. What does `readonly` do in the following array?

Given:

```ts
let arr1: readonly number[] = [10, 20, 30];
```

- A. Allows only one element
- B. Prevents modifications to the array
- C. Converts numbers into strings
- D. Makes the array immutable at runtime

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. Prevents modifications to the array**

TypeScript prevents operations that would modify the array.

```ts
let arr1: readonly number[] = [10, 20, 30];
```

</details>

---

### 5. Which declaration correctly creates a readonly array of numbers?

- A. `let arr1: readonly number[] = [10, 20, 30];`
- B. `let arr1: number readonly[] = [10, 20, 30];`
- C. `let arr1: readonly [10, 20, 30];`
- D. `let arr1: number[] readonly = [10, 20, 30];`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **A.**

```ts
let arr1: readonly number[] = [10, 20, 30];
```

This creates a read-only array of numbers.

</details>

---

### 6. Which operation is NOT allowed on the following array?

Given:

```ts
let arr1: readonly number[] = [10, 20, 30];
```

- A. `console.log(arr1[0])`
- B. Reading values using indexes
- C. `arr1.push(40)`
- D. Accessing the array length

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **C. `arr1.push(40)`**

`push()` modifies the array, so it is not allowed on a readonly array.

Reading values is still allowed.

</details>

---

### 7. Which statement is true about readonly arrays and readonly tuples?

- A. Values cannot be read from them
- B. They prevent mutating operations such as `push()`
- C. They can store only primitive values
- D. They automatically become `any[]`

<details>
<summary>Show Answer & Explanation</summary>

✅ Correct Answer: **B. They prevent mutating operations such as `push()`**

Examples:

```ts
let tup1: readonly [string, number] = ["Prashant", 10];

let arr1: readonly number[] = [10, 20, 30];
```

Mutating methods such as `push()` are not available, but reading values is allowed.

</details>

---
