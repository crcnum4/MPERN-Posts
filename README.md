# MPERN Posts

## Purpose

<p>This repo is part of a larger project related to a Blog application using a MPERN Microservice Architecture for the bigger picture please refer to the main [repo](https://github.com/crcnum4/MPERN-MS)</p>

## Service Details

<p>This service in in charge of maintaining the posts collection in the Mongo database. The service will allow for the creation of posts and the access to posts.</p>

### Front End Capabilities

<p>The react system will work with the gateway for the following capabilities:</p>
<p>
- Create new posts<br />
- Get a list of posts<br />
- Get a list of posts based on certain criteria<br />
- Get the details behind a specific post<br />
- Update an existing post<br />
- Delete a post
</p>

### interaction with other services.

<p>Non logged in users can look up posts and get limited details for each post. Only logged in users can add posts as well as update and edit their own posts. The posts microservice will communicate with the Authentication microservice to validate authentication keys and get the user information to validate if the user can post (and who owns the post) as well as to confirm if the requester has the right to edit or delete a post</p>
<p>Service will work with the comments and raiting service to collect the comments and ratings for specific posts</p>

#### Why are the comments and ratings managed by a different Service but on the same database?

<p>The goal of this seperation is to ensure that if something goes wrong with either the ratings or the comments users are still able to view and watch posts. This also allows the Posts screen to pull just the post data without having to worry about the comments and raitings.</p>

## Usage

### Configuration

<p>System uses a Mongo noSql database for maintaining the posts collection. To connect to database you will need to configure the config folder with a default.js file. (see below)

### config/default.js

<p>Private keys are stored in a gitignored file. This file is called default.js and should be stored in a config folder. Refer to the defaultExample.js file on how to build the default.js file.</p>
