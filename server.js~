
var express = require('express'); // call express
var app = express(); // define our app using express
var bodyParser = require('body-parser'); // get body-parser
var path = require('path');

// var morgan = require('morgan'); // used to see requests
var port = process.env.PORT || 8080; // set the port for our app

// APP CONFIGURATION ---------------------
// use body parser so we can grab information from POST requests
app.use(bodyParser.urlencoded({ extended: true }));


// configure our app to handle CORS requests
app.use(function(req, res, next) {
res.setHeader('Access-Control-Allow-Origin', '*');
res.setHeader('Access-Control-Allow-Methods', 'GET, POST');
res.setHeader('Access-Control-Allow-Headers', 'X-Requested-With,content-type, \
Authorization');
next();
});

app.get('/:id' , function(req,res){

	var id = req.params.id;
	if(!isNaN(id)&& id > 0 && id<30)
	{
  		res.sendFile(path.join(__dirname + '/data/'+id+'.html'));		
	}
	else
	{
		res.send("err");
	}

});


app.listen(port);
console.log('Magic happens on port ' + port);
