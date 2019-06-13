---
layout: post
title: "How to structure React Native App."
date: 2019-05-30
dateString: "2019 May 30"
categories: technical
image: /assets/images/react-native.png
thumbnail-image: /assets/images/react-native.png
summary: ""
---
## Table of contents
1. Introduction
2. Understand the default structure
2. The first way - for small app
3. The second way - for scalable app
4. Demo repository

One of the greate things about React Native is the flexibility. You can structure your app as you want. This is greate but can  also be problem when you choose the architecture for app, especially to new developers.

Before I disscus about the structure, I will list the tool I use in my project:
1. [React Navigation]() - Application Navigation
2. [Redux]() - State Manager
3. [Redux-thunk]() - Enable async action for Redux

## Understand the default structure

After you create a new project, the default structure will be (for React Native 0.60):

{% include center-image.html link="/assets/images/rn-structure/default-structure.png" alt="default structure" width="500" %}

1. **android/**: The android native code will live here. This folder contains launch icon, native modules, configurations... for android. You can open file *android/build.grade* with Android Studio and build your app normally.

2. **ios/**: The ios native code will live here. This folder contains launch icon, native modules, configurations... for ios. You can open file *ios/{project-name}.xcodeproj* or *ios/{project-name}.xcworkspace* with Xcode and build your app for ios.

3. **index.js**: The entry point to app.

4. **package.json**: This file keeps some meta data of and the libraries (and it version) was used in your app.

5. **Everything else**: You can ignore its at this time.

## The first way - for small app

When I start work with React Native, I orginized some projects with structure based on type (type-based). 

{% include center-image.html link="/assets/images/rn-structure/type-based-structure.png" alt="type based structure" width="500" %}

#### app

The *app/* folder is the sibling to the *android/* or *ios/* folder. This contains whole source code and assets of your app.

#### app/actions

This folder contains Redux Actions. I will define all actions in separate files by feature. Let me give you an example: I define login, logout and register actions in *auth.js* file, and getPlaylist, getSongs action in *song.js* file.

{% gist b5dfed84349a1f932041a945c5d971b4 %}

If you don't use Redux, you can skip this folder.

#### app/components

This folder contains components for app. The goals of this is maximun code reuse. We will push our components to this folder. Here is an example of my components folder:

{%gist e675c6bc8aed7fe56abd357094562b50%}

**Question:** Why some components are in a separate file, the others are in a folder?

Some components are very complex, so I separate it's style and it's logic to two files. Something else is simple, so no need to separate it.

**Question:** Why do I name the style of video component is video.style.js not style.js?

The answer is related to development process, I usually use *Cmd + P* (or Ctrl + P in Windows) in Visual Studio for quick open file. When I want to open file style.js of video component, if I type "*style.js*" to search for video style file, the result is too many files and so hard to pick wanted file but if I type "*video*",  two files are in video component was list in the top of result. So I can open it easer.

#### app/config

This contains the files that define color, keep the config such as api host, admod key, ...

#### app/modules (or app/libs)

This folder contains modules such as restful api module, storage module, ...

#### app/reducers

This folder contains reducers that change state based on action

#### app/screens

This folder contains screens (a component for whole screen).

#### app/App.js

This file integrate navigation, store of redux.