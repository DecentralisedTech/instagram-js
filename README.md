# Instagram-JS
A Instagram Automation Libary for NodeJS

## Installation


## Usage
Import the libary and create a new client object.
```js
    const InstagramJS = require('instagram-js')
    
    const client = new InstagramJS.Client()
```

## Client
* [client.init](#clientinitdev)
* [client.login](#clientloginusername-password)
* [client.close](#clientclose)
* [client.followerCount](#clientfollowercountaccount)
* [client.follow](#clientfollowusername)
* [client.unfollow](#clientunfollowusername)
* [client.comment](#clientcommentpost-message)
* [client.likePost](#clientlikepostpost)
* [client.unlikePost](#clientunlikepostpost)
* [client.post](#clientunlikepostpost)


### client.init([dev])
Creates a Chromium instance to emulate Instagram on mobile.
* ``dev`` <[bool]()> (Optional) If **true** is given the Chromium browser will be visable and not run in the hidden in the background

### client.login(username, password)
Logs into your Instagram account, this is required to perform actions that being signed in necessary.
* ``username`` <[string]()> Instagram account username
* ``password`` <[string]()> Instagram account password
* Returns <[Promise]()>

### client.close()
This will close the Chromium browser used for oporating Instagram, to reopen you will need to call [client.init()](#clientinitdev).
It is recommened to close when not in use in complex applications to free up memory.
* Returns <[Promise]()>

### client.followerCount(username)
Queries and returns the amount of followers an account has.
You do not need to be logged in to use this method.
* ``username`` <[string]()> Instagram account to query
* Returns <[Promise]()(<[int]()>)>

### client.follow(username)
Follows an Instagram account if the logged in account ins't already doing so.
* ``username`` <[string]()> Instagram account to follow

### client.unfollow(username)
Unfollows an Instagram account if the logged in account ins't already doing so.
* ``username`` <[string]()> Instagram account to unfollow
* Returns <[Promise]()>

### client.comment(post, message)
Comments a message on a specified Instagram post.
* ``post`` <[string]()> URL of the post to comment on
* ``message`` <[string]()> Message to comment
* Returns <[Promise]()>

### client.likePost(post)
Likes a specified Instagram post.
* ``post`` <[string]()> URL of the Instagram post to like
* Returns <[Promise]()>

### client.unlikePost(post)
UnLikes a specified Instagram post.
* ``post`` <[string]()> URL of the Instagram post to unlike
* Returns <[Promise]()>

### client.post(content[, comment])
Creates a post.
* ``content`` <[string]()> Dir of the image or video to upload
* ``comment`` <[string]()> Optional - Comment to of the post
* Returns <[Promise]()>