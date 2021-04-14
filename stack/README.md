## Stack

A stack is an ordered collection of items following the Last-In-First-Out (LIFO) principle. We add and remove items from the same part of the pile, called the top. We cannot remove items from the base. Just like a pile of books.

Stacks have tons of uses, from creating a history of pages visited to commands entered and to store actions that can be undone.

### Implementation

Internally the stack will be represented with a `slice` type, and I'll expose the following methods:

 - Push()
 - Pull()
 - New()

`New()` serves as the constructor, which initializes the internal slice when we start using it.

I’ll create an `ItemStack` generic type, concurrency safe, that can generate stacks containing any type by using `genny`, to create a type-specific stack implementation, encapsulating the actual value-specific data structure containing the data.

### Creating a concrete stack data structure

You can use this generic implementation to generate type-specific stacks, using

```
//generate a `IntStack` stack of `int` values
genny -in stack.go -out stack-int.go gen "Item=int"

//generate a `StringStack` stack of `string` values
genny -in stack.go -out stack-string.go gen "Item=string"
```