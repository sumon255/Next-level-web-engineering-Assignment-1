Type narrowing is the process by which TypeScript refines an untyped or broad variable into a more specific type within a given execution path. By narrowing types, you prevent runtime exceptions and unlock type-safe access to properties and methods.

Common Type Narrowing Techniques:
TypeScript provides several ways to narrow types. Three commonly used techniques are typeof, instanceof, and the in operator.

1. Using typeof
The typeof operator checks the type of a variable at runtime. TypeScript uses the result to narrow the variable's type.

function printValue(value: string | number) {
  if (typeof value === "string") {
    console.log(value.toUpperCase());
  } else {
    console.log(value.toFixed(2));
  }
}

2. Using instanceof
The instanceof operator verifies whether an object is an instance of a specific class or constructor function by checking its prototype chain.

TypeScript
class Dog {
  bark() {
    console.log("Woof!");
  }
}

class Cat {
  meow() {
    console.log("Meow!");
  }
}

function makeSound(animal: Dog | Cat) {
  if (animal instanceof Dog) {
    animal.bark();
  } else {
    animal.meow();
  }
}

3. The in Operator Guard
The in operator checks whether a specific property or key exists on an object. This is particularly useful when differentiating between object shapes without needing classes.

TypeScript
type Admin = { role: string };
type User = { email: string };

function getDetails(person: Admin | User) {
  if ("role" in person) {
    console.log(person.role);
  } else {
    console.log(person.email);
  }
}
Conclusion
Type narrowing is a cornerstone of effective TypeScript development. By taking advantage of typeof, instanceof, and the in operator, you eliminate ambiguity across conditional branches and write cleaner, safer code when dealing with complex unions.