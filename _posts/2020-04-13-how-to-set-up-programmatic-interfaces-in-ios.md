---
layout: post
title:  "How to Set Up Programmatic Interfaces in iOS"
author: jeff
categories: [ Tutorial ]
image: https://miro.medium.com/max/1400/0*s0Kf47H7c8GxFb3G
featured: false
hidden: false
---

There are plenty of valid reasons to use storyboards or to programmatically lay out your interface. Storyboards let us quickly build out a beautiful interface, but face limitations and scale problems. If you have a team working on an app, then Storyboards can get messy and hard to keep track of with version control. Once you decide that storyboards aren’t the tool for you, Xcode takes some tinkering to set things up to lay out your interface in Swift. After you create your project,

First,  **delete**  the  _Main.storyboard._ Yup, delete it entirely.

Then, we have to delete any reference to it- The first spot we need to take care of is the reference to  _Main.storyboard_  in  _Info.plist_ — Go ahead and  **delete the entry by clicking the minus sign**. The last place it’s referenced is in the  _Deployment Info_ section of your project settings. A dropdown for  _Main Interface_  will still say Main.storyboard,  **Select the empty option in the dropdown**.

Next, add the following to your SceneDelegate.swift

    guard let windowScene = (scene as? UIWindowScene) else { return }
    window = UIWindow(frame: windowScene.coordinateSpace.bounds)
    window?.windowScene = windowScene
    window?.rootViewController = ViewController()

Now, you can specify your actual layout in ViewController.swift!

You’re all set up to implement the design of your dreams programmatically, and  [here’s a quick reference to help you get the hang of it](https://softauthor.com/ios-ui-design-programmatically-xcode-9-swift-4)!