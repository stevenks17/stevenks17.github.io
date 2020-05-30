---
layout: post
title:      "React Redux (Life made easier by checkpoint saves for a Dev)"
date:       2020-05-30 15:50:28 +0000
permalink:  react_redux_life_made_easier_by_checkpoint_saves_for_a_dev
---


Working on my final project with React-Redux seemed very daunting at first mostly because I had a rudimentary understanding of alot of the concepts but Redux generally eluded me. I know it managed state because everything you google about it has the same exact keywords and phrases about it but I wasn't completely sure what it meant when state was being referenced. All of this kind of blew up once a friend of mine explained it to me like I was five. Simply put think of your app as a video game the redux global state as well as redux thunk's specific state in alot of ways is like a auto save or checkpoint in any standard action or adventure game you play. Its a current events version piled into a specific state of what you have accomplished or done up to that point. And you can have multiple states because states are just different tenses or specific versions of a redux application. You shelve these in the store and choose which state you would like to operate on as the underlying base or use it to start a template so you can fill out forms. 


The dawning of my eureka moment where I finally understood state really rounded out my doubts of why I'd want redux or even redux thunk. Having the store and the ability to just simply connect and pull as needed is great is makes an application much more dynamic and receptive. Redux-Thunk refines this process even more by allowing you to intercept  an action before dispatch to specifically adjust whats being dispatched down to the specific state of certain elements or objects within the global state you may have been working with. 

We are getting ahead of ourselves though we need to first set a basis of the concept of redux overall. To do this I'd like to first illustrate the general redux flow using a gif I found online that has been very helpful. Below is a Redux Flow Chart.

![Redux Flow Chart](https://res.cloudinary.com/practicaldev/image/fetch/s--m5BdPzhS--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_66%2Cw_880/https://i.imgur.com/riadAin.gif)



This chart is great because it highlights everything and the traversal of each working part and the manipulation of state that occurs. In the beginning your state is in the view after you prompt the use of the action creator the action is then sent off and can be intercepted by middelware in the case I used Redux Thunk so I will be highlighting its process here. So thunk can take an action prior to dispatch and alter what will be going to dispatch inevitably by allowing you to access the specific state for a certain variable or object. In my case thunk assisted me in intercepting and manipulating Notes and Questions so they could be added to an array and nested within my Graph Object. This way upon completion everything is neatly sent to the dispatch to then be reduced by the reducer. This may seem like a play on words but the reducer itself is pivotal to Redux's flow as the reducer is what will be determing the changes made to app state. It is at this point that redux relies on reducers to take previous state and actions  to execute the next state that will be created or stored. Finally we are back at the beginining as now that state as successfully be dispatched and reduced and now is a state that is shelved in the store to be accessed as needed. At first I believed that redux and thunk were alot more management then I needed as it seemed overkill. But through debugging and making changes constantly I realized while the training wheels come with alot of rules they do so to make my job alot easier as I do not have to know everything as state will have what I want I just need to browse and grab what I may want to show or use. I think the concept at play is to increase application scaleablilty in a larger application state becomes more pivotal as you are managing much more and storing far more. Simply put React was a common sense library made with very common practice implementation in mind. And redux was the icing on that cake to increase usability and flexibility because if you already did it once why not have the application do it for you the second time around?


