```

/* 1 */
{
    "_id" : 1.0,
    "item" : "abc",
    "price" : NumberDecimal("10"),
    "quantity" : 2,
    "date" : ISODate("2014-03-01T08:00:00.000Z")
}

/* 2 */
{
    "_id" : 2.0,
    "item" : "jkl",
    "price" : NumberDecimal("20"),
    "quantity" : 1,
    "date" : ISODate("2014-03-01T09:00:00.000Z")
}

/* 3 */
{
    "_id" : 3.0,
    "item" : "xyz",
    "price" : NumberDecimal("5"),
    "quantity" : 10,
    "date" : ISODate("2014-03-15T09:00:00.000Z")
}

/* 4 */
{
    "_id" : 4.0,
    "item" : "xyz",
    "price" : NumberDecimal("5"),
    "quantity" : 20,
    "date" : ISODate("2014-04-04T11:21:39.736Z")
}

/* 5 */
{
    "_id" : 5.0,
    "item" : "abc",
    "price" : NumberDecimal("10"),
    "quantity" : 10,
    "date" : ISODate("2014-04-04T21:23:13.331Z")
}

/* 6 */
{
    "_id" : 6.0,
    "item" : "def",
    "price" : NumberDecimal("7.5"),
    "quantity" : 5,
    "date" : ISODate("2015-06-04T05:08:13.000Z")
}

/* 7 */
{
    "_id" : 7.0,
    "item" : "def",
    "price" : NumberDecimal("7.5"),
    "quantity" : 10,
    "date" : ISODate("2015-09-10T08:43:00.000Z")
}

/* 8 */
{
    "_id" : 8.0,
    "item" : "abc",
    "price" : NumberDecimal("10"),
    "quantity" : 5,
    "date" : ISODate("2016-02-06T20:20:13.000Z")
}
Query with group by
--It will show the total quantity. group the item and push result into each array
db.getCollection('sales').aggregate([
    
    {
        $group : { 
            _id : "$item",
            books: { $push: "$$ROOT" },
             total : { $sum : "$quantity" }   
          }    
    }
]);

```
