```
C:\Users\NGOPALAM\Downloads\mongosh-1.1.7-win32-x64\bin>mongosh "mongodb+srv://cluster0.pbzos.mongodb.net/myFirstDatabase" --username 007
Enter password: ***
Current Mongosh Log ID: 61daa3e24d8461f519c9f02d
Connecting to:          mongodb+srv://cluster0.pbzos.mongodb.net/myFirstDatabase
Using MongoDB:          4.4.10
Using Mongosh:          1.1.7 
For mongosh info see: https://docs.mongodb.com/mongodb-shell/
```
                      MongoDB Exercise in mongo shell
                      
Connect to a running mongo instance, use a database named mongo_practice.
Atlas atlas-awkq71-shard-0 [primary] myFirstDatabase> use mongodb_practice
switched to db mongodb_practice

```
->collection creation
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.createcollection('movies')
```
```
-> inserting files into collection
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.movies.insertMany([{title:'Fight Club', writer: 'Chuck Palahniuko', year:1999, actors:['Brad Pitt','Edwrd Norton']}, {title:'Pulp Fiction',writer:'Quentin Tarantino',year:1994,actors:['John Travolta','Uma Thurman']},{title: 'Inglorious Basterds', writer: 'Quentin Tarantino', year: 2009, actors: ['Brad Pitt','Diane Kruger','Eli Roth']}, {title: 'The Hobbit: An Unexpected Journey', writer: 'J.R.R Tolkein', year: 2012, franchise: 'The Hobbit'}, {title: 'The Hobbit: The Desolation of Smaug', writer: 'J.R.R Tolkein', year: 2013, franchise: 'The Hobbit'}, {title: 'The Hobbit: The Battle of the Five Armies', writer: 'J.R.R Tolkein', year: 2012, franchise: 'The Hobbit', synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'}, {title:"Pee Wee Herman's Big Adventure"},{title: 'Avatar'}])
```
```
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("61daa6b716a10db11a817bbd"),
    '1': ObjectId("61daa6b716a10db11a817bbe"),
    '2': ObjectId("61daa6b716a10db11a817bbf"), 
    '3': ObjectId("61daa6b716a10db11a817bc0"),
    '4': ObjectId("61daa6b716a10db11a817bc1"),
    '5': ObjectId("61daa6b716a10db11a817bc2"),
    '6': ObjectId("61daa6b716a10db11a817bc3"),
    '7': ObjectId("61daa6b716a10db11a817bc4")
  }
}
```



        Queries

query the movies collection to

1. get all documents
```

     Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find()
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb5"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb6"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb7"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb8"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb9"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bba"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bbb"),
    title: "Pee Wee Herman's Big Adventure"
  },
  { _id: ObjectId("61daa60a16a10db11a817bbc"), title: 'Avatar' },
  {
    _id: ObjectId("61daa6b716a10db11a817bbd"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbe"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbf"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc0"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc1"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc2"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc3"),
    title: "Pee Wee Herman's Big Adventure"
  },
  { _id: ObjectId("61daa6b716a10db11a817bc4"), title: 'Avatar' }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```


2. get all documents with writer set to "Quentin Tarantino"
 ```
   Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({writer:"Quentin Tarantino"})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb6"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb7"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbe"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbf"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```

3. get all documents where actors include "Brad Pitt"
 ```
 Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({actors:"Brad Pitt"})
 
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb5"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb7"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbd"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbf"),
    title: 'Inglorious Basterds',
    writer: 'Quentin Tarantino',
    year: 2009,
    actors: [ 'Brad Pitt', 'Diane Kruger', 'Eli Roth' ]
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
4. get all documents with franchise set to "The Hobbit"  
   Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({franchise:"The Hobbit"})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb8"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb9"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bba"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc0"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc1"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc2"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```

5. get all movies released in the 90s
```
   Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({year:{$gt:1990,$lt:2000}})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb5"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb6"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbd"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbe"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  }
]
```

6. get all movies released before the year 2000 or after 2010
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({$or:[{year:{gt:2010}},{year:{$lt:2000}}]})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb5"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb6"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbd"),
    title: 'Fight Club',
    writer: 'Chuck Palahniuko',
    year: 1999,
    actors: [ 'Brad Pitt', 'Edwrd Norton' ]
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bbe"),
    title: 'Pulp Fiction',
    writer: 'Quentin Tarantino',
    year: 1994,
    actors: [ 'John Travolta', 'Uma Thurman' ]
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```


```
     Update Documents

