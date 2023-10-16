### CRUD (Create, Read, Update, Delete) Operations

This example shows how to do a CRUD operations in fql by building a simple TODO application. Follow these steps:

1. Create a `Todos` collection:

```fql
Collection.create({ name: "Todos" })
```

2. Add a new TODO item:

```fql
Todos.create({
  title: "🛍️ Go Shopping",
  completed: false,
})
```

3. Get all TODO items:

```fql
Todos.all()
```

4. Update a TODO item by its ID. Make sure to replace the '<id>' with your proper document id. 

```fql
let todo = Todos.byId("<id>")
todo.update({
 completed: true
})
```

5. Delete a TODO item by its ID:

```fql
Todos.byId(id).delete()
```

6. Get all completed TODO items:

```fql
Todos.where(.completed == true)
```

7. Get all incomplete TODO items:

```fql
Todos.where(.completed == false)
```

8. You can also get the first uncompleted todo with the following query

```fql
Todos.where(.completed == false).first()
```