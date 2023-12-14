# MongoDB Cheat Sheet

## Show All Databases

```Bash
show dbs
```

## Show Current Database

```Bash
db
```

## Create Or Switch Database

```Bash
use acme
```

## Drop

```Bash
db.dropDatabase()
```

## Create Collection

```Bash
db.createCollection('posts')
```

## Show Collections

```Bash
show collections
```

## Insert Row

```Bash
db.posts.insert({
  title: 'Post One',
  body: 'Body of post one',
  category: 'News',
  tags: ['news', 'events'],
  user: {
    name: 'John Doe',
    status: 'author'
  },
  date: Date()
})
```

## Insert Multiple Rows

```Bash
db.posts.insertMany([
  {
    title: 'Post Two',
    body: 'Body of post two',
    category: 'Technology',
    date: Date()
  },
  {
    title: 'Post Three',
    body: 'Body of post three',
    category: 'News',
    date: Date()
  },
  {
    title: 'Post Four',
    body: 'Body of post three',
    category: 'Entertainment',
    date: Date()
  }
])
```

## Get All Rows

```Bash
db.posts.find()
```

## Get All Rows Formatted

```Bash
db.find().pretty()
```

## Find Rows

```Bash
db.posts.find({ category: 'News' })
```

## Sort Rows

```Bash
# asc
db.posts.find().sort({ title: 1 }).pretty()
# desc
db.posts.find().sort({ title: -1 }).pretty()
```

## Count Rows

```Bash
db.posts.find().count()
db.posts.find({ category: 'news' }).count()
```

## Limit Rows

```Bash
db.posts.find().limit(2).pretty()
```

## Chaining

```Bash
db.posts.find().limit(2).sort({ title: 1 }).pretty()
```

## Foreach

```Bash
db.posts.find().forEach(function(doc) {
  print("Blog Post: " + doc.title)
})
```

## Find One Row

```Bash
db.posts.findOne({ category: 'News' })
```

## Find Specific Fields

```Bash
db.posts.find({ title: 'Post One' }, {
  title: 1,
  author: 1
})
```

## Update Row

```Bash
db.posts.update({ title: 'Post Two' },
{
  title: 'Post Two',
  body: 'New body for post 2',
  date: Date()
},
{
  upsert: true
})
```

## Update Specific Field

```Bash
db.posts.update({ title: 'Post Two' },
{
  $set: {
    body: 'Body for post 2',
    category: 'Technology'
  }
})
```

## Increment Field (\$inc)

```Bash
db.posts.update({ title: 'Post Two' },
{
  $inc: {
    likes: 5
  }
})
```

## Rename Field

```Bash
db.posts.update({ title: 'Post Two' },
{
  $rename: {
    likes: 'views'
  }
})
```

## Delete Row

```Bash
db.posts.remove({ title: 'Post Four' })
```

## Sub-Documents

```Bash
db.posts.update({ title: 'Post One' },
{
  $set: {
    comments: [
      {
        body: 'Comment One',
        user: 'Mary Williams',
        date: Date()
      },
      {
        body: 'Comment Two',
        user: 'Harry White',
        date: Date()
      }
    ]
  }
})
```

## Find By Element in Array (\$elemMatch)

```Bash
db.posts.find({
  comments: {
     $elemMatch: {
       user: 'Mary Williams'
       }
    }
  }
)
```

## Add Index

```Bash
db.posts.createIndex({ title: 'text' })
```

## Text Search

```Bash
db.posts.find({
  $text: {
    $search: "\"Post O\""
    }
})
```

## Greater & Less Than

```Bash
db.posts.find({ views: { $gt: 2 } })
db.posts.find({ views: { $gte: 7 } })
db.posts.find({ views: { $lt: 7 } })
db.posts.find({ views: { $lte: 7 } })
```
