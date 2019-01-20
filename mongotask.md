# MongoDB Final task

## Q 1
```javascript
use mongo_practice
```
* Result
```javascript
switched to db mongo_practice
```
## Q 2
```javascript
db.createCollection("movie")
```
* Result
```javascript
db.createCollection("movie")
{
        "ok" : 1,
        "operationTime" : Timestamp(1547497348, 1),
        "$clusterTime" : {
                "clusterTime" : Timestamp(1547497348, 1),
                "signature" : {
                        "hash" : BinData(0,"S8Ngm1v/3CtA2++q1mu4awxTF3c="),
                        "keyId" : NumberLong("6635771712665288705")
                }
        }
}
```

## Q 2.1
```javascript
db.movie.insert([
	{
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
        "Brad Pitt",
        "Edward Norton",
        ]
	},
	{
		"title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
        "John Travolta",
        "Uma Thurman",
        ]
	},
	{
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
        "Brad Pitt",
        "Diane Kruger",
        "Eli Roth",
        ]
	},
    {
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
    },
    {
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
    },
    {
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
    },
    {
        "title" : "Pee Wee Herman's Big Adventure"
    },
    {
        "title" : "Avatar"
    }
])
```
* Result
```javascript
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 8,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
```
## Q 3
```javascript
db.movie.find().pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f8f"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f90"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f91"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f92"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f93"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f94"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f95"),
        "title" : "Pee Wee Herman's Big Adventure"
}
{ "_id" : ObjectId("5c43cdb6057bc9301eaf3f96"), "title" : "Avatar" }
```
## Q 4
```javascript
db.movie.find({writer:"Quentin Tarantino"}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f90"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f91"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
```
## Q 5
```javascript
db.movie.find({actors:{$in: ["Brad Pitt"]}}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f8f"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f91"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
```
## Q 6
```javascript
 db.movie.find({franchise:"The Hobbit"}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f92"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f93"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f94"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
```
## Q 7
```javascript
db.movie.find({year: { $gte :  1900, $lte : 1999}}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f8f"),
        "title" : "Fight Club",
        "writer" : "Chuck Palahniuk",
        "year" : 1999,
        "actors" : [
                "Brad Pitt",
                "Edward Norton"
        ]
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f90"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman"
        ]
}
```
## Q 8
```javascript
db.movie.find({year: { $gte :  2000, $lte : 2010}}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f91"),
        "title" : "Inglorious Basterds",
        "writer" : "Quentin Tarantino",
        "year" : 2009,
        "actors" : [
                "Brad Pitt",
                "Diane Kruger",
                "Eli Roth"
        ]
}
```
## Q 9
```javascript
db.movie.findAndModify({
    query: { title: "The Hobbit: An Unexpected Journey" },
	update: {
    $set: {synopsis: "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}
	}
})
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f92"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit"
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
```
## Q 10
```javascript
db.movie.findAndModify({
    query: { title: "The Hobbit: The Desolation of Smaug" },
	update: {
    $set: {synopsis: "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}
	}
})
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f93"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit"
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f93"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
```
## Q 11
```javascript
db.movie.findAndModify({
    query: { title: "Pulp Fiction" },
	update: {
    $push: {actors: "Samuel L. Jackson"}
	}
})
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f90"),
        "title" : "Pulp Fiction",
        "writer" : "Quentin Tarantino",
        "year" : 1994,
        "actors" : [
                "John Travolta",
                "Uma Thurman",
                "Samuel L. Jackson"
        ]
}
```

## Q 12
```javascript
 db.movie.find({synopsis: {$regex: /Bilbo/}}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f92"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f93"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f94"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
```
## Q 13
```javascript
db.movie.find({synopsis: {$regex: /Gandalf/}}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f93"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
```
## Q 14
```javascript
db.movie.find({synopsis: /(?=^.*Bilbo)(?!^.*Gandalf).*/}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f92"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f94"),
        "title" : "The Hobbit: The Battle of the Five Armies",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "Bilbo and Company are forced to engage in a war against an array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness."
}
```
## Q 15
```javascript
db.movie.find({$or:[{synopsis: /dwarves/ },{synopsis:/hobbit/}]}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f92"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f93"),
        "title" : "The Hobbit: The Desolation of Smaug",
        "writer" : "J.R.R. Tolkein",
        "year" : 2013,
        "franchise" : "The Hobbit",
        "synopsis" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
}
```
## Q 16 
```javascript
db.movie.find({$and:[{synopsis: /gold/ },{synopsis:/dragon/}]}).pretty()
```
* Result
```javascript
{
        "_id" : ObjectId("5c43cdb6057bc9301eaf3f92"),
        "title" : "The Hobbit: An Unexpected Journey",
        "writer" : "J.R.R. Tolkein",
        "year" : 2012,
        "franchise" : "The Hobbit",
        "synopsis" : "A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."
}
```
## Q 17
```javascript
db.movie.remove({title: "Pee Wee Herman's Big Adventure"})
```
* Result
```javascript
WriteResult({ "nRemoved" : 1 })
```
# Q 18
```javascript
db.movie.remove({title: "Avatar"})
```
* Result
```javascript
WriteResult({ "nRemoved" : 1 }) 
```


