npm i express node-fetch redis redis-cli

npm i -D nodemon


const express = require('express');
const fetch = require('node-fetch');
const redis = require('redis');

const PORT = process.env.PORT || 5000;
const REDIS_PORT = process.env.PORT || 6379;

const client = redis.createClient(REDIS_PORT);

const app = express();

function setResponse(username, repos){
	return '<h2> ${username} has ${repos} gitHUb <h1>'
}

async function getRepos(req, res){
	try {
    const { username } = req.params;
    const response = await fetch('link pro back/users/${username}');
    const data = await response.json();
    const repos = data.public_repos;
    
    client.setex(username,  3600, repos)
    res.send(setResponse(username, repos)):
    
    } catch (err){
    	console.error(err);
        res.status(500)
    }
}

app.get('/repos/:username', getRepos);

app.listen(5000, () => {
	console.log('App listeming on port ${PORT}');
});
  
  -------------- CODIGO DA AULA -----------------
  
npm i express node-fetch redis redis-cli

npm i -D nodemon
  
.env  
MONGO_URI = mongodb://localhost:27017
REDIS_HOST=localhost
REDIS_PORT=6379
REDIS_URL=redis://localhost:6379

  
Import express from "express";
import axios from "axios";
import cors from "cors";
import { createClient } from "redis"; // db.js
import dotenv from "dotenv";
dotenv.config(); // 'dotenv-expand'

const app = express();
app.use(cors());

export const redis = createClient({ // db.js
  url: process.env.REDIS_URL
});

await redis.connect(); // db.js
  
const EXPIRATION = 3600; // seconds // db.js

app.get("/photos", async (req, res) => {
  const albumId = req.query.albumId;
  const cacheKey = albumId ? `photos?albumId=${albumId}` : "photos";
  try {
    const cachedPhotos = await redis.get(cacheKey);
    if(cachedPhotos) {
      res.send(JSON.parse(cachedPhotos));
    } else {
      const { data } = await axios.get(`${URL}/photos`, { params: {albumId} });
      redis.setEx(cacheKey, EXPIRATION, JSON.stringify(data));
      res.send(data);
    }
  } catch (error) {
    console.log(error);
    res.sendStatus(500);
  }
});

const port = process.env.PORT || 5000;
app.listen(port, () => {
  console.log(`Server is up and running on port ${port}`);
})