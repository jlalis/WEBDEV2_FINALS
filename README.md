# Final Activity 1

## Steps in Making Graph to Web Server
1. Initialize node repository ```npm init -y```
2. Install plotly dependency ```npm install --save plotly```
3. Draw your plot
```js
// VISUALIZATION 
// API KEY = SjNmN9IwRvkO9tysPHQc < - for .env
// https://plot.ly/nodejs/getting-started/ for nodejs

// 1. instantiate plotly
const plotly = require('plotly')("jlalis", "SjNmN9IwRvkO9tysPHQc")
//  2. data
const data = [
  {
    x: ["giraffes", "orangutans", "monkeys"],
    y: [20, 14, 23],
    type: "bar"
  }
];
console.log(data[0].type) // display bar
console.log(data[0].x[0]) // display giraffe
//  3. graph options (height,etc.)
var graphOptions = {filename: "lalis-basic-bar", fileopt: "overwrite"};
//  4. execute graph plot
plotly.plot(data, graphOptions, function (err, msg) {
    // console.log(msg);
    console.log(msg.url); // link
});

//WEB SERVER
const path = require('path') // npm install path
const express = require('express') //npm install express
const app = express()
app.get('/', function(req, res) {
    res.end('Hello World')
    // visualization
})
// app.listen(3000)
const PORT = process.env.PORT || 5000
app.listen(PORT)
console.log('Server is running on 192.168.202.83:3000')




```

<!-- ```bash
> npm init -y

``` -->

## Steps in Heroku
1. Install heroku https://devcenter.heroku.com/articles/getting-started-with-nodejs#set-up
2. cmd -> heroku login

## Steps to deploy heroku
1. Deploy to Heroku
``` js
# Install Heroku CLI
> heroku --version
> heroku login
Loggin in... done
Logged in as lalisit111@gmail.com
> heroku create jlalis
// NEEDED!!!!!!! .gitignore, app.js (const PORT), Procfile -> web: node app.js
Creating ⬢ jlalis... done
https://jlalis.herokuapp.com/ | https://git.heroku.com/jlalis.git
> git status
> git add .
> git commit -m ""
> git push heroku master
> heroku open
```
