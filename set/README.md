## Set

A Set is a collection of values. You can iterate over those values, add new values, remove values and clear the set, get the set size, and check if the set contains an item. A value in the set might only be stored once, duplicates are not possible.

Notice the second line, which allows us to use the Set for any type we want, by [generating a specific implementation of this generic data structure](https://flaviocopes.com/golang-generic-generate/).

### Creating a concrete set data structure

Install `genny` if you don't have it already.

```
//generate a `StringSet` set of `string`s
genny -in set.go -out set-string.go gen "Iten=string Value=int"

//generate a `IntSet` set of `int`s
genny -in set.go -out set-int.go gen "Item=int"
```

### Terminar
https://flaviocopes.com/golang-data-structure-set/

