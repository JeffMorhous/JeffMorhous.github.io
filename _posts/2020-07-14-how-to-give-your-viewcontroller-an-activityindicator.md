---
layout: post
title:  "How To Give Your ViewController An Activity Indicator"
author: jeff
categories: [ Tutorial ]
image: https://miro.medium.com/max/1400/0*ybjK_NN1aGJ7eSok
featured: false
hidden: false
---


UIKit provides a nifty little spinning wheel we can display to the user when we’re waiting on something that the user can’t see. It’s considered a best practice to pop one of these up when doing something like a network call, so the person using our app isn’t clueless as to what’s going on. Basically, you create the spinner, and add it to your view. Then, just before a background task like an API request, tell it to animate. When the background request finishes, you just tell it to stop animating.

**First, declare your spinner in the ViewController**

	var activityIndicator = UIActivityIndicatorView(style: .Large)

**Inside viewDidLoad, or a method called by viewDidLoad, add the spinner to your view**

	activityIndicator.translatesAutoresizingMaskIntoConstraints = false
	view.addSubview(activityIndicator)
	activityIndicator.centerXAnchor.constraint(equalTo: view.centerXAnchor).isActive = true
	activityIndicator.centerYAnchor.constraint(equalTo: view.centerYAnchor).isActive = **true**

**Before you make your background task, start the spinner**

	activityIndicator.startAnimating()

**And when the background task completes, stop the spinner!**

	self.activityIndicator.stopAnimating()

----------

This is such a small UI feature that has a huge benefit. If you implement it correctly, the people that use your app will probably never consciously notice it. But if you don’t implement this, users will likely feel like your app is slow, or mistake a normal wait time for a buggy freeze of the app. Hope you got some value out of this, I know your users will!