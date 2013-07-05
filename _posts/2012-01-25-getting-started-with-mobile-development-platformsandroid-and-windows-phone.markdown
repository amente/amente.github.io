---
author: amentebullo
comments: true
date: 2012-01-25 06:53:52
layout: post
slug: getting-started-with-mobile-development-platformsandroid-and-windows-phone
title: 'Getting Started with Mobile Development Platforms,Android and Windows Phone. '
wordpress_id: 358
categories:
- Computer Programming
thumbnail: /images/uploads/2012/01/android.png
preview: "I configured my PC to be a perfect mobile development environment.My previous PC had performance issues that held me back,but now I have started two projects, one on Android and one on Windows Phone."
---

I configured my PC to be a perfect mobile development environment.My previous PC had performance issues that held me back,but now I have started two projects, one on Android and one on Windows Phone. Here are some steps to help you get started if you haven't  already: I know there is a lot of tutorials and how to's on the internet (they are what got me started first place), but I will try to be brief and concise here,on how to set up a working environment with out no fuss.

**Setting up a complete working Android development environment in Windows 7.**

Requirements:

Internet access : It will be almost impossible if you don't have internet access on your development PC.

A computer with at least 3GB of memory (2GB will do but there will be some performance issues, especially when you run the Android Virtual Device ).

Procedures:

Step 1: Download and Install the latest Java JDK, [from here](http://www.oracle.com/technetwork/java/javase/downloads/index.html).

Step 2: Download and Install Eclipse Classic 3.7.1 (Indigo) , [from here](http://www.eclipse.org/downloads/).

Step 3: Download and Install the Android SDK windows installer, [from here.](http://developer.android.com/sdk/index.html)

Step 4: Start Eclipse, then select **Help** > **Install New Software **and add the site below to the repository

    
    https://dl-ssl.google.com/android/eclipse/


Step 5: Once the repository is loaded, Install one or more of the Android platforms. (I recommend Android 4.0, and Android 2.3) to start with.

Step 6: You are almost done, but you need to create an Android Virtual Device , if you haven't done already so, on Step 3. Here is a tip to get the AVD boot up faster: Give the device at least 1GB SD card, enable Snapshot, and Change the built in skin resolution to the less graphic HVGA.

If every thing went alright, then you have created your Android development IDE, integrated with Eclipse on Windows 7. The next step is to get started with coding and here is a famous tutorial that I found very helpful:[http://www.vogella.de/articles/Android/article.html](http://www.vogella.de/articles/Android/article.html)

**Setting up a complete working Windows Phone development environment in Windows 7.**

We all know that Microsoft products are integrated to each other so this one is very simple:

Requirement: I recommend a PC with 3GB or more to get it perform well.

Step 1: If you are a student, then Microsoft has waived the Visual Studio Ultimate IDE for you. So go and claim it from [https://www.dreamspark.com/](https://www.dreamspark.com/) ,If you are not a student then, just get Visual Studio by whatever means because it is a must here.

Step 2: Once you have install Visual Studio ,make sure it is updated to SP1, then  go here and install the Windows Phone SDK, [http://www.microsoft.com/download/en/details.aspx?id=27570](http://www.microsoft.com/download/en/details.aspx?id=27570)

If everything went alright, then you have a complete Windows Phone development environment set up in Visual Studio. You better start building apps, because Microsoft is being generous when the say get apps released and you will be awarded points that will get you say.. an [XBOX360](http://allaboutwindowsphone.com/flow/item/13684_Release_4_Windows_Phone_apps_r.php).

Here are final screen shots from my PC:

[![](/images/uploads/2012/01/android.png)](/images/uploads/2012/01/android.png)

[![](/images/uploads/2012/01/windows-phone.png)](/images/uploads/2012/01/windows-phone.png)


