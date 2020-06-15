---
layout: post
title: "How to structure reactjs project."
date: 2020-12-30
dateString: "2019 December 31"
categories: technical
image: /assets/images/reactjs-structure/react-redux.png
thumbnail-image: /assets/images/reactjs-structure/react-redux.png
summary: ""
---
### Table of contents
1. Why?
2. Enviroment
3. How?
4. Summary

### Why I should read this post?

One of the great things about ReactJS is the flexibility. You can structure your web as you want. This is great but can also be problem when you choose the architecture for your web, especially to new developers.

This post will show you how can I structure my web.

### The list of libraries I use in my web

Before I dicuss about structure of a web, I will list the libraries I use:
1. [Redux]() - State Manager
2. [Redux-thunk]() - Enable async action for Redux
3. [React-router]() - Router for react
4. [Reactstrap]() - Bootstrap for react

And I will also show you the features of the demo web to make you easy to understand the structure. The web includes 4 pages:
1. Login
2. Register page
3. Home
4. Profile

The layout of Login and register page are same. This layout will not contain navigation bar. The layout of Home and Profile are same - this will contains navigation bar.

