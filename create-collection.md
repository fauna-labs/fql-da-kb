## Collections in FQL v10
You can create new collections in Fauna using FQL v10. To create a new Collection you can run the following code. The code snippet creates a collection called `Activities`. 

```fql
Collection.create({ name: "Activities" })
```

Here's another example of creating a collection called `Book`

```fql
Collection.create({ name: "Activities" })
```

The Syntax for creating new collection is as follows.

```fql
Collection.create({ name: "<Your-Collection-Name>" })
```

You can also assign a newly created collection to a variable. FQL v10 assignments work simmilar to JavaScript. Following is an example

```fql
let x = Collection.create({ name: "<Your-Collection-Name>" })
x // <--- prints the newly created collection 
```
