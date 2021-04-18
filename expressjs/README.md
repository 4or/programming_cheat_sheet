![expressjs](https://camo.githubusercontent.com/0566752248b4b31b2c4bdc583404e41066bd0b6726f310b73e1140deefcc31ac/68747470733a2f2f692e636c6f756475702e636f6d2f7a6659366c4c376546612d3330303078333030302e706e67)
## ExpressJS Cheat Sheet for quick learning
---


&nbsp;
<p style="text-align: center">by the end of this page you will get to know about expressjs  <font color="02ddff"> this page write with expressjs version 5.x</font>
</p>

`thanks for everyone around the world for sharing information and help other to learn and be part of this awesome family` 

[![Linkedin](https://i.stack.imgur.com/gVE0j.png) Follow Me ](https://www.linkedin.com/in/ahmed-bejaoui-75b57318a?trk=people-guest_people_search-card)
  


# let's start learning

## install expressjs <br> 
 ```sh
  npm install express --save
 ```


## import expressjs and say hello world

```javascript

const express = require("express")
const app = express()

app.get("/",function(req,res){
    res.send("Hola world ");
})

app.listen(3000,()=>{
    console.log("server is running on port 3000")
})

```

> now try : curl localhost:3000




## express GET, POST, DELETE, PUT, ALL Method 
```javascript

// this will match any HTTP GET request that will hit /user
app.get("/user",function(req,res){
    res.send("GET request");
})


```

```javascript 
// this will match any POST request that will hit /add_user
app.post("/add_user",function(req,res){
    res.send("POST request");
}) 

```
```javascript 
// this will math any DELETE request that will hit /remove_user
app.delete("/remove_user",function(req,res){
    res.send("delete request");
}) 
```
```javascript
// this will match any PUT reqiest to /
app.put('/', function (req, res) {
  res.send('PUT request to homepage')
})

```
```javascript 

// this will math all method that hit  /api
app.all("/api",function(req,res,next){
    console.log("access all methods")
    next()
}) 

```

```javascript 

// here we open expressjs server to listen to port and we can add callback function 
app.listen(3000,()=>{
    console.log("server is running on port 3000")
})

```


---

## using app.SET()

```javascript
app.set("company","AWS")
app.get("company") // this will return to you AWS

// we can set the template engine that we want to use using app.set()
app.set('view engine', 'pug')
``` 


---
# in the next section we are working with the res ( response ) from the http request
## using res.send()  

```javascript
// The res object represents the HTTP response that an Express app sends when it gets an HTTP reques
app.get('/', function (req, res) {
  res.send("Hello from the other side of the moon")
});
```
## using res.json()  

```javascript
// this will send to the user data as json format
app.get('/', function (req, res) {
  res.json({name:"spacex",year:2020})
}); 

```

## using res.location()  

```javascript
// this will set the location to /user in the response header
app.get('/', function (req, res) {
  res.location("/user")
}); 

```

## using res.redirect()  

```javascript
// this will redirect the user to /login
app.get('/', function (req, res) {
  res.redirect("/login")
}); 

```

## using res.status()  

```javascript
// return status code to the client
app.get('/', function (req, res) {
  res.status(403).end()
  // res.status(400).send('Bad Request')
}); 

```



# in the next section we are working with the req ( request ) 
## using req.params()  

```javascript
// send the id paramater back to the user
app.get('/user/:id', function (req, res) {
  res.send('user id = ' + req.params.id) 
  // when client call /user/2 the response will be => user id = 2
});
```
## using req.ip()  

```javascript
// this will print ip or the host
app.get('/', function (req, res) {
  console.log(req.ip) // 127.0.0.1
}); 

```

## using res.protocol()  

```javascript
// this will return the protocol that used to call this api [ HTTP, HTTPS]
app.get('/', function (req, res) {
  console.log(req.protocol())
}); 

```

## using req.subdomains()  

```javascript
// if it was called with domain "x.space.example.com" it will return array of subdomain
app.get('/', function (req, res) {
  console.log(req.subdomains) // => ['space','x']
}); 

```

 
## setting cookies and clear cookies
```javascript 
// response with USER cookies
res.cookie('USER', 'apollo', { domain: '.example.com', path: '/', secure: true, expires: new Date(Date.now() + 900000), httpOnly: true })

// clear cookie by name 
res.clearCookie('USER', { path: '/' })

```
