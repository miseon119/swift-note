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

### Array

```swift
var a = Array<Int>()
a.append(5)
a.append(22)
```

### Class

`private` var:
```swift
class EmojiMemoryGame {
    private var model: MemoryGame<String>
}
```
other class can NOT read and write this `var`

`private(set)` var:
```swift
class EmojiMemoryGame {
    private(set) var model: MemoryGame<String>
}
```
can read this `var` but can not write(change) it.

static variable:
```swift
class EmojiMemoryGame {
    static let emojis = ["🥝", "🍉", "🥑", "🎅", "😂", "🎄", "🎁", "😁", "😘", "💣" ,"🤖", "💀",
    "🤓", "😅", "🤙", "🦷", "👣", "🧚‍♂️", "🧜‍♂️", "🧜‍♀️", "🧞‍♂️","🧞‍♀️"]

}
```

static function:
```swift
class EmojiMemoryGame {
    static let emojis = ["🥝", "🍉", "🥑", "🎅", "😂", "🎄", "🎁", "😁", "😘", "💣" ,"🤖", "💀",
    "🤓", "😅", "🤙", "🦷", "👣", "🧚‍♂️", "🧜‍♂️", "🧜‍♀️", "🧞‍♂️","🧞‍♀️"]
    
    static func createMemoryGame() -> MemoryGame<String> {
        MemoryGame<String>(numberOfpairsOfCards: 4) { pairIndex in EmojiMemoryGame.emojis[pairIndex]}
        
    }

    private var model: MemoryGame<String> = EmojiMemoryGame.createMemoryGame()

    var cards: Array<MemoryGame<String>.Card> {
        return model.cards 
    }
}
```
