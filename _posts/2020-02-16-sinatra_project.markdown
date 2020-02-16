---
layout: post
title:      "Sinatra Project"
date:       2020-02-16 20:29:44 +0000
permalink:  sinatra_project
---

This project in general was a bit duplicitous in nature to myself. Because it appears at first to be fairly straightforward as I quickly learned routing may not always logically occur the way you would expect. As I was building out controllers based on single purpose paradigm I realized how convoluted or miscontrued a path could be based on the interaction you may want. For instance I initally thought since I only wanted the ability to edit an object to only be possible by the creator of that object I would want to nest the ability to do so in  routes that are directly under the purview of the current user to make it simple. But as I kept going I realized I still need users to be able to view all work only object owners should be able to edit. So my initial design flow was a bit flawed. This is where I believe pair programming and working with other cohort members really assisted me hearing their suggestions and them explaining how they solved a problem was very enlightening due to the fact that it gave me a new perspective to use. As I was chugging along I came to understand that Creating and Reading objects was the fairly simple part of the process. Updating and Deleting could have some very real and odd interactions when not executed correctly. At one point I had Users being able to delete other's individuals objects and not their own.
