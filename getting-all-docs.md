### Getting all documents in a Collection

To get all the documents in a collection use the `<Collection-Name>.all()` method. Let's assume we have a collection called `Letters`. To get all the document in this collection run the following code.

```fql
Letters.all()
```
Keep in mind that `<Collection-Name>.all()` method makes a complete scan of the collection. You can also chain `<Collection-Name>.all()` with other Collection methods. 


For instance if you want to get all the users who's age is greater than 10 you can chain a `where()` function with `all()` function. Following example code demostrates tis.

```fql
User.all().where(.age > 10)
```

You can keep adding multiple chains to this document. Following is an example to get all the users who are over 18 and has `Picard` as their lastname.

```fql
User.all()
  .where(.age > 10)
  .where(.lastname == 'Picard')
```