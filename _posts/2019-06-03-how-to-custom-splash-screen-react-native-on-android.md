---
layout: post
title: "How to custom Splash Screen of React Native App (Android)."
date: 2019-06-03
dateString: "2019 July 03"
categories: technical
image: /assets/images/react-native-splash-screen/cover.jpg
thumbnail-image: /assets/images/react-native-splash-screen/android.png
summary: "When you open an React Native App, you will see the white screen before the first react native screen is loaded. In this post, I will guide you how to custom this screen."
published: true
---
<div class="row mx-0 px-0 justify-content-center">
<div>
<img src="/assets/images/react-native-splash-screen/start.gif" alt="before" width="300"/>
<span class="mx-3">to</span>
<img src="/assets/images/react-native-splash-screen/end.gif" alt="after" width="300"/>
</div>
</div>

## Why do I see this screen? What is it?

When you open an React Native App, you will see the white screen before you see your coded screen. Why do you see it?

To know why you see this screen, you must know how an react native app work? React Native app includes two main part: native screen and javascript code. When you start an app, the system will load the native screen and the native screen will load your javascript code. So you will see the native screen (default it is white screen) util the javascript code was loaded completely.

##  How to custom this screen?

To custom this screen, you need Android Studio and some knowledge about android app.  You will create a new background and override the white background. 

#### Prepare resource

We need change style of native app to see clearly. I will change background of my app to #CCC.
<div class="row mx-0 px-0 justify-content-center">
<div>
<img src="/assets/images/react-native-splash-screen/home.jpg" alt="main" width="300"/>
</div>
</div>

If you want to show your logo in splash screen, you have to create several logo files for different desity screens. To do this, you must have a logo file, I use [android logo](/assets/images/react-native-splash-screen/android.png).

Open project in Android Studio (Open file android/build.gradle in Android Studio), create new Image Asset (click right mouse at res -> New -> Image Asset):
 - Icon Type: Launcher Icons (Legary only)
 - Name: ic_logo
 - Asset Type: Image
 - Path: select path to logo
 - Shape: None
<div class="row mx-0 px-0 justify-content-center">
<div>
<img src="/assets/images/react-native-splash-screen/create-logo.jpg" alt="create-logo" width="400"/>
</div>
</div>
#### Override default screen

Create new file colors.xml in folder android/app/src/main/res/values (right click res/values -> New -> Values resource file).
{% gist 706b9b346c2966ac946e904537fb33dc %}

If folder res/drawable don't exist, create it (right click res -> New -> Android Resource Directory):
- Directory name: drawable
- Resource type: drawable
- Source set: main
<div class="row mx-0 px-0 justify-content-center">
<div>
<img src="/assets/images/react-native-splash-screen/create-drawable.jpg" alt="Create drawable folder" width="400"/>
</div>
</div>
Create new file splash_background.xml in folder android/app/src/main/res/drawable (right click res/drawable -> New -> Drawable resource file). 
{% gist 706b9b346c2966ac946e904537fb33dc %}

Modify file styles.xml in folder android/app/src/main/res/values from 
{% gist 41400b83d58d42b4338245e044c10f08 %}
to
{% gist ddfec3ba7368fb8cd7d7a8b3a6ddc31a %}

Finally, change the screen style, you need change theme of your activity in AndroidManifest.xml in folder manifests from
{% gist 380a67e205c6aa1cbe876224a5ff3dda %}
to
{% gist d69c121be0610171421506072acc40eb %}

Project structure:
<div class="row mx-0 px-0 justify-content-center">
<div>
<img src="/assets/images/react-native-splash-screen/project-structure-android.jpg" alt="project-structure-android" width="400"/>
</div>
</div>

## Conclusion
There is result
<div class="row mx-0 px-0 justify-content-center">
<div>
<img src="/assets/images/react-native-splash-screen/end.gif" alt="project-structure-android" width="400"/>
</div>
</div>
You can find source code of project on [github](https://github.com/khanhtrancse/demo-splash-screen-rn)