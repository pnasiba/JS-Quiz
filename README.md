# JS-Quiz
// 1.  What will be logged to the console from the following code snippet? Explain the concept of hoisting.

// console . log ( myVar ); // undefined -> The variable myVar is hoisted to the top, but it's not initialized yet, so the result is undefined.
// var myVar = " Hello , World !";
// console . log ( myVar );  // Hello , World ! -> show that value. this is how var is hoisted but only declaration, not the value.

// 2.  Explain the difference in scope between variables declared with var, let, and const. Provide a code example that demonstrates the block scope of let.

// var - Function Scope -> this is available outside the block (if not in a function)
// let and const - Block Scope -> these are only available inside the block {} they were declared in.

// Example with let

// {
//     let text = "Hello, from inside the block."
//     console.log(text); // this works and result is Hello, from inside the block.
// }
// console.log(text); // ReferenceError: text is not defined

// Example with var
// {
//     var greeting = "Hi, from inside the block."
//     console.log(greeting); // this works and result is Hi, from inside the block
// }
// console.log(greeting); // this also works and result the same with the above that console.log.

// 3. (Variables) What is the output of the code below? Why does this happen?
// let x = 10;
// if (true) {
//   let x = 20;
//   console.log(x); // 20 -> this finds the inner x=20, and prints 20.
// }
// console.log(x); // 10 -> that inner x is not visible. So, js used the outer x=10, and prints 10.

// 4 (Variables) What happens when you execute the following code? Explain the behavior of const.

// const person = {
//   name: " Alex ",
// };
// person.name = " John "; // Is this line valid ? -> Valid
// console.log(person.name); // John
// person = { name: " Mary " }; // What about this line ? -> Is Not Valid, TypeError: Assignment to constant variable.

// 5 (Primitive Types) What is the output of the following two console.log statements? Explain the difference in how JavaScript handles the ‘+‘ and ‘-‘ operators with strings and numbers.
console.log("10" + 5); // 105 -> operator to concatenate "10" and 5, result in the string "105"
console.log("10" - 5); // 5 -> operator is mathematical operator, so this convert the string to number and subtracts 5, result is 5.

// 6. (Primitive Types) What do the following expressions evaluate to? Explain the concept of ”truthy” and ”falsy” in JavaScript.
Boolean(""); // false
Boolean(0); // false
Boolean(null); // false
Boolean([]); // true

// 7. (Primitive Types) What is the data type of null? What will the following code log to the console? Is the result considered a mistake in the language design?
console.log(typeof null); // object -> typeof null returns object.

// 8. )(Primitive Types) Explain the difference between null and undefined in JavaScript. Provide a scenario for when you would use each.

// null -> intentionally empty
// undefined -> not assigned yet

// let a; // undefined
// let b = null; // null(manually assigned)

// console.log(a); // undefined
// console.log(b); // null

//9. (If Statement) What will be logged to the console? Explain the logic flow.

// let score = 75;
// let grade;
// if (score >= 90) {
//   grade = "A ";
// } else if (score >= 80) {
//   grade = "B ";
// } else if (score >= 70) {
//   grade = "C ";
// } else {
//   grade = "D ";
// }
// console.log(grade); // result is C -> 75 is not >= 90 or 80, it's >= 70

// 10. (If Statement) Rewrite the following if-else statement using the ternary operator (? :).

// let age = 20;
// let message;
// if (age >= 18) {
//   message = " Adult ";
// } else {
//   message = " Minor ";
// }

// let age = 20;
// let message = age >= 18 ? "Adult" : "Minor";
// console.log(message);

// 11. (If Statement) What is the output of this code snippet? Explain JavaScript’s type coercion in the context of the ‘==‘ operator.
// if (0 == false) {
//   console.log(" First "); // First
// }
// if ("" == false) {
//   console.log(" Second "); // Second
// }
// if ([] == false) {
//   console.log(" Third "); // Third
// }
// == ->  loose equality operator. it'll try to convert the values being compared to the same type before checking for equality.

// 12. (If Statement) What alert will be shown? Explain why.
// if ("0") {
//   alert("Hello"); // Hello -> "0" is a non-empty string, so the condition is true
// }

// 13. (For Loops) Write a for loop that iterates from 1 to 5 and prints the square of each number to the console.
// for (let i = 1; i <= 5; i++) {
//   console.log(i * i);
// }

// 14. (For Loops) What is the output of the following code?
// for (let i = 0; i < 3; i++) {
//   console.log(` Outer loop : ${i} `);
//   for (let j = 0; j < 2; j++) {
//     console.log(` Inner loop : ${j} `);
//   }
// }
// Output:
//  Outer loop : 0
//  Inner loop : 0
//  Inner loop : 1
//  Outer loop : 1
//  Inner loop : 0
//  Inner loop : 1
//  Outer loop : 2
//  Inner loop : 0
//  Inner loop : 1

// 15. (For Loops) Write a for loop to calculate the sum of all elements in the given array numbers.
const numbers = [10, 20, 30, 40, 50];
let sum = 0;

for (let i = 0; i < numbers.length; i++) {
  sum += numbers[i];
}

console.log(sum); // result is 150

// 16. (For Loops) What will be logged to the console from this loop? Explain the role of the break statement.
for (let i = 1; i <= 10; i++) {
  if (i === 6) {
    break;
  }
  console.log(i);
}

// Output:
// 1
// 2
// 3
// 4
// 5

// loop prints numbers 1 to 5. When i === 6, break stops the loop.

// 17. (Functions) What is the primary difference between a function declaration and a function expression in terms of hoisting? Provide an example.
// Function declarations are hoisted completely (you can call them before they’re defined)
// Function expressions are not hoisted, or only the variable is hoisted (without the function value).

// Example:

// Function Declaration
greet(); // this works
function greet() {
  console.log("Hello"); // Hello
}

// Function Expression
// sayHi(); // Error: sayHi is not a function
// var sayHi = function () {
//   console.log("Hi");
// };

// 18. (Functions) Write a function named getRectangleArea that takes two parameters, width and height, and returns the area of the rectangle.

function getRectangleArea(width, height) {
  return width * height;
}

// console.log(getRectangleArea(20, 30));

// 19. (Functions) What does the following code output? Explain your reasoning.
function greet(name) {
  console.log(" Hello , " + name); // Hello, World
}
let result = greet(" World ");
console.log(result); // undefined
// function doesn't have a return statement, it returns undefined by default.

// 20. (Functions) What is an arrow function? Rewrite the following function declaration as an arrow function.
// function add(a, b) {
//   return a + b;
// }

const add = (a, b) => a + b;

// console.log(add(3, 6)); // 9
