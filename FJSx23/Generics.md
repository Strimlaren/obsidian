Back to [[FJSx23]] / [[TypeScript]]
### What is it?

Generics in TypeScript are like flexible templates that allow you to create components (like functions, classes, or interfaces) that can work with different types without specifying the exact type upfront. Think of them as a way to write reusable code that can handle different data types in a type-safe way.

### Simple Analogy

Imagine you have a box, and you want to store something in it. Instead of having a specific box for apples, another for oranges, and another for books, you could have a "generic" box that can hold any of these items. When you decide to use the box, you tell it what kind of item you'll be putting in it (apples, oranges, or books), and from that point on, it will only accept that type of item.

### How Generics Work

1. **Flexible Function**: Suppose you write a function that just returns whatever you give it. Without generics, you might write one version of the function for each type of input. With generics, you write one function that works for any type.

   ```typescript
   function identity<T>(value: T): T {
     return value;
   }
   ```

   - `T` is a placeholder for the type that will be specified later.
   - You can call `identity` with a string, number, or any other type.

2. **Type Safety**: When you use the generic function, TypeScript knows what type you’re working with and ensures you don’t accidentally do something wrong.

   ```typescript
   const result = identity<string>("hello"); // T is string
   const anotherResult = identity<number>(42); // T is number
   ```

3. **Reusable Code**: Generics allow you to reuse the same code for different types without having to rewrite it for each type.

### Why Generics Are Useful

- **Reusability**: Write one piece of code that works for multiple types.
- **Type Safety**: Ensures that you don’t mix up types, reducing bugs.
- **Flexibility**: Allows your code to be more adaptable to different situations.

In summary, generics let you write flexible and reusable code while still keeping things type-safe, so you don’t accidentally mix up your data types.