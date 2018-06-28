![MongoAggreation](https://www.codeproject.com/KB/database/1149682/image001.png)

## Mongo Aggregations Pipeline
___To perform aggregations operations, MongoDB group values from multiple documents together and then perform a variety of operations on grouped data to return a single result.___

MongoDB has three ways to perform aggregation: the aggregation pipeline, the map-reduce function, and the single purpose aggregation methods, we will focus on aggregation pipeline. The MongoDB aggregation pipeline consists of stages. Each stage transforms the documents as they pass through the pipeline:
- `$project` – select, reshape data
- `$match` – filter data
- `$group` – aggregate data
- `$sort` – sorts data
- `$skip` – skips data
- `$limit` – limit data
- `$unwind` – normalizes data

#### $group
Groups documents based on some key.
```js
// Collection schema
var isd_schema = mongoose.Schema({}, {
  strict: false,
  collection: 'isds'
});
var isd_model = conn.model('isds', isd_schema);
// Count the number of Users Belonging To A Particular Region
isd.aggregate([
  {
    $group: {
      _id: '$region',  //$region is the column name in collection
      count: {$sum: 1}
    }
  }
], function (err, result) {
  if (err) {
    next(err);
  } else {
    res.json(result);
  }
});
```
#### $match
`$match` acts as a where condition to filter out documents. `$match` is a stage operator with this definition: `{ $match: { <query> } }`. The syntax for query is identical read operation query syntax.

<i>Because `$match` limits the total number of documents in the aggregation pipeline, earlier `$match` operations minimize the amount of processing down the pipe.</i>

In effect, with `$match` Mongo will filter the collection accoring to the query parameters, and only pass through the documents matching the query, to the next stage of the pipeline.
```js
// Collection Dchema
var isd_schema = mongoose.Schema({}, {
  strict: false,
  collection: 'isds'
});
// Number of users who joined last month
var time = new Date().getTime() - 30 * 24 * 60 * 60 * 1000;
isd.aggregate([
  {
    $match: {
      created: {$gt: new Date(time)}
    }
  },
  {
    $group: {
       _id: null,
      count: {$sum: 1}
    }
  }
], function (err, result) {
  if (err) {
    next(err);
  } else {
    res.json(result);
  }
});
```
#### $project
`$project` is used to add columns dynamically to the collection and use it for further aggregation.
```js
// Collection Schema
var isd_schema = mongoose.Schema({}, {
  strict: false,
  collection: 'isds'
});
// Number of User Registering Per Month
isd.aggregate([
  {
    $project: {
      month: {$month: "$created"}
    }
  }, {
    $group: {
      _id: "$month",
      users: {$sum: 1}
    }
  }
], function (err, result) {
  if (err) {
    next(err);
  } else {
    res.json(result);
  }
});
```

[Aggregation Pipeline](https://docs.mongodb.com/manual/core/aggregation-pipeline/)

[Aggregations in MongoDB by Example](https://www.compose.com/articles/aggregations-in-mongodb-by-example/)

#### [Return: Express README](../../README.md)
