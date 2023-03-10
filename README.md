

<div align="left">

#  JustReleased

<p align="left">

JustReleased is an API made to give useful information about movies and video games that have or are about to release!

<a href="https://github.com/github_username/repo_name"></a>
<!-- TABLE OF CONTENTS -->

<details>

<summary align="left">

## Table of Contents

</summary>

<ol>

<li align="left">
<a href="#about-the-project">About The Project</a>
<ul>
<li align="left"><a href="#built-with">Built With</a></li>
<li align="left"><a href="#the-data">The Data</a></li>

</ul>

</li>


<li align="left"><a href="#how-to-use">How to Use</a></li>

<li align="left"><a href="#api-documentation">API Documentation</a></li>

<li align="left"><a href="#examples">Examples</a></li>




</ol>

</details>

<!-- ABOUT THE PROJECT -->

##  About The Project
### Motivation
<p align="left">
I created JustReleased to learn more about hosting backend applications, specifically through a Linux vps, and leveraging Express.js and a Postgres DB. The API is hosted on an ubuntu droplet with DigitalOcean. 
	
### The Data
	
<p align="left">The movie and videogame data is taken from the <a href="https://imdb-api.com/api">IMDB API</a> and the <a href="https://api-docs.igdb.com/#about">IGDB API</a> respectively. The data is updated on a monthly basis automatically.</p>
<p/>

###  Built With:
<div align="left">
	
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)

![NodeJS](https://img.shields.io/badge/node.js-6DA55F?style=for-the-badge&logo=node.js&logoColor=white)

![Express.js](https://img.shields.io/badge/express.js-%23404d59.svg?style=for-the-badge&logo=express&logoColor=%2361DAFB)

![DigitalOcean](https://img.shields.io/badge/DigitalOcean-%230167ff.svg?style=for-the-badge&logo=digitalOcean&logoColor=white)

![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)


## How to Use 



<p align="left">Simply visit <a href=http://67.207.92.253:5000/>the base URL</a> to get started!</p>

Visit the [API Documentation](#api-documentation) for the available endpoints and [Examples](#examples) on how to use them.



## API Documentation 



All responses have the following JSON structure:
```JSON
    {
        "id": "The integer id of the release",
        "type": "The Type of release (vg = video game, mv = movie)",
        "title": "The title of the release.",
        "description": "The description of the release.",
        "image": "The cover image of the release.",
        "url": "The url to a releases corresponding igdb profile (video game) or imdb page (movie)",
        "follows": "The amount of follows the release has",
        "release_date": "The release date",
        "created": "The timestamp of creation in the database.",
        "last_updated": "The timestamp of last update in the database."
    }
```
### GET 


#### All Releases

`GET /releases/`

#### All Releases

`GET /releases/`

#### Release by ID

`GET /releases/:id/`

#### Releases by type

`GET /releases/:type/`

#### Upcoming Releases

`GET /releases/upcoming/`

#### Recent Releases

`GET /releases/recentlyreleased/`


##  Examples



GET - All releases
```javascript
axios.get(`http://67.207.92.253:5000/releases`)
	.then(res  => {
		const  data  =  res.data;
		console.log(data);
})
```
GET - Releases by type
```javascript
// releases types:
// movie = 'mv' 
// videogame = 'vg'
axios.get(`http://67.207.92.253:5000/releases/type/:type`)
	.then(res  => {
		const  data  =  res.data;
		console.log(data);
})
```

Visit the [API Documentation](#api-documentation) for more information on the available endpoints.

<p align="right">(<a href="#justreleased">back to top</a>)</p>
