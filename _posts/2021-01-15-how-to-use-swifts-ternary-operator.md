---
layout: post
title:  "How To Use Swift’s Ternary Operator"
author: jeff
categories: [ Tutorial ]
image: "https://cdn-images-1.medium.com/max/1600/1*D3ujgVPO9LiSopCrQdCB2g.jpeg"
featured: false
hidden: false
---
Ternary operators are beyond cool. They’re an easy way to do some if-else logic all on one line. Beyond that, they’re still easy to read and understand, so you don’t have to sacrifice readability for the ‘cool factor’ of using a language’s advanced features. In fact, it’s a great way to keep methods shorter and draw attention to other logic that may be more meaningful to your program.

### Start With An If-Else Statement

Take the below code for example. You compare two variables, and print something based on the result.

```
if variable1 == variable2 {
    print("Equality! 🥳")
} else {
    print("NO EQUALITY 🤬")
}
```

### Convert It To One Line
The ternary operator consists of 3 parts.
1.  A conditional check
2.  The result of the operation if the conditional is true
3.  The result of the operation if the conditional is false

For our above if-else statement, we could write it like this 👇

```
print(variable1 == variable2 ? "Equality! 🥳" : "NO EQUALITY 🤬")
```

----------

### Assigning A Value

Ternary operations in Swift aren’t limited to just print statements. In fact, the ternary operator returns a value which can be used to set a variable.

You could take the below check for the age to drink alcohol
```
var result = “”

if(age < 21){  
  result = "Too young to drink 🍺"  
} else {  
  result = "Old enough to drink 🍻"  
}

print(result)
```

This is a lot of code to just assign a string based on a number value. We can use the ternary operator to do this in just 2 lines — and you can see the example below 👇

```
let result = age > 21 ? 
```

----------

If you found this helpful, you might enjoy [checking out my book on learning to program with Swift](https://gum.co/codeforhumans)!