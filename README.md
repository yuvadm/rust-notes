# Rust Book Notes

## Basics (Chapter 3)

### Variables and Mutability

- Variables are immutable by default
- `mut` keyword makes variables mutable
- Constants
  - are always immutable
  - must be set to constant expressions
  - must be type annotated
- Variables can always be shadowed (i.e. reassigned with `let`)
- Variable types cannot be mutated

### Data Types

- Types must be annotated when they cannot be infered
- Integers can be signed or unsigned and have an explicit size
- Floats have single or double precision
- Bools are bools
- Character types represent a Unicode scalar value
- Tuples bind different typed values together
- Tuple values are accesed with period e.g. `x.0`
- Arrays
  - have fixed lengths
  - all elements have same type
  - data is allocated on stack rather than heap
  - elements accessed via `a[0]`
  - out-of-bounds array access is a runtime panic

### Functions

- Function names are `snake_case`
- Function declaration order is irrelevant
- Function params must be type annotated
- Function bodies are statements with an optional ending expression
- Expressions do not end with semicolons
- The final function expression is the return value
- The `return` keyword can be explicit mid-function

### Comments

- Start with `// two slashes`
- Usually appear on separate lines above annotated code
- But can also appear `// on same line`

### Control Flow

- `if` conditions do not appear in parenthesis
- Multiple conditions are handled with `else if`
- `if`s are expressions and thus can be assigned to variables
- `loop` block will loop until `break`
- Or just use `while`
- `for` loops are the best choice as usual

## Ownership (Chapter 4)

### Ownership

- Each Rust value has an *owner*
- There can only be one owner at a time
- When an owner goes out of scope, the value is dropped
- Scopes are similar to other languages behavior
- `String`s are allocated on the heap
- When variables go out of scope Rust calls a `drop` function
- Shallow heap variables copies are actually *moves*
- Stack values are `Copy`ied (trait) as expected
- Semantics for passing values to functions are same
- References allow refering to values with taking ownership
- `&s1` is a reference to `s1`
- References cannot be mutated
- Mutable references (`&mut s1`) can be mutated
- Only one mutable reference to a given value can exist in scope
- At any given time you can have *either* one mutable references, or many immutable references
- References must always be valid

### Slices


