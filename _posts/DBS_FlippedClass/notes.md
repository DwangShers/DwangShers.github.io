### Demonstration of Test Data
This retrieves all the data of the player entity.
```Javascript
db.player.find()
```

### CRUD Queries Execution

#### Create
```Javascript
db.player.insertOne({
    "id": 20001,                   
    "name": "Player 20001",       
    "resource": {                  
        "gold": 950,
        "wood": 820,
        "stone": 200,
        "food": 600
    },
    "experience": 150,             
    "level": 9,                    
    "base_location": {            
        "x": 90,
        "y": 70
    }
});
```
#### Read
```Javascript
db.player.findOne({"id": 20001})
```
#### Update
```Javascript
This code updates the players data.
db.player.updateOne(
    { "id": 20001 },
    {
        $inc: {
            "resources.gold": 100,
            "resources.stone": 50
            "resources.wood": 150,
            "resources.food": 200
        },
        $set: {
            lastUpdated: new Date()
        }
    }
);
```
```Javascript
db.player.updateOne(
    { "id": 20001 },
    {
        $inc: {
            "resources.gold": -100,
            "resources.stone": -50
            "resources.wood": -150,
            "resources.food": -200
        },
        $set: {
            lastUpdated: new Date()
        }
    }
);
```

#### Delete
To delete the inserted data, we can;
```Javascript
db.player.deleteOne({ "id": 20001 });
```