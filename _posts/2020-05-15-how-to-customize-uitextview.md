---
layout: post
title:  "How To Customize UITextView"
author: jeff
categories: [ Tutorial ]
image: https://miro.medium.com/max/1400/1*V4A-f4Dt00tY45pnqQZr2Q.png
featured: false
hidden: false
---

So recently I’ve been working on an iOS version of my Mock My Words app. It’s pretty simple in functionality so I wanted to compensate with a nice user interface. The main functionality requires that a user enter (or paste) in text of pretty much any size. Oftentimes iOS text entry with a  **UITextField**, but that only offers single line input. For multi-line input, you have to use  **UITextView**  😔. After throwing that in my app I was rather unimpressed with how it looked. So, I decided to put my own spin on it. It took a bit of research and I’m pleased with how it turned out so I thought I’d share with the community on how customize the UITextView object to your own needs.

----------

## Create the UITextView

I’m building this app programmatically, so the first step is to instantiate the UITextView object. If you’re using a storyboard, you’ll want to create an IBOutlet and then follow the other steps the same. I declared my UITextView at the class level of the view controller it’s used in, and the one-line looks like

        **let** textBox = UITextView()

**Please note, all of the following code should be executed by  _viewdidload()_**, but feel free to extract it to a function and then call that function from viewDidLoad()

## Add it to the view

Next, you have to add it to the view hierarchy so it actually shows up. If you’re using a storyboard, skip this step.

        view.addSubview(textBox)textBox.translatesAutoresizingMaskIntoConstraints = **false**

## Set the delegate

If you actually want your app to react to actions the user may take, you need to make your view controller extend UITextViewDelegate, and then have the following line in your configuration.

        textBox.delegate = **self**

## Customize the textbox

You can use creative freedom here, but here’s how I laid out my textbox view.

        textBox.autocorrectionType = .no
        textBox.text = placeholderText
        textBox.backgroundColor = .secondarySystemBackground
        textBox.textColor = .secondaryLabel
        textBox.font = UIFont.preferredFont(forTextStyle: .body)
        textBox.layer.cornerRadius = 20
        textBox.textContainerInset = UIEdgeInsets(top: 10, left: 10, bottom: 10, right: 10)

## Give it a shadow

Again, this is optional, but this is how I gave my textbox a shadow so it has a material design feel.

        textBox.layer.shadowColor = UIColor.gray.cgColor;
        textBox.layer.shadowOffset = CGSize(width: 0.75, height: 0.75)
        textBox.layer.shadowOpacity = 0.4
        textBox.layer.shadowRadius = 20
        textBox.layer.masksToBounds = **false**

## Tell your view where to put it

Your method for doing this will definitely vary, but I used

        NSLayoutConstraint.activate([insert your array of constraints here])

And that’s it! You have a custom textbox that kind of floats above the view you put it in.

------------
If you liked this, you might like to get updates from me when I write or make something new. I promise I won't spam you, and you can unsubscribe anytime. <a href="https://www.getrevue.co/profile/jeffmorhous">Sign up here.</a>