1. add a synopsis to "The Hobbit: An Unexpected Journey" : "A reluctant hobbit, Bilbo Baggins, sets out to 
  the Lonely Mountain with a spirited group of dwarves to
  reclaim their mountain home - and the gold within it - from the dragon Smaug."
  ```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.movies.update({title:'The Hobbit: An Unexpected Journey'}, {$set:{synopsis:"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
DeprecationWarning: Collection.update() is deprecated. Use updateOne, updateMany, or bulkWrite.
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> 
2. add a synopsis to "The Hobbit: The Desolation of Smaug" : "The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.update({title:'The Hobbit: The Desolation of Smaug'}, {$set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
3. add an actor named "Samuel L. Jackson" to the movie "Pulp Fiction"
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.update({title:'Pulp Fiction'}, {$push:{actors:"Samuel L. Jackson"}})
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 1,
  modifiedCount: 1,
  upsertedCount: 0
}
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```
```
Text Search
1. find all movies that have a synopsis that contains the word "Bilbo"
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.movies.find({synopsis:{$regex:"Bilbo"}})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb8"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb9"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit',
    synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bba"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc2"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
2. find all movies that have a synopsis that contains the word "Gandalf"
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.movies.find({synopsis:{$regex:"Bilbo"}})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb8"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bb9"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit',
    synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bba"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc2"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({synopsis:{$regex:"Gandalf"}})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb9"),
    title: 'The Hobbit: The Desolation of Smaug',
    writer: 'J.R.R Tolkein',
    year: 2013,
    franchise: 'The Hobbit',
    synopsis: 'The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring.'
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
3. find all movies that have a synopsis that contains the word "Bilbo" and not the word "Gandalf"
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb8"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bba"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc2"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> 
```


4. find all movies that have a synopsis that contains the word "dwarves" or "hobbit"
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb8"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bba"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc2"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```
5. find all movies that have a synopsis that contains the word "gold" and "dragon"
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})
[
  {
    _id: ObjectId("61daa60a16a10db11a817bb8"),
    title: 'The Hobbit: An Unexpected Journey',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug.'
  },
  {
    _id: ObjectId("61daa60a16a10db11a817bba"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  },
  {
    _id: ObjectId("61daa6b716a10db11a817bc2"),
    title: 'The Hobbit: The Battle of the Five Armies',
    writer: 'J.R.R Tolkein',
    year: 2012,
    franchise: 'The Hobbit',
    synopsis: 'Bilbo and Company are forced to engage in a war against array of combatants and keep the Lonely Mountain from falling into the hands of a rising darkness'
  }
]
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.find({$and:[{synopsis:{$regex:"gold"}}, {synopsis:{$reg$rege$reg$regex:"dragon"}}]})
```

```
 ->Delete Documents
 ```
1. delete the movie "Pee Wee Herman's Big Adventure"
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.movies.remove({tittle:"Pee Wee Herman's Big Adventure"})
{ acknowledged: true, deletedCount: 1 }
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>


2. delete the movie "Avatar"
  Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
DeprecationWarning: Collection.remove() is deprecated. Use deleteOne, deleteMany, findOneAndDelete, or bulkWrite.
{ acknowledged: true, deletedCount: 2 }

->Relationships
Insert the following documents into a users collection username : GoodGuyGreg first_name : "Good Guy" last_name : "Greg" username : ScumbagSteve full_name : first : "Scumbag" last : "Steve"

creating collection
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.createCollection('users')
{ ok: 1 }

```
insertion
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.users.insertMany([{ username: 'GoodGuyGreg', first_name: 'GoodGuy', last_name: 'Greg' }, { username: 'ScumbagSteve', fullname: { first: 'Scumbag', last: 'Steve' } }])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("61dabf6516a10db11a817bc5"),
    '1': ObjectId("61dabf6516a10db11a817bc6")
  }
}
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```


Insert the following documents into a posts collection username :
GoodGuyGreg title : Passes out at party body : Wakes up early and cleans house
username : GoodGuyGreg title : Steals your identity body : Raises your credit score username :
GoodGuyGreg title : Reports a bug in your code body : Sends you a Pull Request username :
ScumbagSteve title : Borrows something body : Sells it username : ScumbagSteve title : 
Borrows everything body : The end username : ScumbagSteve title : Forks your repo on github body : Sets to private

collection- posts
```
creation
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.createCollection('posts')
{ ok: 1 }
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>
```
```
INSERTION


Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.posts.insertMany([{ username: 'GoodGuyGreg', title: 'Passes out at party', body: 'Wakes up early and cleans house' },{ username: 'GoodGuyGreg', title: 'Steals your identity', body: 'Raises your credit score' },{ username: 'GoodGuyGreg', title: 'Reports a bug in your code', body: 'Sends you a pull request' },{ username: 'ScumbagSteve', title: 'Borrows something', body: 'Sells it' },{ username: 'ScumbagSteve', title: 'Borrows everything', body: 'The end' }, { username: 'ScumbagSteve', title: 'Forks your repo in github', body: 'Sets to private' }])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId("61dac06216a10db11a817bc7"),
    '1': ObjectId("61dac06216a10db11a817bc8"),
    '2': ObjectId("61dac06216a10db11a817bc9"),
    '3': ObjectId("61dac06216a10db11a817bca"),
    '4': ObjectId("61dac06216a10db11a817bcb"),
    '5': ObjectId("61dac06216a10db11a817bcc")
  }
}
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>




