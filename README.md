<h1 align="center">
  <br><a href="https://imgbb.com/"><img src="https://i.ibb.co/fppDbMx/Webp-net-resizeimage.jpg" alt="Webp-net-resizeimage" border="0"></a></a>
</h1>

# WATCHLIST

## Contents
- [Inroduction](#Introduction )
- [Features](#Key-Feautures)
- [Example](#Example )
- [Installation](#Installation)
- [Tools](#Built-With)
- [Usage](#Usage)
- [Contributing](#Contributing)
- [License](#License)


## Introduction

This is a simple MERN Apllication built on to display movies from a backend populated by a Moviedb API
## Key Feautures

### Back End
- [x] Emite Routes 
- [x] Protect Routes with Authenication middleware
- [x] Use of JSON Token 
- [x] Call API from MovieDB
- [x] Protected Routes
- [x] Comment on each Movie Detail

### Front End
- [x] User Login 
- [x] Consume backend API from NodeJS
- [x] Render movie content dynamically 
- [x] Filter Products Based on Company or category



## Example 



## Modules

## Back End

```js
const express = require("express");
// assign express to app
const app = express();
// route modules 
const jwt = require("jsonwebtoken");
const Joi = require("joi");
```

## Front End
Most modules are imported into react from the index.js file
```js
import React from 'react';
import ReactDOM from 'react-dom';
```
css module used are bootstrap 4 and font-awesome  
```js
import 'bootstrap/dist/css/bootstrap.css';
```

Semantic-ui is a css framework
```
npm install sematic-ui-react sematic-ui-css --save
```

## Events

## Back End
This are some route used in the backend

This route is to get all Movies 
```js
router.get("/", auth, async (req, res) => {
	
	res.json(JSON.parse(Movies));
});
```

Post a comment on a specific ID
```js
router.post("/:id/comment", (req, res) => {
	const { error } = validateComment(req.body);

	if (error) {
		res.status(400).send(error.details[0].message);
		return;
	}
	const { results } = JSON.parse(Movies);
	const movie = results.some(movie => movie.id === parseInt(req.params.id));
	if (!movie) return res.status(400).send("Invalid movie.");

	const newComment = {
		id: Comments.length,
		movieId: parseInt(req.body.movieId),
		comment: req.body.comment,
		userName: req.body.username,
		date: new Date(Date.now()).toLocaleString()
	};

	Comments.push(newComment);
	res.send(newComment);
});
```


## Front End
Consume movie API from backend
```js
const apiEndPoint = `${apiUrl}/movies`;

export function getMovies() {
	return http.get(apiEndPoint);
}
```

Comment on a specific movie 
```js
export function postComment(movieId, comment, username) {
	console.log(username);
	return http.post(`${apiEndPoint}/${movieId}/comment`, {
		movieId,
		comment,
		username
	});
}

### Frontend State
Main state is found in the product.jsx
```js
state = { movies: [] };
```
## Installation

Inside client and server folder
```bash
cd Client
npm install
npm start
```

```bash
cd Server
npm install
nodemon start
```

```
### Run with Docker
```console
cd Client
docker build -t watchlist_client .
```

```console
cd Server
docker build -t watchlist_server .
```

### Run with Docker-compose 
```console
docker-compose up --build
```


## After Installation 

Inside the config folder change setting

add a privatekey for jwt 
and your Moviedb Api Key https://www.themoviedb.org/documentation/api

```js

{
	"jwtPrivateKey": "",
	"requiresAuth": false,
	"moviedbApiKey": ""
}


```

## Built With


## Usage


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
MIT (c) 2018 [Ian Odhiambo](https://github.com/ianodad)

This section has moved here: https://facebook.github.io/create-react-app/docs/making-a-progressive-web-app

### Advanced Configuration



### Deployment



### `npm run build` fails to minify

