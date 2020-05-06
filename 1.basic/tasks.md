#### write commands for following mongodb opertaions

1. create a database named `sports`

use sports

2. list all databases present in local mongod server.

show dbs

3. create 3 collections named `cricket`, `football`, `TT` in sports database.

db.createCollection('cricket')
db.createCollection('football')
db.createCollection('TT')

4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.

db.cricket.insert({name : "Ashish", age : 24, email : "ashish@gmail.com"})
db.cricket.insert({name : "Stark", age : 28, email : "stark@gmail.com"})
db.cricket.insert({name : "Arya", age : 22, email : "arya@gmail.com"})

db.football.insert({name : "Pablo", age : 22, email : "pablo@gmail.com"})
db.football.insert({name : "Kehlani", age : 22, email : "kehlani@gmail.com"})
db.football.insert({name : "Max", age : 19, email : "max@gmail.com"})

db.TT.insert({name : "Right", age : 22,  email : "right@gmail.com"})
db.TT.insert({name : "Sg", age : 25,  email : "sg@gmail.com"})
db.TT.insert({name : "Ashish", age : 24,  email : "ashish@gmail.com"})

5. list all collections in sports database.

show collections

6. rename `TT` collection to `tennis`.

db.TT.renameCollection('tennis',true)

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

db.createCollection('khokho',{capped : true, size : 1000000, max : 3})

8. check whether a collection is capped or not?

db.collection.isCapped('khokho')

9. remove all documents from `football` collection.

db.football.remove({})

10. delete cricket collection completely.

db.cricket.drop()

11. rename database sports to games

db.copyDatabase('sports','games','localhost')

12. delete sports database. 

use sports
db.dropDatabase()