Insert the following documents into a comments collection
CREATING COLLECTION - COMMENTS
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.createCollection('comments')
{ ok: 1 }
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>

~username : GoodGuyGreg comment : liked it a lot post : [post_obj_id]
where [post_obj_id] is the ObjectId of the posts document: "Borrows something"
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.comments.insert({username:'GoodGuyGreg',comment:'liked it a lot',post:ObjectId("61dac06216a10db11a817bca")})
{
  acknowledged: true,
  insertedIds: { '0': ObjectId("61dac8a016a10db11a817bcf") }
}



~username : GoodGuyGreg comment : What's mine is yours! post : [post_obj_id]
where [post_obj_id] is the ObjectId of the posts document: "Borrows everything"

Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.comments.insert(
... {username:'GoodGuyGreg', comment: 'Hope you got a good deal!', post:ObjectId("61dac06216a10db11a817bcb")})
DeprecationWarning: Collection.insert() is deprecated. Use insertOne, insertMany, or bulkWrite.
{
  acknowledged: true,
  insertedIds: { '0': ObjectId("61dac06216a10db11a817bcb") }
}





~username : GoodGuyGreg comment : Don't violate the licensing agreement! post : [post_obj_id]
where [post_obj_id] is the ObjectId of the posts document: "Forks your repo on github
Atlas atlas-awkq71-shard-0 mongodb_practice> db.comments.insert(
... {username: 'GoodGuyGreg', comment: "Don't violate the licensing agreement!", post:ObjectId("61dac06216a10db11a817bcc")})
{
  acknowledged: true,
  insertedIds: { '0': ObjectId("61dac06216a10db11a817bcc") }
}





username : ScumbagSteve comment : It still isn't clean post : [post_obj_id]
where [post_obj_id] is the ObjectId of the posts document: "Passes out at party"
Atlas atlas-awkq71-shard-0[primary] mongodb_practice> db.comments.insert(
... {username: 'ScumbagSteve', comment: "It still isn't clean", post:ObjectId("61dac06216a10db11a817bc7")})
{
  acknowledged: true,
  insertedIds: { '0': ObjectId("61dac06216a10db11a817bc7") }
}
```







~username : ScumbagSteve comment : Denied your PR cause I found a hack post : [post_obj_id]
where [post_obj_id] is the ObjectId of the posts document: "Reports a bug in your code"

```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.comments.insert(
... {username: 'ScumbagSteve', comment: "Denied your PR cause I found a hack",
..... post:ObjectId("61da8e8bf1e258629fdd6f67")})
{
  acknowledged: true,
  insertedIds: { '0': ObjectId("61da8e8bf1e258629fdd6f67") }
}


Querying related collections
1. find all users
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.users.find().pretty()
[
  {
    _id: ObjectId("61da85b9f1e258629fdd6f5a"),
    username: 'GoodGuyGreg',
    first_name: 'GoodGuy',
    last_name: 'Greg'
  },
  {
    _id: ObjectId("61da85b9f1e258629fdd6f5b"),
    username: 'ScumbagSteve',
    fullname: { first: 'Scumbag', last: 'Steve' }
  }
]
```
2. find all posts
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.posts.find().pretty()
[
  {
    _id: ObjectId("61da896cf1e258629fdd6f5c"),
    username: 'GoodGuyGreg',
    title: 'Passes out at party',
    body: 'Wakes up early and cleans house'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f5d"),
    username: 'GoodGuyGreg',
    title: 'Steals your identity',
    body: 'Raises your credit score'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f5e"),
    username: 'GoodGuyGreg',
    title: 'Reports a bug in your code',
    body: 'Sends you a pull request'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f5f"),
    username: 'ScumbagSteve',
    title: 'Borrows something',
    body: 'Sells it'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f60"),
    username: 'ScumbagSteve',
    title: 'Borrows everything',
    body: 'The end'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f61"),
    username: 'ScumbagSteve',
    title: 'Forks your repo in github',
    body: 'Sets to private'
  }
]
```

3. find all posts that was authored by "GoodGuyGreg"
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.posts.find({username:"GoodGuyGreg"})
[
  {
    _id: ObjectId("61da896cf1e258629fdd6f5c"),
    username: 'GoodGuyGreg',
    title: 'Passes out at party',
    body: 'Wakes up early and cleans house'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f5d"),
    username: 'GoodGuyGreg',
    title: 'Steals your identity',
    body: 'Raises your credit score'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f5e"),
    username: 'GoodGuyGreg',
    title: 'Reports a bug in your code',
    body: 'Sends you a pull request'
  }
]
```

4. find all posts that was authored by "ScumbagSteve"
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice>  db.posts.find({username:"ScumbagSteve"})
[
  {
    _id: ObjectId("61da896cf1e258629fdd6f5f"),
    username: 'ScumbagSteve',
    title: 'Borrows something',
    body: 'Sells it'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f60"),
    username: 'ScumbagSteve',
    title: 'Borrows everything',
    body: 'The end'
  },
  {
    _id: ObjectId("61da896cf1e258629fdd6f61"),
    username: 'ScumbagSteve',
    title: 'Forks your repo in github',
    body: 'Sets to private'
  }
]
``` 


