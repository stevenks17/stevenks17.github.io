---
layout: post
title:      " User Persistence and Security"
date:       2020-02-22 12:31:05 -0500
permalink:  user_persistence_and_security
---


This blog will be going over the specific technical aspects of the interactions that occur when a user logs in and out and how the persistence is achieved via session cookies. The ability to login into a website is a means to store data specific to the user.  Simply logging in already uses a robust set of commands for its completion as this will have to check a database to compare user credentials authenticate them which is done during the post request in a controller to send data. Once done the site can then render a specific view for the user depending on the website.HTTP by design is a stateless protocol because of this persistence would have to happen another way. The solution was found in cookies. A cookie is a simple text based file that stores three items which are: server name, cookie lifetime and a randomly generated unique number to identify the cookie by. A key factor in all this is that persistence via cookie and session is best left to a session variable as utilizing a instance variable can have the side effect of only being persisted while the specific object instance is alive. A very normal process that can occur that would terminate the instance would be once deployed, many systems by design will enter a dormant or idle state when not in use or re-start as needed. During that time you can have multiple users making the same request as the server is now spinning up you have users fighting for the same request but stored within a instance variable which will make this a very messy flow.


# Cookie
Moving on, visiting a website for the first time the transaction of generating a cookie will be requested should the user permit it. Once the cookie is successfully created and downloaded into a directory for your browser it will be accessed each time you visit the website going forward. Each time you visit the server will check in with the cookie you were given and will specifically read the contents to be used as it completes each browser request. This is a means to identify you and dynamically have the website access views and pages specific to the user. This cookie only ever has value to the server that had it created as it is a unique pairing. Because of the information detailed above cookies themselves are anonymous as they do not keep any user specific information whereas it is a saved list of site specific preferences that are adjusted for the user.


# Authentication

To begin with to authenticate a user the gem bcrypt is used. The bcrypt algorithm salts and hashes passwords this process is by design meant to be slow as to limit possible methods to obtain or otherwise crack the security being used to hide personal data. Bcrypt lends us other methods to achieve this one being uniqueness to allow only one specific value to ever be associated and never have a duplicate or simply the presence of a username and password needed to move forward with the login process. This is also where has_secure_password is used as it will compare the salted and hashed password digest to the input recieved. The actual password is never checked in this compare as the identifier is the hash that will not change unless the password itself changes. So to understand the security of the process understanding what "Hashing a password" is will be important. Hashing is the act of taking in the password and utilizing an algorithm to encrypt the string this encryption uses 192 bits to encode with the "OrpheanBeholderScryDoubt"  cypher after this part is done the next process is to now take the 192 bit encrypted value and encrypt that value 64 times using "eksblowfish" cypher. To view the process programmically a snippet is provided below. The key concern becomes finding the most efficient split for production where the maximum security is upheld without affecting the usability of the website.

![](https://cdn.auth0.com/blog/intro-bcrypt/bcrypt-algo.png)

# Final Thoughts
Overall persistence and security are both important objectives that need to be constantly monitored and revised to better both the user's experience and security while accessing a website. There is a constant tightrope of maintaing maximum security while also not diluting or otherwise hampering the workflow a user may be used to in the timely manner they have come to expect when accessing the website.


