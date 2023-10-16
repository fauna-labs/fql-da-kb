### Creating Documents/Records in Collection
Collections are containers for holding documents or records in Fauna. To create a new Document in a collection use the `<Collection-Name>.create()` function. For instance if you have a collection called `User` run the following code to create a new user document.

```fql
User.create({
  name: "Jon Luc",
  email: "Jonluc@tng.world",
  rank: "Captain",
  assignment: "Startship USS Enterprise"
})
```

Following is another example of creating a document in `Post` collection. 

```fql
Post.create({
  title: "my blog post"
  description: "some awesome blog posr"
})
```
The `<Collection-Name>.create()` function receives an object as argument. FQL v10 objects works same as JavaScript objects. 