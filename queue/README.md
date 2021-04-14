## Queue

A queue is a an ordered collection of items following the First-In-First-Out (FIFO) principle. We add items from one end of the queue, and we retrieve items from the other end.

Queue applications have all sorts of uses, which can be easily inferred from real-world queues. It’s not hard to imagine a queue representation of a supermarket line or the queue to get into a concert hall.

### Implementation

Internally the queue will be represented with a `slice` type, and I’ll expose the following methods:

 - New()
 - Enqueue()
 - Dequeue()
 - Front()
 - IsEmpty()
 - Size()

`New()` serves as the constructor, which initializes the internal slice when we start using it.

I’ll create an `ItemQueue` generic type, concurrency safe, that can generate queues containing any type by using `genny`, to create a type-specific queue implementation, encapsulating the actual value-specific data structure containing the data.

### Creating a concrete queue data structure

You can use this generic implemenation to generate type-specific queues, using

```
//generate a `IntQueue` queue of `int` values
genny -in queue.go -out queue-int.go gen "Item=int"

//generate a `StringQueue` queue of `string` values
genny -in queue.go -out queue-string.go gen "Item=string"
```