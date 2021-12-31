# Basic

## Varieties of Types

- struct
- class
- protocol
- "Don't care" type (aka generics)
- enum
- functions

### Struct and Class

They both have ...

stored `var`, computed `var`.

constant `let`

e.g.
```swift
let defaultColor = Color.orange
```

support `func`

```swift
func multiply(operand: Int, by: Int) -> Int {
  return operand * by
}

multiply(operand: 5, by: 6)

func multiply(_ operand: Int, by otherOperand: Int) -> Int {
  return operand * otherOperand
}
multiply( 5, by: 6)

```

initializers (i.e. special functions that are called when creating a struct and class)


#### What's the difference between struct and class ?

| Struct  | Class |
|---|---|
| Value type(i.e. copied when passed or assigned)  | Reference type (i.e. Passed around via pointers)  |
| copy on write | automatically reference counted |
| Functional programming | Object-Oriented programming |
| No inheritance | Inheritance(Single) |
| "Free" init initializes ALL `var` | "Free" init initializes NO `var`|
| Mutability must be explicity stated | Always mutable |
