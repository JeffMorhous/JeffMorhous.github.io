---
layout: post
title:  "Start a New Application with Vue.js and Vuetify"
author: jeff
categories: [ Tutorial ]
image: https://miro.medium.com/max/4800/1*WCgrmLE6o2L-X9eri4Pwyw.png
---

[**Vue.js**](https://vuejs.org/v2/guide/)  is an open source JavaScript framework created and maintained by a vibrant and passionate community. Although it’s  _relatively_ new to the web apps world, Vue is quickly gaining ground on the more popular alternatives, React and Angular.

While remarkably useful, Vue.js by itself isn’t necessarily pretty. Sure, we could build out all the components we need, customizing CSS to fit our design patterns, but there’s a far easier way.  [**Vuetify**](https://vuetifyjs.com/en/)  is a component framework that follows Material Design concepts. In short, it’s a massive UI library that plays really nicely with Vue. Things like forms, buttons, app bars, and even spinners can be used almost instantly, accelerating our front-end labor to an unbelievable pace. Beyond this, it all but ensures we’re following a consistent design pattern, which boosts our user experience!

Now, let’s get down to it.

----------

## Step 0 (optional): Version Control 💪

It’s always a good idea to start version control when you start your project. Head over to github.com and create a new repository with whatever name you want. Click the “Initialize this repository with a README” button, then hit “Create Repository”

![](https://miro.medium.com/max/60/1*aE4NJYbzLbjyh1wLBaQLcw.png?q=20)

![](https://miro.medium.com/max/3616/1*aE4NJYbzLbjyh1wLBaQLcw.png)

Creating a new repository on Github

Next clone your repo either via SSH or HTTP from the command line with

    $ git clone <the-link-github-provides>

In your terminal, move into the directory that just got cloned with

    $ cd <my-repo-name>

If you’re not familiar with git and want to be,  [“Git-it” is a wonderful tutorial](http://jlord.us/git-it/)  that runs you through most everything you’ll need to get started.

## Step 1: Install Vue Cli

Vue CLI (command line interface) is by far the fastest and easiest way to create the scaffolding needed for a Vue.js project.

There’s some  [documentation on installing it here](https://cli.vuejs.org/guide/installation.html), but if you have npm installed already, it’s as simple as running the following in our terminal

    $ npm install -g @vue/cli

## Step 2: Create Vue Project

Now that we have the command line interface installed, to create a new project, we just need to run the following in the command line.

    $ vue create my-app

You should replace “my-app” with your desired app name of course! You’ll be prompted for some customization options here, but I’ve always been happy with the defaults.

![](https://miro.medium.com/max/60/1*lQVstwloZEP6oT1BOLqS6Q.png?q=20)

![](https://miro.medium.com/max/4124/1*lQVstwloZEP6oT1BOLqS6Q.png)


Fire up your code editor of choice. For most things,  [I use VS code](https://code.visualstudio.com/). It’s lightweight and incredibly customizable, not to mention free, perfect for Vue.js development.

You now have a functional Vue.js app created! This is a great place to commit 😃

## Step 3: Add Vuetify 🔮

Move your working directory into the app that was just created with (of course, replace my-app with the name you gave the  _vue create_  command)

    $ cd my-app

Then, we can set up our app to use Vuetify by simply running the following command

    $ vue add vuetify

To see your new beautiful web app, run the start script (either yarn serve or npm run dev) and view it in your browser!

Just like the command line tool recommends, this is a great place to commit your changes

## Step 4 and Beyond: Adding Components and Customization

Now that you have Vuetify hooked up to Vue, adding crazy complex and appealing components is as easy as one liners. Go through the documentation and see what components might be useful to you. Take a look at the resources below to see what you can do. Actually getting components to do things is more of a Vue.js skill, so their docs and various tutorials will be helpful to you.

----------

## Resources 🧐

[The Vue.js Website and Docs](https://vuejs.org/v2/guide/)

[The Vuetify Website and Docs](https://vuetifyjs.com/en/)

[Git-it Tutorial](http://jlord.us/git-it/)

---------
If you liked this, you might like to get updates from me when I write or make something new. I promise I won't spam you, and you can unsubscribe anytime. <a href="https://www.getrevue.co/profile/jeffmorhous">Sign up here.</a>