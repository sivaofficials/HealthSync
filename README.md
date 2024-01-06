# HealthSync

## index.js 
  The main file where the imports (requries) and routes deafult(express,body-parser,ejs,cookie-parser)

```
  const express = require("express");
const bodyParser = require("body-parser");
const app = express();
const { localsName, render } = require("ejs");
const fs = require("fs");
const multer = require("multer");
const cookieParser = require("cookie-parser");

app.use(cookieParser());

app.set("view engine", "ejs");
app.use(express.static("public"));
app.use(bodyParser.urlencoded({ extended: true }));
```

  
