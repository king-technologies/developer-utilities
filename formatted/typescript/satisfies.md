# The satisfies Operator

The `satisfies` operator is used to check if a value satisfies a type. It is used in the following way:

- syntax: `someValue satisfies SomeType`

satisfies applies the best of both worlds:

The value must adhere to a specific shape (as with : declarations )
Type inference is still allowed to give the value a more narrow shape than the declared type

```typescript
type MyType = { a: number; b: string };

const value: MyType = { a: 1, b: "hello" };

if (value satisfies MyType) {
  console.log("value satisfies MyType");
}
```

In this example, the `satisfies` operator is used to check if the `value` variable satisfies the `MyType` type. If it does, the message `value satisfies MyType` is printed to the console.

The `satisfies` operator is useful for checking if a value conforms to a specific type at runtime. It can be used in conditional statements to perform different actions based on the type of a value.

The `satisfies` operator is a type guard, which means that it narrows the type of a value within a conditional block. This allows you to access properties of the value that are specific to the type being checked.

The `satisfies` operator is a powerful feature of TypeScript that allows you to write more robust and type-safe code. It can help you catch type errors at runtime and ensure that your code behaves as expected.

different Usage Example:

```typescript
interface Vibe {
  mood: "happy" | "sad";
}
const vibe = {
  mood: "happy",
} satisfies Vibe;
vibe.mood;
```

By using satisfies, we were able to make sure our vibe matched the Vibe interface, without forcing too wide a type for the mood property.
