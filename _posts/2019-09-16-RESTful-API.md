---
layout: post
title: "RESTful API"
subtitle: "RESTful API"
categories: Programming
tags: NodeJS
---

# **NodeJS** <br>

What is RESTful API?
* Based on HTTP Protocol
* Resource represent URI(Uniform Resource Identifiers) and should be "Unique"
* Simple URI
* We identify Resource status using HTTP Methods
* Send a data with xml/json

CRUD
Action to manage web resource through network.<br>
We have 4 HTTP methods (POST, GET, PUT, DELETE)
- Create (POST)
- Retrieve (GET)
- Update (PUT)
- Delete (DELETE)

API Design
- use a plural noun (e.g, /movies)
- if needed, mention sub-resouce to URL (/movies/23)
- you can also use filter condition (/movies?state=active)
 
Example <br>

|URL|Methods|Description|
|--------|--------|--------|
|/Movies|GET|get all movie list|
|/Movies|POST|add movie|
|/movies/:title|get|get title of the movie|
|/movies/:title|DELETE|delete title of the moive|
|/movies/:title|PUT|update title of the movie|
|/movies?min=9|GET|Movie list which is currently running|

