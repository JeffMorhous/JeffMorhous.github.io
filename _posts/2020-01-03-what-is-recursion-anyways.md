---
layout: post
title:  "What Is Recursion Anyways?"
author: jeff
categories: [ Tutorial ]
image: https://miro.medium.com/max/1400/0*LPLCjT_SUObUwLl_
---

Has a problem ever seemed too overwhelming to you to think about? Most people would recommend breaking it down as small as possible to make it manageable, and that’s exactly what recursion is!

Technically, recursion is  [“The process in which a function calls itself directly or indirectly.”](https://www.geeksforgeeks.org/recursion/)  If a function calls itself, we refer to it as a  **recursive function**.

At first glance, this seems like a nightmere. However, it can be an invaluable tool in solving programming problems. Let’s take a look at a famous search algorithm.

Imagine you’re a teacher, and you have a stack of graded papers that you’ve already sorted alphabetically by last name. If you were looking for the last name, “Patrick,” what would you do? Think about it for a minute…

One approach might be to start at the beginning of the stack, and flip through each paper until you found “Patrick.” This is an example of a  **linear search**, and it’s not always the fastest solution here.

Another intuitive approach is  **binary search**, which you’ve likely utilized in real life without even knowing what it is. To do a binary search, you start by flipping to the middle of the stack and seeing where you are in the alphabet. If the name is before Patrick, you know that Patrick is on the bottom half of the stack. If the name you’re holding is after Patrick, you know that Patrick is in the top half of the stack. No that you know that, you  _just do another binary search on the appropriate half_  of the stack!

You can repeat this process until you hit Patrick, and each binary search that you do will cut your total papers in half. If you started with 100 papers, you could have it narrowed down to 25 by only looking at 2 papers! This incredibly powerful but somehow still simple algorithm is likely the perfect example of recursion.

----------

## For recursion to work, we need 2 things to be true:

1.  For a small enough problem, we know the answer. (IE: When the name we’re looking at is Patrick, we’re holding the right paper)
2.  The problem set must get smaller every time we recurse (IE: We discard half our stack of papers)

It’s also important to note that anything you can use recursion on could be solved without recursion. Once you wrap your head around the concept, crazy complex problems have simple and elegant recursive solutions. This is especially helpful when it becomes time to translate your abstract algorithm into code.

Now that you know what recursion is, what massive problems will you solve one step at a time?

----------

Enjoy this article? Leave a comment below telling me what you think! This is part of my larger effort to improve my technical communication skills, explaining technical, nerdy topics in nontechnical, engaging ways!