5. find all comments
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.comments.find().pretty()
[
  {
    _id: ObjectId("61da8b2ef1e258629fdd6f62"),
    username: 'GoodGuyGreg',
    comment: 'Hope you got a good deal!',
    post: ObjectId("61da896cf1e258629fdd6f5f")
  },
  {
    _id: ObjectId("61da8cd5f1e258629fdd6f64"),
    username: 'GoodGuyGreg',
    comment: "What's mine is yours!",
    post: ObjectId("61da896cf1e258629fdd6f60")
  },
  {
    _id: ObjectId("61da8d6ef1e258629fdd6f65"),
    username: 'GoodGuyGreg',
    comment: "Don't violate the licensing agreement!",
    post: ObjectId("61da896cf1e258629fdd6f61")
  },
  {
    _id: ObjectId("61da8dfcf1e258629fdd6f66"),
    username: 'ScumbagSteve',
    comment: "It still isn't clean",
    post: ObjectId("61da896cf1e258629fdd6f5c")
  },
  {
    _id: ObjectId("61da8e8bf1e258629fdd6f67"),
    username: 'ScumbagSteve',
    comment: 'Denied your PR cause I found a hack',
    post: ObjectId("61da896cf1e258629fdd6f5e")
  }
]
```

6. find all comments that was authored by "GoodGuyGreg"
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> 
db.comments.find({username:"GoodGuyGreg"})
[
  {
    _id: ObjectId("61da8b2ef1e258629fdd6f62"),
    username: 'GoodGuyGreg',
    comment: 'Hope you got a good deal!',
    post: ObjectId("61da896cf1e258629fdd6f5f")
  },
  {
    _id: ObjectId("61da8cd5f1e258629fdd6f64"),
    username: 'GoodGuyGreg',
    comment: "What's mine is yours!",
    post: ObjectId("61da896cf1e258629fdd6f60")
  },
  {
    _id: ObjectId("61da8d6ef1e258629fdd6f65"),
    username: 'GoodGuyGreg',
    comment: "Don't violate the licensing agreement!",
    post: ObjectId("61da896cf1e258629fdd6f61")
  }
]
```
7. find all comments that was authored by "ScumbagSteve"
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.comments.find({username:'ScumbagSteve'})
[
  {
    _id: ObjectId("61da8dfcf1e258629fdd6f66"),
    username: 'ScumbagSteve',
    comment: "It still isn't clean",
    post: ObjectId("61da896cf1e258629fdd6f5c")
  },
  {
    _id: ObjectId("61da8e8bf1e258629fdd6f67"),
    username: 'ScumbagSteve',
    comment: 'Denied your PR cause I found a hack',
    post: ObjectId("61da896cf1e258629fdd6f5e")
  }
]
```
8. find all comments belonging to the post "Reports a bug in your code"
```
Atlas atlas-awkq71-shard-0 [primary] mongodb_practice> db.comments.find({post:ObjectId("61da896cf1e258629fdd6f5e")})
[
  {
    _id: ObjectId("61da8e8bf1e258629fdd6f67"),
    username: 'ScumbagSteve',
    comment: 'Denied your PR cause I found a hack',
    post: ObjectId("61da896cf1e258629fdd6f5e")
  }
]
```






                     assignment 2





                                                  MongoDB -Aggregation Exercises
Import the zips.json file into your MongoDB. Database name is "population" and collection name is "zipcodes".

mongoimport --db population --collection zipcodes --file C:/SUBSATPA/zips.json



    Atlanta Population

~use db.zipcodes.find() to filter results to only the results where city is ATLANTA and state is GA.
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.find({$and:[{city:'ATLANTA'},{state: 'GA'}]})
[
  {
    _id: '30303',
    city: 'ATLANTA',
    loc: [ -84.388846, 33.752504 ],
    pop: 1845,
    state: 'GA'
  },
  {
    _id: '30305',
    city: 'ATLANTA',
    loc: [ -84.385145, 33.831963 ],
    pop: 19122,
    state: 'GA'
  },
  {
    _id: '30306',
    city: 'ATLANTA',
    loc: [ -84.351418, 33.786027 ],
    pop: 20081,
    state: 'GA'
  }
  .
  .
  .
 ]
Type "it" for more.


~use db.zipcodes.aggregate with $match to do the same as above.
Atlas atlas-awkq71-shard-0 [primary]population> db.zipcodes.aggregate([{$match:{$and:[{city:'ATLANTA'},{state:'GA'}]}}])
[
  {
    _id: '30303',
    city: 'ATLANTA',
    loc: [ -84.388846, 33.752504 ],
    pop: 1845,
    state: 'GA'
  },
  {
    _id: '30305',
    city: 'ATLANTA',
    loc: [ -84.385145, 33.831963 ],
    pop: 19122,
    state: 'GA'
  },
  {
    _id: '30306',
    city: 'ATLANTA',
    loc: [ -84.351418, 33.786027 ],
    pop: 20081,
    state: 'GA'
  }
 .
 .
 .
 ]
Type "it" for more.


~use $group to count the number of zip codes in Atlanta.
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([{$group:{_id: '$city'}},{$count:"ATLANTA"}])
[ { ATLANTA: 16584 } ]

~use $group to find the total population in Atlanta.
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([{$group:{_id:'$city', totalpop: {$sum:'$pop'}}},{$match:{_id:"ATLANTA"}}])
[ { _id: 'ATLANTA', totalpop: 630046 } ]




  Population by state


~use aggregate to calculate the total population for each state
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([{$group:{_id:"$state", totalpop:{ $sum: "$pop"}}}])
[
  { _id: 'SD', totalpop: 695397 },
  { _id: 'NM', totalpop: 1515069 },
  { _id: 'VA', totalpop: 6181479 },
  { _id: 'MS', totalpop: 2573216 },
  { _id: 'NC', totalpop: 6628637 },
  { _id: 'TX', totalpop: 16984601 },
  { _id: 'LA', totalpop: 4217595 },
  { _id: 'VT', totalpop: 562758 },
  { _id: 'IA', totalpop: 2776420 },
  { _id: 'NH', totalpop: 1109252 },
  { _id: 'FL', totalpop: 12686644 },
  { _id: 'IL', totalpop: 11427576 },
  { _id: 'MN', totalpop: 4372982 },
  { _id: 'AR', totalpop: 2350725 },
  { _id: 'ID', totalpop: 1006749 },
  { _id: 'OH', totalpop: 10846517 },
  { _id: 'MA', totalpop: 6016425 },
  { _id: 'PA', totalpop: 11881643 },
  { _id: 'SC', totalpop: 3486703 },
  { _id: 'NY', totalpop: 17990402 }
]
Type "it" for more
  ~sort the results by population, highest first
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([{$group:{_id:"$state", totalpop:{ $sum: "$pop"}}},{$sort: {totalpop:-1}}])
[
  { _id: 'CA', totalpop: 29754890 },
  { _id: 'NY', totalpop: 17990402 },
  { _id: 'TX', totalpop: 16984601 },
  { _id: 'FL', totalpop: 12686644 },
  { _id: 'PA', totalpop: 11881643 },
  { _id: 'IL', totalpop: 11427576 },
  { _id: 'OH', totalpop: 10846517 },
  { _id: 'MI', totalpop: 9295297 },
  { _id: 'NJ', totalpop: 7730188 },
  { _id: 'NC', totalpop: 6628637 },
  { _id: 'GA', totalpop: 6478216 },
  { _id: 'VA', totalpop: 6181479 },
  { _id: 'MA', totalpop: 6016425 },
  { _id: 'IN', totalpop: 5544136 },
  { _id: 'MO', totalpop: 5110648 },
  { _id: 'WI', totalpop: 4891769 },
  { _id: 'TN', totalpop: 4876457 },
  { _id: 'WA', totalpop: 4866692 },
  { _id: 'MD', totalpop: 4781379 },
  { _id: 'MN', totalpop: 4372982 }
]
Type "it" for more

~limit the results to just the first 3 results. What are the top 3 states in population?
Atlas atlas-awkq71-shard-0 [primary]population> db.zipcodes.aggregate([{$group:{_id:"$state", totalpop:{ $sum: "$pop"}}},{$sort: {totalpop:-1}},{$limit:3}])
[
  { _id: 'CA', totalpop: 29754890 },
  { _id: 'NY', totalpop: 17990402 },
  { _id: 'TX', totalpop: 16984601 }
]


         Population by city
~use aggregate to calculate the total population for each city (you have to use city/state combination). You can use a combination for the _id of the $group: { city: '$city', state: '$state' }
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([{$group: {_id:{state:"$state",city:"$city"},
... pop:{$sum:"$pop"}}}])
[
  { _id: { state: 'CA', city: 'ONYX' }, pop: 380 },
  { _id: { state: 'IL', city: 'MEDORA' }, pop: 531 },
  { _id: { state: 'AR', city: 'DARDANELLE' }, pop: 8281 },
  { _id: { state: 'ME', city: 'FRANKLIN' }, pop: 1433 },
  { _id: { state: 'ND', city: 'BERWICK' }, pop: 1251 },
  { _id: { state: 'PA', city: 'THOMASVILLE' }, pop: 3435 },
  { _id: { state: 'NY', city: 'OGDENSBURG' }, pop: 19659 },
  { _id: { state: 'OH', city: 'MAUMEE' }, pop: 22993 },
  { _id: { state: 'GA', city: 'BROOKLET' }, pop: 4850 },
  { _id: { state: 'CA', city: 'CEDARVILLE' }, pop: 991 },
  { _id: { state: 'WV', city: 'ULER' }, pop: 724 },
  { _id: { state: 'NC', city: 'DUDLEY' }, pop: 8450 },
  { _id: { state: 'IN', city: 'MADISON' }, pop: 20596 },
  { _id: { state: 'MN', city: 'GOODVIEW' }, pop: 34518 },
  { _id: { state: 'OR', city: 'KENO' }, pop: 2696 },
  { _id: { state: 'OR', city: 'MEDICAL SPRINGS' }, pop: 10024 },
  { _id: { state: 'IL', city: 'ROYAL LAKES' }, pop: 844 },
  { _id: { state: 'ND', city: 'CUMMINGS' }, pop: 286 },
  { _id: { state: 'AL', city: 'MARION' }, pop: 7284 },
  { _id: { state: 'PA', city: 'MINERAL POINT' }, pop: 420 }
]
Type "it" for more


~sort the results by population, highest first
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([{ $group: { _id: { state: "$state", city: "$city" }, 
...pop: { $sum: "$pop" } } }, { $sort:{pop:-1} }])
[
  { _id: { state: 'IL', city: 'CHICAGO' }, pop: 2452177 },
  { _id: { state: 'NY', city: 'BROOKLYN' }, pop: 2300504 },
  { _id: { state: 'CA', city: 'LOS ANGELES' }, pop: 2102295 },
  { _id: { state: 'TX', city: 'HOUSTON' }, pop: 2095918 },
  { _id: { state: 'PA', city: 'PHILADELPHIA' }, pop: 1610956 },
  { _id: { state: 'NY', city: 'NEW YORK' }, pop: 1476790 },
  { _id: { state: 'NY', city: 'BRONX' }, pop: 1209548 },
  { _id: { state: 'CA', city: 'SAN DIEGO' }, pop: 1049298 },
  { _id: { state: 'MI', city: 'DETROIT' }, pop: 963243 },
  { _id: { state: 'TX', city: 'DALLAS' }, pop: 940191 },
  { _id: { state: 'AZ', city: 'PHOENIX' }, pop: 890853 },
  { _id: { state: 'FL', city: 'MIAMI' }, pop: 825232 },
  { _id: { state: 'CA', city: 'SAN JOSE' }, pop: 816653 },
  { _id: { state: 'TX', city: 'SAN ANTONIO' }, pop: 811792 },
  { _id: { state: 'MD', city: 'BALTIMORE' }, pop: 733081 },
  { _id: { state: 'CA', city: 'SAN FRANCISCO' }, pop: 723993 },
  { _id: { state: 'TN', city: 'MEMPHIS' }, pop: 632837 },
  { _id: { state: 'CA', city: 'SACRAMENTO' }, pop: 628279 },
  { _id: { state: 'FL', city: 'JACKSONVILLE' }, pop: 610160 },
  { _id: { state: 'GA', city: 'ATLANTA' }, pop: 609591 }
]
Type "it" for more


~limit the results to just the first 3 results. What are the top 3 cities in population?
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([{ $group: { _id: { state: "$state", city: "$city" }, 
...pop: { $sum: "$pop" } } }, { $sort:{pop:-1} },{$limit:3}])
[
  { _id: { state: 'IL', city: 'CHICAGO' }, pop: 2452177 },
  { _id: { state: 'NY', city: 'BROOKLYN' }, pop: 2300504 },
  { _id: { state: 'CA', city: 'LOS ANGELES' }, pop: 2102295 }
]
~What are the top 3 cities in population in Texas?

                         Bonus


~Write a query to get the average city population for each state.
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate( [
...    { $group: { _id: { state: "$state", city: "$city" }, pop: { $sum: "$pop" } } },
...    { $group: { _id: "$_id.state", avgCityPop: { $avg: "$pop" } } }
... ] )
[
  { _id: 'NV', avgCityPop: 18209.590909090908 },
  { _id: 'KS', avgCityPop: 3819.884259259259 },
  { _id: 'VT', avgCityPop: 2315.8765432098767 },
  { _id: 'WI', avgCityPop: 7323.00748502994 },
  { _id: 'TN', avgCityPop: 9656.350495049504 },
  { _id: 'KY', avgCityPop: 4767.164721141375 },
  { _id: 'AZ', avgCityPop: 20591.16853932584 },
  { _id: 'UT', avgCityPop: 9518.508287292818 },
  { _id: 'DE', avgCityPop: 14481.91304347826 },
  { _id: 'DC', avgCityPop: 303450 },
  { _id: 'SD', avgCityPop: 1839.6746031746031 },
  { _id: 'IN', avgCityPop: 9271.130434782608 },
  { _id: 'MI', avgCityPop: 12087.512353706112 },
  { _id: 'OK', avgCityPop: 6155.743639921722 },
  { _id: 'MD', avgCityPop: 12615.775725593667 },
  { _id: 'CT', avgCityPop: 14674.625 },
  { _id: 'RI', avgCityPop: 19292.653846153848 },
  { _id: 'WA', avgCityPop: 12258.670025188916 },
  { _id: 'MT', avgCityPop: 2593.987012987013 },
  { _id: 'AK', avgCityPop: 2976.4918032786886 }
]
Type "it" for more
~What are the top 3 states in terms of average city population?
Atlas atlas-awkq71-shard-0 [primary] population> db.zipcodes.aggregate([ 
...{ $group: { _id: { state: "$state", city: "$city" }, pop: { $sum: "$pop" } } }, 
...{ $group: { _id: "$_id.state", avgCityPop: { $avg: "$pop" } } },
...{$sort:{avgCityPop:-1}}, {$limit:3}])
[
  { _id: 'DC', avgCityPop: 303450 },
  { _id: 'CA', avgCityPop: 27756.42723880597 },
  { _id: 'FL', avgCityPop: 27400.958963282937 }
]




assginment 3
1. Write a MongoDB query to display all the documents in the collection Adresses.
      db.Adresses.find();
2. Write a MongoDB query to display the fields restaurant_id, name, borough and cuisine for all the documents in the collection restaurant.
    db.Adresses.find({},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1});

3. Write a MongoDB query to display the fields restaurant_id, name, borough and cuisine, but exclude the field _id for all the documents in the collection restaurant.
db.Adresses.find({},{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1,"_id":0});

4. Write a MongoDB query to display the fields restaurant_id, name, borough and zip code, but exclude the field _id for all the documents in the collection restaurant.
db.Adresses.find({},{"restaurant_id" : 1,"name":1,"borough":1,"address.zipcode" :1,"_id":0});


5. Write a MongoDB query to display the first 5 restaurant which is in the borough Bronx.
db.Adresses.find({"borough": "Bronx"}).limit(5);


6. Write a MongoDB query to display all the restaurant which is in the borough Bronx.

7. Write a MongoDB query to display the next 5 restaurants after skipping first 5 which are in the borough Bronx.
 db.Adresses.find({"borough": "Bronx"}).skip(5).limit(5);


8. Write a MongoDB query to find the restaurants who achieved a score more than 90.
   db.Adresses.find({grades : { $elemMatch:{"score":{$gt : 90}}}});

9. Write a MongoDB query to find the restaurants that achieved a score, more than 80 but less than 100.
db.Adresses.find({grades : { $elemMatch:{"score":{$gt : 80 , $lt :100}}}});

10. Write a MongoDB query to find the restaurants which locate in latitude value less than -95.754168.
   db.Adresses.find({"address.coord" : {$lt : -95.754168}});

11. Write a MongoDB query to find the restaurants that do not prepare any cuisine of 'American' and their grade score more than 70 and latitude less than -65.754168.
db.Adresses.find(
               {$and:
                    [
                       {"cuisine" : {$ne :"American "}},
                       {"grades.score" : {$gt : 70}},
                       {"address.coord" : {$lt : -65.754168}}
                    ]
                }
                    );


12. Write a MongoDB query to find the restaurants which do not prepare any cuisine of 'American' and achieved a score more than 70 and located in the longitude less than -65.754168.
db.Adresses.find(
                           {
                             "cuisine" : {$ne : "American "},
                             "grades.score" :{$gt: 70},
                             "address.coord" : {$lt : -65.754168}
                            }
                     );


13. Write a MongoDB query to find the restaurants which do not prepare any cuisine of 'American ' and achieved a grade point 'A' not belongs to the borough Brooklyn. The document must be displayed according to the cuisine in descending order.
         db.Adresses.find( {
                             "cuisine" : {$ne : "American "},
                             "grades.grade" :"A",
                             "borough": {$ne : "Brooklyn"}
                       } 
                    ).sort({"cuisine":-1});

14. Write a MongoDB query to find the restaurant Id, name, borough and cuisine for those restaurants which contain 'Wil' as first three letters for its name.
db.Adresses.find(
{name: /^Wil/},
{
"restaurant_id" : 1,
"name":1,"borough":1,
"cuisine" :1
}
);

15. Write a MongoDB query to find the restaurant Id, name, borough and cuisine for those restaurants which contain 'ces' as last three letters for its name.
db.Adresses.find(
{name: /ces$/},
{
"restaurant_id" : 1,
"name":1,"borough":1,
"cuisine" :1
}
);

16. Write a MongoDB query to find the restaurant Id, name, borough and cuisine for those restaurants which contain 'Reg' as three letters somewhere in its name.
db.Adresses.find(
{"name": /.*Reg.*/},
{
"restaurant_id" : 1,
"name":1,"borough":1,
"cuisine" :1
}
);

17. Write a MongoDB query to find the restaurants which belong to the borough Bronx and prepared either American or Chinese dish.
 db.Adresses.find(
{ 
"borough": "Bronx" , 
$or : [
{ "cuisine" : "American " },
{ "cuisine" : "Chinese" }
] 
} 
);

18. Write a MongoDB query to find the restaurant Id, name, borough and cuisine for those restaurants which belong to the borough Staten Island or Queens or Bronxor Brooklyn.
 db.Adresses.find(
{"borough" :{$in :["Staten Island","Queens","Bronx","Brooklyn"]}},
{
"restaurant_id" : 1,
"name":1,"borough":1,
"cuisine" :1
}
);

19. Write a MongoDB query to find the restaurant Id, name, borough and cuisine for those restaurants which are not belonging to the borough Staten Island or Queens or Bronxor Brooklyn.
db.Adresses.find(
{"borough" :{$nin :["Staten Island","Queens","Bronx","Brooklyn"]}},
{
"restaurant_id" : 1,
"name":1,"borough":1,
"cuisine" :1
}
);

20. Write a MongoDB query to find the restaurant Id, name, borough and cuisine for those restaurants which achieved a score which is not more than 10.
  db.Adresses.find(
{"grades.score" : 
{ $not: 
{$gt : 10}
}
},
{
"restaurant_id" : 1,
"name":1,"borough":1,
"cuisine" :1
}
);

21. Write a MongoDB query to find the restaurant Id, name, borough and cuisine for those restaurants which prepared dish except 'American' and 'Chinees' or restaurant's name begins with letter 'Wil'.
           db.Adresses.find(
{$or: [
  {name: /^Wil/}, 
  {"$and": [
       {"cuisine" : {$ne :"American "}}, 
       {"cuisine" : {$ne :"Chinees"}}
   ]}
]}
,{"restaurant_id" : 1,"name":1,"borough":1,"cuisine" :1}
);

22. Write a MongoDB query to find the restaurant Id, name, and grades for those restaurants which achieved a grade of "A" and scored 11 on an ISODate "2014-08-11T00:00:00Z" among many of survey dates..
     db.Adresses.find( 
                {
                 "grades.date": ISODate("2014-08-11T00:00:00Z"), 
                 "grades.grade":"A" , 
                 "grades.score" : 11
                }, 
                {"restaurant_id" : 1,"name":1,"grades":1}
             );

23. Write a MongoDB query to find the restaurant Id, name and grades for those restaurants where the 2nd element of grades array contains a grade of "A" and score 9 on an ISODate "2014-08-11T00:00:00Z"
   db.Adresses.find( 
                      { "grades.1.date": ISODate("2014-08-11T00:00:00Z"), 
                        "grades.1.grade":"A" , 
                        "grades.1.score" : 9
                      }, 
                       {"restaurant_id" : 1,"name":1,"grades":1}
                   );

24. Write a MongoDB query to find the restaurant Id, name, address and geographical location for those restaurants where 2nd element of coord array contains a value which is more than 42 and upto 52..
         db.Adresses.find( 
                      { 
                        "address.coord.1": {$gt : 42, $lte : 52}
                      },
                        {"restaurant_id" : 1,"name":1,"address":1,"coord":1}
                   );

25. Write a MongoDB query to arrange the name of the restaurants in ascending order along with all the columns.
db.Adresses.find().sort({"name":1});


26. Write a MongoDB query to arrange the name of the restaurants in descending along with all the columns.db.Adresses.find().sort(
                          {"name":-1}
                          );

           
27. Write a MongoDB query to arranged the name of the cuisine in ascending order and for that same cuisine borough should be in descending order.
 db.restaurants.find().sort(
                           {"cuisine":1,"borough" : -1,}
                          );

28. Write a MongoDB query to know whether all the addresses contains the street or not.
db.Adresses.find(
                     {"address.street" : 
                         { $exists : true } 
                     } 
                   );

29. Write a MongoDB query which will select all documents in the restaurants collection where the coord field value is Double.
db.Adresses.find(
                    {"address.coord" : 
                       {$type : 1}
                    }
                   );


30. Write a MongoDB query which will select the restaurant Id, name and grades for those restaurants which returns 0 as a remainder after dividing the score by 7.
               db.Adresses.find(
                      {"grades.score" :
                         {$mod : [7,0]}
                      },
                         {"restaurant_id" : 1,"name":1,"grades":1}
                    );

31. Write a MongoDB query to find the restaurant name, borough, longitude and attitude and cuisine for those restaurants which contains 'mon' as three letters somewhere in its name.
      db.Adresses.find(
                   { name : 
                     { $regex : "mon.*", $options: "i" } 
                   },
                       {
                         "name":1,
                         "borough":1,
                         "address.coord":1,
                         "cuisine" :1
                        }
                   );

32. Write a MongoDB query to find the restaurant name, borough, longitude and latitude and cuisine for those restaurants which contain 'Mad' as first three letters of its name.
   db.Adresses.find(
                   { name : 
                     { $regex : /^Mad/i, } 
                   },  
                       {
                         "name":1,
                         "borough":1,
                         "address.coord":1,
                         "cuisine" :1
                        }
                   );
