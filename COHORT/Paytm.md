
# 1.
allow user to sign up 
allow user to sign in 
allow user to update information (first name ,last name,password)

create a db.js file 
import mongoose and connect to the database 
create mongose schema for the usertable 
export mongoose model from the file to call it to user



solution :

```
const mongoose = require('mongoose');

// database connection

mongoose.connect("mongodb+srv://nikhilachale:h5cEFEH1DBem4DLF@nikhillearn.8tlde.mongodb.net/")

.then(() => console.log("MongoDB Connected"))

.catch(err => console.log("MongoDB Connection Error:", err));

  

const userSchema = new mongoose.Schema({

fname: {String,required:true,unique:true,maxlength:15},

fname: {String,required:true,maxlength:15},

lname: {String,required:true,maxlength:15},

password: {String,required:true,minlength:6},

  

})

  

const User = mongoose.model('Review', userSchema);

  

module.exports = {User};
```

# 2
creating routing file structure

create new file that exports new express router index.js


import the router in index.js 
```
const express = require('express');

const mainRouter=require('./routes/index');

const app=express();

  

app.use(express.json());

app.use ("api/v1",mainRouter)

```

```
const express = require('express');

  

const router=express.Router();

  

module.exports = router;

```


# 3
Route user request 

Create a new user router 
user.js in routes and route all request to /api/vq/user to the user router


and  

import the router in the index.js and route all the request from api/v1




# 4 
add cors body parser and jsonwebtokens




how do you do transactions in a mongodb 

using session
create sessions 

