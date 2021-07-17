# A generic constrained identity function

The function accepts a generic type and a runtime value.
The runtime value must extend the generic type.
The final type is the one of the value provided.

## Example

```ts
// inferred type: 'bar'
const good = constrain<string>()("foo" as const);

// Argument of type 'string' is not assignable to parameter of type 'number'.
const bad = constrain<number>()("foo" as const);
```

## The problem

You need to make sure a value conforms to a given type, while preserving its more accurate/narrow inferred type.
Typically TypeScript makes you choose one or the other.
This library allows you to have both.

## The future

It should be zero-runtime, therefore a babel-macro version makes sense.

## Q&A

Q: Why does it use this weird double function syntax?

A: Because of TypeScript limitations.

## Credits

Inspired by:

- Real-world problems at work
- [How to write a Constrained Identity Function (CIF) in TypeScript by Kent C. Dodds](https://kentcdodds.com/blog/how-to-write-a-constrained-identity-function-in-typescript)
