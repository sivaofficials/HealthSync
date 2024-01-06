# HealthSync

## index.js 
  The main file where the imports (requries) and routes deafult(express,body-parser,ejs,cookie-parser)

```
const express = require("express"); //express
const bodyParser = require("body-parser"); //body-parser 
const _ = require("lodash"); //formate
const axios = require("axios"); //api call
const { localsName } = require("ejs");
const fs = require("fs"); //filesystem 
const multer = require("multer"); //local data upload

const app = express(); //recreat app 
app.set("view engine", "ejs"); //ejs file view
app.use(express.static("public")); // static file where save css and js
app.use(bodyParser.urlencoded({ extended: true })); //parser

app.use(cookieParser());

app.set("view engine", "ejs");
app.use(express.static("public"));
app.use(bodyParser.urlencoded({ extended: true }));
```
## middle ware

```
const myLogger = function (req, res, next) {
  req.requestTime = req.socket.remoteAddress;
  // console.log('LOGGED')
  next();
};
app.use(myLogger);

```
## date function
```
exports.day= function (){
    var today = new Date();
    var options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
    var day = today.toLocaleDateString("en-US", options)
    return day
}
```
```

const date = require(__dirname + "/date.js");
```
## listen 
```

app.listen(port, function (req, res) {
  console.log("server is up");
});

```
## creat new post
```
app.get("/posts/:topic", (req, res) => {
  var test = _.lowerCase(req.params.topic);
  gobal_topic = test;
  kimgs = getpic(gobal_topic);
  posts.forEach((post) => {
    if (test === _.lowerCase(post.fname)) {
      res.render("content", {
        title: post.fname,
        twitter: post.uname,
        instagram: post.instagram,
        city: post.city,
        rel: post.rel,
        Profile: post.Profile,
        gender: post.gender,
        phone: post.phone,
        email: post.email,
        address: post.address,
        status: post.status,
        facebook: post.facebook,
        descretion: post.descretion,
        bg: bg,
        Profile: post.filename,
        album: kimgs,
      });
    }
  });
```


  
