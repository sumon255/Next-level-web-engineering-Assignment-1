Type Alias vs. Interface in TypeScript
Introduction:
TypeScript provides two powerful ways to define custom types, These are- type aliases and interface. These help developers describe the structure of data and improve code readability. However, they have some important differences.

Core Differences:
An interface is primarily used to define the structure of objects. It supports declaration merging, meaning multiple declarations with the same name are automatically combined.
Code example--
interface User {
  name: string;
  age: number;
}

interface User {
  email: string;
}

A type alias, on the other hand, can define more than just object structures. It supports primitives, unions, intersections, tuples, and other complex types.
type Status = "success" | "error" | "loading";
type User = {
  name: string;
  age: number;
};

Both support extension, but they use different syntax. Interfaces use extends, while type aliases commonly use intersection operators (&).
interface Admin extends User {
  role: string;
}

type AdminUser = User & {
  role: string;
};

Conclusion:
You need to select an interfaces when defining object structures, especially when declaration merging or extensibility is useful. Choose type aliases when working with unions, tuples, primitives, or complex type combinations.